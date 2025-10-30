# Sessy Smart Accu Manager

Manage multiuple sessy's with smart loading





Aanleiding:

Ik heb twee sessys in huis en het valt mij op dat deze laden als de prijs relatief hoog is. 

Lees: Uren erna zijn er goedkopere uren om te laden. Prijstechnisch is dat intresanter

De Sessy's lijken geen rekening te houden met het max Ampere van de net aansluiting.



Met deze blueprint probeer dit beter te doen.



Status: Dit project is nog in ontwikkeling. Er bestaat geen roadmap of planning of onderhoudschema.

Ik doe dit wanneer ik dit wil en tijd voor hebt



Disclaimer:  Code is gemaakt met behulp van Gemini en eigen research.

&nbsp;            Ik ben NIET aansprakelijk voor elke vorm van schade bij gebruik van deze code.

&nbsp;			 Gebruik is op eiden risico

&nbsp;			 



Doel code:

Het doels is om met twee sessy's van 5 kWh deze zo optimaal mogelijk te laden en ontladen.

Bij het laden wordt rekening gehouden met:

\- verwachte tijdsduur benodigd voor laden tot vol

\- Beste moment, op de goedkoopste uren, van de dag laden.



Tijdens het laden wordt de gemiddelde prijs van de lading bijgehouden.



Het ontladen gebeurd met de nul-op-de-meter methode.

Het ontladen start vanf xx cent boven de gemiddelde prijs van de lading





Afhankelijkheden:

Deze blueprint is afhankelijk van de sessy integratie van Pim Doos ( https://github.com/PimDoos/ha-sessy )

en energieleverancier integratie voor de prijzen en forecast


Helpers:

De input_number helpers (input_vermogen_accu_1 en input_vermogen_accu_2) moeten handmatig in Home Assistant worden aangemaakt voordat u de Blueprint kunt configureren.
Volg deze stappen:

1. Ga in Home Assistant naar Instellingen $\rightarrow$ Apparaten & Diensten $\rightarrow$ Helpers (tabblad bovenaan).
2.    Klik op Helper aanmaken.
3.    Kies Numeriek (Number).
4.        Configureer de helper voor Accu 1:Naam: Accu 1 Vermogen (W) (of een duidelijke naam)
            Minimum waarde: $-5000$ (of uw maximale ontlaadvermogen, negatief)
            Maximum waarde: $5000$ (of uw maximale laadvermogen, positief)
            Stap: 1
            Eenheid: W
            Weergavemodus: Schakelaar of Box (afhankelijk van uw voorkeur)
    
5. Herhaal dit proces voor Accu 2.
Zodra deze twee input_number helpers bestaan (bijv. input_number.accu_1_vermogen_w en input_number.accu_2_vermogen_w), kunt u ze selecteren wanneer u de Blueprint importeert en configureert.


change-log:

0.001 First ever version





to-do

\- Keuze optie maken nul-op-de-meter na xx cent boven gemiddelde prijs of bij x watt verbruik van het net

\- max laad en ontlaad vermogen

&nbsp;



