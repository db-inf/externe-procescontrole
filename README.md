Procescontrole van een reeks of lus bash shellopdrachten
========================================================

De bestanden in deze directory controleren het verloop van een lang durende reeks of lus van shellopdrachten. Ze kunnen in die reeks opdrachten ingesloten worden met de opdracht "source". Door vervolgens enkel hun naam te veranderen, kan de lus gepauzeerd worden, of kan de computer in slaapstand of uit gezet worden. Ook kan tijdens uitvoering nog het aantal threads gewijzigd worden, dat zware opdrachten in de reeks mogen gebruiken.

Meer over gebruik en werking is te lezen in de andere bestanden van dit project.

Ook handig om b.v. een reeks shellopdrachten uitgesteld te starten, is de volgende functie, die u b.v. in ~/.bash_aliases kan definiëren:

    # start de hierna volgende shell-opdracht van een reeks opdrachten op de als parameters opgegeven tijd.
    # Voorbeeld: "wachttot 10:20; opdracht ..." (vandaag om 10u20)
    # Voorbeeld: "wachttot tomorrow 12:10; opdracht ..." (morgen om 12u10)
    wachttot() { sleep $(( $(date -d "$*" +%s) - $(date +%s) )); }

Deze werkwijze voor procescontrole is uitvoerig getest in mijn  scripts voor hercompressie van video, uitgevoerd in een lus voor meerdere filmbestanden.
