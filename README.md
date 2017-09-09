# pr

Her kan du få prøve deg på den såkalte Forking workflowen. Målet ditt
er å få en endring merget inn i dette repositoryet (`wkillerud/pr`).

Om du støter på et ord eller begrep du ikke forstår kan det hende
du finner en forklaring på
[Github sin Github Glossary](https://help.github.com/articles/github-glossary/).

Du finner noen lenker til annet hjelpemateriale om Git nederst i
denne filen.

## Hva du trenger

* Git, enten via [terminalen (anbefales)](https://git-scm.com/) eller
med en GUI som for eksempel Github sin egen app, SourceTree eller 
TortioseGit.
* For å lage en pull request på Github må du ha en Github-konto

## PR 101

Kort fortalt er det åtte steg for å komme i mål.
Stegene blir beskrevet i mer detalj senere.

1. Lag en fork av dette repositoryet
2. Klon din fork til PCen din
3. Lag en branch fra `master`
4. Gjør en endring
5. Lag en commit med endringen din
6. Push endringen til din fork
7. Lag en pull request mot `wkillerud/pr` sin `master` branch
8. Jeg ser over pull requesten, og hvis alt ser OK ut merger jeg den

### Forking

Du lager en fork av dette repositoryet ved å trykke på Fork-knappen
øverst til høyre. Github bruker noen sekunder på å lage en kopi som
legges under din brukerkonto.

Når Github er ferdig med kopieringen blir du tatt til forken din.
Under navnet på repositoryet oppe til venstre skal det stå
"forked from wkillerud/pr".

### Cloning

For de fleste endringer vil du trenge å jobbe på PCen din. Github
har etter hvert fått støtte for å endre filer i nettleseren, men
det blir å jukse litt ;)

For å få filene ned på PCen din må du lage en klone. Trykk på den
grønne "Clone or download"-knappen. Kopier adressen.

Start Git Bash eller en annen Git-klient og klon repositoryet ditt:

```
$ git clone https://github.com/DITT_BRUKERNAVN/pr.git
```

> Om du får en feilmelding om at HTTPS ikke støttes må du trykke
> "Use SSH" i popupen til "Clone or download". Github sine hjelpesider
> burde forklare hva som må gjøres.

### Branching

Før man gjør endringer er det god praksis å lage sin egen branch.
Det gjør at det er enklere å gå tilbake til en fungerende versjon
om noe skulle gå galt, og det er lettere å jobbe sammen med andre
som gjør endringer i den samme koden.

For å lage en branch man skal jobbe på med én gang bruker man ofte
denne kommandoen:

```
$ git checkout -b feature/my-shiny-new-thing
```

`-b` gjør at Git lager branchen med navnet
`feature/my-shiny-new-thing` for deg. Det er en raskere måte å skrive
dette på:

```
$ git branch feature/my-shiny-new-thing
$ git checkout feature/my-shiny-new-thing
```

### Gjør en endring

Her står du ganske fritt. Du kan lage en ny fil med noe gøy, eller du
kan endre på en fil som allerede finnes. Du kan for eksempel legge til
navnet eller brukernavnet ditt i filen `CONTRIBUTORS.md`.

Åpne filen i en editor av eget valg, eksempelvis Atom, Visual
Studio Code, Sublime Text, Nodepad++, vim - så lenge den kan åpne en
tekstfil gjør den nytten :)

Gjør endringen din og lagre.

### Lag en commit

For å kunne dele endringen din må du commite den. Det er en
tostegsprosess med Git.

1. Stage endringen din med `git add CONTRIBUTORS.md`
2. Commit endringen din med `git commit`

Om du ikke har så mye på hjertet kan du bruke denne kommandoen:

```
$ git commit -m "Dette er min commitmelding"
```

Som standard tar nemling `git commit` deg til en terminalbasert
editor kalt `vim`, så vidt nevnt i forrige seksjon.
Formålet er å gi en en beskrivelse av endringen du har gjort
som kommer til å synes i historikken til dette repositoriet.
Du kan se hvordan en commitmelding vil se ut ved å skrive kommandoen
`git log`.

#### Hvorfor skrive meldinger?

Det anbefales å skrive gode meldinger for å gjøre det lettere for
andre som jobber med koden å se hvorfor en endring ble gjort. Det
er ikke så farlig her, men jeg anbefaler likevel å komme inn i vanen
med å skrive gode meldinger, så prøv å unngå å bruke `-m` om du kan.

For å skrive en commitmelding i vim må du kjenne til noen få
vim-kommandoer:

* Trykk `i` for å gå i _insert mode_, som lar deg skrive tekst
* Trykk `ESC` for å gå tilbake til _command mode_
* Trykk `:x` (kolon, så x, så Enter) for å lagre meldingen og gå ut
av vim

Om du vil unngå vim kan du be Git bruke en annen editor. Sjekk
dokumentasjonen på [Git sine hjemmesider](https://git-scm.com).

### Push endringen til din fork

For å gjøre endringen din tilgjengelig for en pull request må den
publiseres på Github. For å gjøre det må du bruke kommandoen
`git push origin HEAD`.

Om alt går etter planen skal du få denne beskjeden:

```
To github.com:DITT_BRUKERNAVN/pr.git
 * [new branch]      HEAD -> feature/my-shiny-new-thing
```

Du kan dobbeltsjekke på Github.com at endringen er pushet
ved å se etter branchen din i nedtrekksmenyen til venstre 
("Branch: master").

### Lag en pull request!

Github er ganske hjelpsom, så om du ser på repositoryet ditt på
Github etter å ha pushet en endring vil du få spørsmålet om du
vil lage en pull request.

Trykk på "Compare & pull request"-knappen. Du tas til en ny side
der du kan se over endringene dine og komme med en beskrivelse som
vises i pull requesten på Github. Det er også en håndfull
nedtrekksmenyer der du kan velge ting som _target branch_ og liknende.
Github bør ha valgt riktige verdier her som standard, så de kan du
la være enn så lenge.

Om endringene du gjorde ser OK ut når du scroller ned på siden kan
du trykke på knappen "Create pull request".

Gratulerer, og tusen takk - du har nå laget en pull request!

### Merging av pull request

Nå er det opp til eieren av repositoryet (that's me!) å gå igjennom
pull requesten. Om alt ser OK ut for eieren vil hen merge pull
requesten. Endringen er nå "offisiell", og du er en contributor.

### Bonus: bruk din nye super power

Nå som du vet hvordan pull requests fungerer, hvorfor ikke bruke
kunnskapen til å hjelpe et open source prosjekt?

freeCodeCamp har [en fin artikkel](https://medium.freecodecamp.org/finding-your-first-open-source-project-or-bug-to-work-on-1712f651e5ba)
om hvor og hvordan man kan bidra til et prosjekt som nybegynner. Om
du en gang lager et pull request og føler du sitter fast kan du pinge
meg (wkillerud) her på Github, så kan jeg se om jeg kan lose deg
igjennom :)

Lykke til!

## Litt materiale om Git

[Atlassian har en veldig god guide til Git](https://www.atlassian.com/git/tutorials/what-is-version-control)
som starter med det grunnleggende og går videre til å dekke
flere nyttige temaer som ulike workflows, blant annet den som ble
introdusert over ([Forking Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows#forking-workflow)).

Github har noe hjelpemateriale for å komme i gang:

* [Hello, world!](https://guides.github.com/activities/hello-world/).
Introduksjon til noen kjernekonsept. Bruker Github.com, ikke terminal.
* [Bootcamp](https://help.github.com/). Litt mer hands-on.

Om du er mer viderekommen finnes det en gratis bok som går i dybden:

* [Pro Git](https://git-scm.com/book/en/v2)

