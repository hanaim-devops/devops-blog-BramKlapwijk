# Blijven deployen met FluxCD

*[Voornaam Achternaam, oktober 2024.](https://github.com/hanaim-devops/blog-student-naam)*

FluxCD is een populaire tool voor continuous delivery en maakt gebruik van het GitOps-principe om de implementatie van applicaties in Kubernetes-omgevingen te automatiseren.

Als je in je applicatie gebruik maakt van Kubernetes klusters moet je op het moment dat je een update wilt uitvoeren nog
zelf veel stappen maken om deze ook op productie te deployen. Aangezien je deze configuratie bestanden al in Git opslaat
is het nog maar een kleine stap om dit ook te automatiseren.

## GitOps

In GitOps is de Git repository de enkele bron van waarheid voor infrastructuur. In plaats van configuraties handmatig 
aan te passen op servers, automatiseert GitOps de implementatie en het beheer van infrastructuur via Git-repositories.
Onderdeel van Git OPS zijn bijvoorbeeld CI/CD pipelines en infrastructure as code.

De essentiele onderdelen van een GitOps werkwijze zijn:

1. Git repository
2. CD pipeline
3. Application Deployment Tool
4. Monitoring systeem

## FluxCD

Hier komt FluxCD in het spel, zij pakken de application deployment op van de GitOps werkwijze. FluxCD kan de toestand van je Kubernetes-cluster automatisch synchroniseren met de configuratie die in een Git-repository staat. Als er wijzigingen in de repository worden aangebracht, worden deze automatisch naar het cluster gepusht.

Omdat de staat van de infrastructuur in Git bewaard wordt kan er ook makkelijk weer teruggedraaid worden naar een vorige versie.


## Alternatieven

## Implementatie

## Bronnen

<hr/>
# Wat zijn de belangrijkste functies van FluxCD en hoe ondersteunen ze GitOps?

FluxCD is een populaire tool voor continuous delivery en maakt gebruik van het GitOps-principe om de implementatie van applicaties in Kubernetes-omgevingen te automatiseren. Hier zijn de belangrijkste functies van FluxCD en hoe ze GitOps ondersteunen:

## Belangrijkste functies van FluxCD

### 1. Automatische Synchronisatie

FluxCD kan de toestand van je Kubernetes-cluster automatisch synchroniseren met de configuratie die in een Git-repository staat. Als er wijzigingen in de repository worden aangebracht, worden deze automatisch naar het cluster gepusht.
Git als.

### 2. Enkele Bron van Waarheid

Alle configuraties en applicatie-instellingen worden in Git opgeslagen, waardoor teams versiebeheer, rollback-mogelijkheden en audit trails hebben voor hun infrastructuur en applicaties.

### 3. Continuële Observatie

FluxCD observeert continu de Git-repository op wijzigingen. Zodra een wijziging wordt gedetecteerd, past het deze aan in het Kubernetes-cluster.

### 4. Rollback-mogelijkheden

Door gebruik te maken van Git kunnen teams eenvoudig terugrollen naar eerdere versies van hun configuratie als dat nodig is.

### 5. Integratie met andere tools

FluxCD kan gemakkelijk geïntegreerd worden met andere tools en platformen, zoals Helm voor pakketbeheer, Kustomize voor het beheren van configuraties, en verschillende CI/CD-tools.

### 6. Beheer van Helm Releases

FluxCD ondersteunt het beheer van Helm-charts, waardoor het eenvoudig wordt om applicaties die met Helm zijn geïnstalleerd te beheren en bij te werken.

### 7. Policies en Validaties

Je kunt policies instellen om te bepalen hoe en wanneer wijzigingen doorgevoerd worden, wat helpt bij het handhaven van compliance en best practices.

## Ondersteuning van GitOps

### Declaratieve Configuratie

GitOps maakt gebruik van declaratieve configuratie, wat betekent dat je de gewenste toestand van je applicaties in Git definieert. FluxCD past deze configuraties automatisch toe, waardoor je consistentie en voorspelbaarheid in je deployments hebt.

- **Versiebeheer**: Door het gebruik van Git kunnen alle wijzigingen worden gevolgd, en kan je eenvoudig terugkeren naar eerdere versies. Dit maakt het eenvoudig om wijzigingen in de tijd te begrijpen en om audits uit te voeren.
- **Samenwerking**: Teams kunnen samen aan de configuratie werken via pull requests, wat samenwerking bevordert en zorgt voor een betere controle over wie wat heeft gewijzigd.
- **Observability**: FluxCD biedt inzicht in de huidige toestand van de applicaties in je cluster en hoe deze zich verhouden tot de configuraties in Git, wat helpt bij troubleshooting en het waarborgen van de gewenste toestand.

Door deze functies stelt FluxCD teams in staat om efficiënt en veilig met Kubernetes om te gaan, wat leidt tot snellere leveringen en minder fouten. GitOps met FluxCD bevordert een cultuur van samenwerking en transparantie in softwareontwikkeling.

# Hoe verschilt FluxCD van andere CI/CD-tools voor Kubernetes?

FluxCD verschilt op verschillende manieren van andere CI/CD-tools voor Kubernetes. Hier zijn enkele belangrijke punten van differentiatie:

### 1. **GitOps-aanpak**

- **FluxCD**: Gebruikt de GitOps-principes waarbij Git de enkele bron van waarheid is voor de configuratie van de applicatie en de infrastructuur. Wijzigingen in de Git-repository worden automatisch gesynchroniseerd met het Kubernetes-cluster.
- **Andere CI/CD-tools**: Veel traditionele CI/CD-tools gebruiken een meer procedurele benadering waarbij handmatige of geautomatiseerde pipelines worden opgezet om code te bouwen, testen en implementeren, zonder altijd Git als enige bron van waarheid te gebruiken.

### 2. **Declaratieve Configuratie**

- **FluxCD**: Maakt gebruik van declaratieve configuraties, wat betekent dat je de gewenste toestand van je infrastructuur en applicaties in Git definieert. FluxCD zorgt ervoor dat het cluster deze toestand handhaaft.
- **Andere CI/CD-tools**: Sommige tools gebruiken een imperatieve benadering, waarbij je specifieke stappen definieert die moeten worden uitgevoerd, wat kan leiden tot complexiteit en minder voorspelbaarheid.

### 3. **Automatische Synchronisatie**

- **FluxCD**: Observaties van de Git-repository en synchroniseert automatisch de toestand van het cluster met de configuratie in Git.
- **Andere CI/CD-tools**: Veel tools vereisen een handmatige trigger of een geplande job om de implementaties uit te voeren, wat kan leiden tot vertragingen of inconsistenties.

### 4. **Focus op Kubernetes**

- **FluxCD**: Specifiek ontworpen voor Kubernetes en geoptimaliseerd voor het werken binnen deze omgeving, met ondersteuning voor Kubernetes-specifieke features zoals Kustomize en Helm.
- **Andere CI/CD-tools**: Veel CI/CD-tools zijn meer algemeen en kunnen meerdere omgevingen en platformen ondersteunen, wat betekent dat ze mogelijk niet de diepgaande Kubernetes-integratie bieden die FluxCD heeft.

### 5. **Configuratiebeheer**

- **FluxCD**: Beheert de configuratie van applicaties direct via Git, wat resulteert in duidelijke versiebeheer en rollback-mogelijkheden.
- **Andere CI/CD-tools**: Vaak gefocust op het bouwen en testen van code met minder nadruk op hoe de configuraties in de productie-omgeving worden beheerd.

### 6. **Ecosysteem en Integraties**

- **FluxCD**: Integreert naadloos met andere tools en ecosystemen binnen het Kubernetes-landschap, zoals Helm, Kustomize en observability-tools.
- **Andere CI/CD-tools**: Hebben mogelijk meer plug-ins en integraties voor verschillende CI/CD-workflows, maar niet noodzakelijk voor Kubernetes-specifieke workflows.

### 7. **Community en Adoptie**

- **FluxCD**: Ondersteund door de open-source community en een focus op de Kubernetes-gemeenschap, wat betekent dat het vaak sneller nieuwe functies en verbeteringen aanneemt die specifiek voor Kubernetes zijn.
- **Andere CI/CD-tools**: Kunnen bredere ondersteuning hebben voor verschillende platformen en omgevingen, maar mogelijk niet de specifieke focus op Kubernetes en GitOps die FluxCD biedt.

### Samenvatting

FluxCD is uniek in zijn focus op GitOps en declaratieve configuratie, wat het een krachtige tool maakt voor teams die willen profiteren van de voordelen van automatisering en versiebeheer in Kubernetes. Terwijl andere CI/CD-tools ook waardevolle functionaliteit bieden, is FluxCD specifiek ontworpen om de uitdagingen van Kubernetes-omgevingen aan te pakken.

# Wat is het GitOps-werkmodel en hoe past FluxCD daarin?

Het GitOps-werkmodel is een aanpak voor het beheren en automatiseren van infrastructuur en applicaties door middel van versiebeheer, meestal met Git als centraal systeem. De basisprincipes van GitOps zijn gebaseerd op het idee dat je infrastructuur en applicatieconfiguraties als **code** behandelt. Dit betekent dat alle wijzigingen, inclusief het uitrollen van applicaties of het aanpassen van infrastructuur, worden aangebracht door updates aan de configuratiebestanden in een Git-repository. Deze repository fungeert als de "single source of truth".

### Basisprincipes van GitOps

1. **Versiebeheer**: Alle infrastructuur en applicatieconfiguraties worden opgeslagen in een Git-repository. Hierdoor kun je elke verandering volgen, beheren en terugdraaien als dat nodig is. Git biedt logboekregistratie en auditingfunctionaliteiten.
2. **Automatisering van uitrol**: Een GitOps-agent (zoals FluxCD) controleert de repository continu op wijzigingen. Zodra een wijziging wordt gedetecteerd (bijvoorbeeld een nieuwe versie van een applicatie of een infrastructuuraanpassing), wordt deze automatisch uitgerold naar de doelomgeving, zoals een Kubernetes-cluster.
3. **Continuïteit en consistentie**: De infrastructuur blijft in de staat zoals gespecificeerd in de Git-repository. Als er handmatige wijzigingen buiten de repository om worden aangebracht (bijvoorbeeld direct in het cluster), kunnen deze worden overschreven door de versie in Git.
4. **Veiligheid en rollback**: Omdat alles via versiebeheer verloopt, is het eenvoudig om wijzigingen te testen en te beoordelen voordat ze worden uitgerold. Als er problemen optreden, kunnen eerdere versies eenvoudig worden teruggezet.

### Hoe past FluxCD hierin?

FluxCD is een **GitOps-tool** die specifiek is ontwikkeld voor Kubernetes. Het automatiseert het synchroniseren van de configuraties in de Git-repository met een Kubernetes-cluster. Dit betekent dat elke wijziging in de infrastructuur of applicatieconfiguratie die in Git wordt aangebracht, automatisch wordt geïmplementeerd in het cluster. FluxCD voert de volgende taken uit in een GitOps-omgeving:

1. **Continu synchroniseren met Git**: FluxCD controleert periodiek de Git-repository om te zien of er nieuwe commits zijn die overeenkomen met wijzigingen in de applicatieconfiguraties of infrastructuur. Als er nieuwe wijzigingen zijn, wordt de clusterconfiguratie aangepast om in overeenstemming te zijn met wat er in de Git-repository staat.
2. **Declaratieve configuraties**: Met FluxCD kun je Kubernetes-resources zoals YAML-bestanden of Helm-charts declaratief beheren. Dit past goed bij het GitOps-principe, waar de volledige systeemconfiguratie wordt beheerd als code.
3. **Rollback en audits**: Omdat FluxCD werkt met een Git-repository, kun je eenvoudig teruggaan naar een eerdere versie van je infrastructuur of applicaties als er iets misgaat. Elke wijziging wordt gelogd in Git, waardoor er een volledig auditable geschiedenis is.
4. **Integratie met CI/CD**: FluxCD integreert goed met Continuous Integration/Continuous Deployment (CI/CD) pipelines. Nadat code in de Git-repository wordt geüpdatet (bijvoorbeeld na een CI-build), pakt FluxCD automatisch de wijzigingen op en voert de uitrol uit naar het cluster.
5. **Helm-ondersteuning**: FluxCD ondersteunt het gebruik van Helm-charts, een veelgebruikte tool in Kubernetes om applicaties als pakket te beheren. Flux kan automatisch updates doorvoeren van nieuwe versies van Helm-charts die zijn vastgelegd in Git.

### Voordelen van GitOps met FluxCD

- **Automatisering**: Vermindert handmatige fouten door alles automatisch te laten uitrollen op basis van wijzigingen in Git.
- **Consistentie en herhaalbaarheid**: Je kunt dezelfde infrastructuur en applicatieconfiguraties herhaaldelijk uitrollen over meerdere omgevingen (ontwikkeling, test, productie).
- **Betere samenwerking**: Aangezien alles in Git gebeurt, kunnen teams beter samenwerken door middel van pull requests, code reviews, en goedkeuringsprocessen.

Samenvattend is GitOps een methodologie waarbij infrastructuurbeheer en applicatiedeployment volledig worden beheerd vanuit een versiebeheersysteem zoals Git, en FluxCD is een van de belangrijkste tools die deze methodologie implementeert voor Kubernetes-omgevingen.

# Hoe configureer en implementeer je FluxCD in een Kubernetes-omgeving?

Het configureren en implementeren van FluxCD in een Kubernetes-omgeving volgt een aantal stappen die je helpen om het GitOps-werkmodel op te zetten. Hieronder beschrijf ik de belangrijkste stappen om FluxCD in een Kubernetes-cluster te installeren en te configureren, met gebruik van een Git-repository als de bron van waarheid voor je applicaties en infrastructuurconfiguraties.

### Voorwaarden

Voordat je FluxCD kunt implementeren, moet je het volgende hebben:

- **Kubernetes-cluster**: Je hebt toegang nodig tot een werkend Kubernetes-cluster. Dit kan lokaal zijn (bijvoorbeeld via Minikube of Kind) of een extern cloudgebaseerd cluster (zoals EKS, GKE, of AKS).
- **Git-repository**: Een Git-repository (bijv. op GitHub, GitLab, etc.) waar je de configuratie- en applicatiebestanden beheert.
- **Kubectl**: De command-line tool om je Kubernetes-cluster te beheren, moet zijn geïnstalleerd en geconfigureerd om met je cluster te communiceren.

### Stappen om FluxCD te configureren en implementeren

### 1. **Installeer de Flux CLI**

De Flux CLI is nodig om Flux te installeren en te beheren in je Kubernetes-cluster.

```bash
bash
Copy code
brew install fluxcd/tap/flux
# of via curl als je brew niet gebruikt:
curl -s https://fluxcd.io/install.sh | sudo bash

```

Controleer of Flux correct is geïnstalleerd:

```bash
bash
Copy code
flux --version

```

### 2. **Koppel je Git-repository**

Je moet Flux toegang geven tot je Git-repository. Dit doe je door een koppelingssleutel te genereren en die aan Flux te verstrekken. Als je bijvoorbeeld GitHub gebruikt, kun je een SSH-sleutel aanmaken:

```bash
bash
Copy code
ssh-keygen -t rsa -b 4096 -C "flux"

```

- Voeg de publieke sleutel toe aan je Git-repository (bijv. op GitHub onder **Repository Settings > Deploy keys**).
- Houd de privésleutel veilig, omdat je deze straks nodig hebt om Flux toegang te geven tot de repository.

### 3. **Installeer Flux in Kubernetes**

Voer de volgende Flux-commando’s uit om FluxCD in je Kubernetes-cluster te installeren en te configureren. Dit gaat gepaard met het instellen van een repository en namespace.

```bash
bash
Copy code
flux install

```

Met dit commando worden de Flux-controllers in je Kubernetes-cluster geïnstalleerd, waaronder de **source-controller**, **kustomize-controller**, en **helm-controller** (indien je Helm gebruikt).

### 4. **Configureer Flux om met je Git-repository te synchroniseren**

Nu gaan we Flux configureren om je Git-repository te volgen en je applicaties of infrastructuurconfiguraties te beheren.

1. **Maak een `GitRepository` resource**. Dit vertelt Flux waar je Git-repository zich bevindt en hoe vaak hij deze moet controleren.

```yaml
yaml
Copy code
apiVersion: source.toolkit.fluxcd.io/v1beta1
kind: GitRepository
metadata:
  name: flux-system
  namespace: flux-system
spec:
  interval: 1m0s
  url: ssh://git@github.com/<your-username>/<your-repo>.git
  secretRef:
    name: flux-system

```

- De `url` verwijst naar je Git-repository.
- `interval` geeft aan hoe vaak Flux de repository controleert op nieuwe wijzigingen.
1. **Maak een `Kustomization` resource**. Dit zegt tegen Flux welke directory’s in je Git-repository moeten worden gebruikt om je applicaties of infrastructuur uit te rollen.

```yaml
yaml
Copy code
apiVersion: kustomize.toolkit.fluxcd.io/v1beta1
kind: Kustomization
metadata:
  name: apps
  namespace: flux-system
spec:
  interval: 1m
  path: "./path/to/your/app"
  prune: true
  sourceRef:
    kind: GitRepository
    name: flux-system
  targetNamespace: default

```

- De `path` geeft het pad aan waar je applicatie of configuratiebestanden zich in de Git-repository bevinden.
- `prune` zorgt ervoor dat resources die niet langer in Git staan, worden verwijderd.
- `targetNamespace` geeft aan in welke namespace de applicaties moeten worden uitgerold.

### 5. **Voeg de SSH-sleutel toe aan Flux**

Nu moet je de eerder gegenereerde SSH-sleutel toevoegen aan je Kubernetes-cluster zodat Flux toegang krijgt tot de Git-repository.

1. Converteer de privésleutel naar een Kubernetes Secret:

```bash
bash
Copy code
kubectl create secret generic flux-system \
  --namespace=flux-system \
  --from-file=identity=<path-to-your-private-key>

```

1. Verifieer of de secret correct is aangemaakt door het volgende te controleren:

```bash
bash
Copy code
kubectl get secrets -n flux-system

```

### 6. **Valideer en bekijk de synchronisatie**

Flux zal nu de Git-repository volgen en automatisch de configuratie uitrollen zoals gedefinieerd. Om de status van de synchronisatie te controleren:

```bash
bash
Copy code
flux get all

```

Dit toont de status van de resources die Flux beheert. Je kunt hier zien wanneer de laatste synchronisatie is uitgevoerd en of er fouten zijn opgetreden.

### 7. **Controleer de status van je resources in Kubernetes**

Gebruik `kubectl` om te controleren of je applicaties en configuraties succesvol zijn uitgerold:

```bash
bash
Copy code
kubectl get pods

```

Je zou nu de applicaties en infrastructuurresources in je Kubernetes-cluster moeten zien draaien, zoals gedefinieerd in je Git-repository.

### Optioneel: Helm-ondersteuning toevoegen

Als je Helm gebruikt om je applicaties te beheren, kun je de **Helm-controller** van Flux gebruiken. Eerst moet je een Helm-chart repository configureren:

```yaml
yaml
Copy code
apiVersion: source.toolkit.fluxcd.io/v1beta1
kind: HelmRepository
metadata:
  name: my-helm-repo
  namespace: flux-system
spec:
  interval: 1m
  url: https://charts.bitnami.com/bitnami

```

Daarna maak je een **HelmRelease** resource aan om een specifieke chart te deployen:

```yaml
yaml
Copy code
apiVersion: helm.toolkit.fluxcd.io/v2beta1
kind: HelmRelease
metadata:
  name: my-helm-release
  namespace: default
spec:
  chart:
    spec:
      chart: nginx
      version: "9.3.7"
      sourceRef:
        kind: HelmRepository
        name: my-helm-repo
        namespace: flux-system
  interval: 1m
  install:
    createNamespace: true

```

Met deze configuratie beheert Flux de Helm-charts en synchroniseert ze met de chart-versies in Git.

### Samenvatting

1. **Installeer de Flux CLI**.
2. **Maak een SSH-sleutel** en voeg deze toe aan je Git-repository.
3. **Installeer FluxCD** in je Kubernetes-cluster.
4. **Maak een GitRepository en Kustomization resource** om Flux met je repository te laten synchroniseren.
5. **Voeg je SSH-sleutel toe als een Kubernetes Secret**.
6. **Controleer de synchronisatie** en zorg dat alles correct draait.

Met deze stappen heb je FluxCD succesvol geïmplementeerd in een Kubernetes-cluster en je cluster ingesteld om automatisch applicaties en infrastructuur te synchroniseren met je Git-repository volgens het GitOps-principe.

# Bronnen

- https://www.youtube.com/watch?v=X5W_706-jSY
- ChatGPT