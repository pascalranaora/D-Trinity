# 🛡️ Trinity : La Trinité Décentralisée

*Authors: [Pascal Ranoroarijaona] — Open Source under CC-BY-SA 4.0* Scroll Down for English Version

https://github.com/user-attachments/assets/39ceb92b-8bbc-44ef-ad27-9601bc21f942

Bienvenue sur **Trinity**. Ce portail souverain permet de sceller l'information dans l'éternité numérique. Il combine trois forces décentralisées pour créer une preuve de vérité universelle.

**Zéro serveur central. Zéro tiers de confiance. 100% Client-Side. La vérité par les mathématiques.**


Accès à l'outil : https://pascalranoroarijaona.github.io/Trinity
---

## 💡 Le Concept : La Trinité de la Confiance

Trinity repose sur trois piliers cryptographiques infaillibles :

1. **Le Quoi (Intégrité) :** L'empreinte locale `SHA-256`. 
2. **Le Qui (Identité) :** Le protocole `Nostr`. 
3. **Le Quand (Temps) :** Le protocole `OpenTimestamps` ancré sur `Bitcoin`.

![La Trinité de la Confiance](https://github.com/pascalranaora/D-Trinity/blob/main/img/trinity.png)

---

## 🟣 1. L'Identité avec Nostr : Qu'est-ce que Nostr et comment créer son identité ?

![Nostr - L'identité numérique souveraine](https://github.com/pascalranaora/D-Trinity/blob/main/img/nostrillustration.png)

Si vous n'avez jamais entendu parler de Nostr ou de cryptographie, pas de panique. C'est beaucoup plus simple qu'il n'y paraît.

### 1. Qu'est-ce que Nostr ?
[Nostr](https://nostr.com/) n'est pas une entreprise (comme Twitter ou Google ou Facebook). C'est un **protocole public** et libre (comme l'email). Il n'y a pas de PDG, pas de serveurs centraux, et personne ne peut censurer ou supprimer votre compte. Il s'agit d'un réseau social ouvert, décentralisé et résistant à la censure.

Ne reposant sur aucun serveur central de confiance, il est résilient ; basé sur des clés et des signatures cryptographiques, il est inviolable ; n'utilisant pas de techniques P2P, il fonctionne.

Sur Nostr, vous ne demandez pas la permission d'exister à une entreprise. Vous ne subissez pas un algorithme dans votre Feed. Votre identité est littéralement générée par une équation mathématique sur votre propre ordinateur. Vous **possédez** votre compte de manière absolue. Vous regardez le contenu que vous voulez voir.

### 2. Les Deux Clés (Le principe fondamental)
Au lieu d'un duo classique "Email / Mot de passe", la création d'une identité Nostr génère deux "clés" (qui ressemblent à de longues suites de lettres et de chiffres) :

* **La Clé Publique (commence par `npub...`) :** C'est votre nom d'utilisateur public. C'est ce que vous partagez avec le monde pour qu'on vous trouve, et c'est ce que notre portail utilise pour prouver que c'est bien vous l'auteur du document.
* **La Clé Privée (commence par `nsec...`) :** C'est votre secret le plus absolu. **Ne la donnez JAMAIS à personne, et ne la tapez jamais sur un site web.** C'est elle qui permet d'apposer la signature mathématique sur vos documents. 
    * *⚠️ Attention : Si vous perdez cette clé, il n'y a pas de bouton "Mot de passe oublié". Sauvegardez-la précieusement !*

### 3. Créer son identité en 2 minutes avec nos2x (Le Coffre-Fort)
Pour utiliser notre portail de scellement en toute sécurité, vous ne devez jamais taper votre clé privée sur la page web. Vous devez la ranger dans une extension de navigateur minimaliste et open-source qui fera office de "coffre-fort" (norme NIP-07).

1. **Installez l'extension :** Sur votre navigateur (Chrome, Brave, Chromium), téléchargez l'extension gratuite **[nos2x](https://github.com/fiatjaf/nos2x)**.
2. **Générez votre identité :** Cliquez sur l'icône de l'extension nos2x et choisissez de générer une nouvelle paire de clés (Generate).
3. **Mettez votre secret à l'abri :** L'extension va vous révéler votre clé privée (`nsec...`). Copiez-la immédiatement en lieu sûr (gestionnaire de mots de passe, papier).
4. **C'est terminé !** Votre navigateur est maintenant équipé de votre identité souveraine. L'extension signera silencieusement vos documents lorsque vous l'autoriserez.

---

## 🧡 2. Le Temps avec OpenTimestamps (OTS)

![L'Ancrage Bitcoin](https://github.com/pascalranaora/D-Trinity/blob/main/img/antiautodafe.png)

Si Nostr prouve **Qui** a signé, OpenTimestamps prouve **Quand** le document existait. 

### Qu'est-ce qu'OpenTimestamps ?
OpenTimestamps est un protocole qui utilise la puissance de calcul colossale du réseau **Bitcoin** comme une "horloge universelle" infalsifiable. 

### Pourquoi Bitcoin ?
Pour prouver qu'un document existait à une date précise, on pourrait demander à un notaire ou à un serveur web. Mais un notaire peut mentir, et un serveur peut être piraté pour changer sa date système. 
**Bitcoin est différent :** pour modifier une date dans la blockchain Bitcoin, il faudrait dépenser des milliards de dollars en électricité, ce qui rend toute falsification physiquement impossible. Bitcoin est l'ancre de réalité la plus solide jamais créée par l'homme.

### Comment ça marche (sans vous coûter un centime) ?
1. **Le Hash :** Notre outil prend l'empreinte de votre fichier (32 octets).
2. **L'Arbre de Merkle :** Cette empreinte est combinée avec des milliers d'autres dans une structure mathématique appelée "Arbre de Merkle".
3. **L'Ancrage :** Seule la racine de cet arbre (un code unique représentant des milliers de documents) est écrite dans la blockchain Bitcoin. 
4. **Le fichier .ots :** C'est votre reçu. Il contient le "chemin mathématique" qui prouve que votre document fait partie de cette racine enregistrée sur Bitcoin.

**Note :** Le scellement sur Bitcoin n'est pas instantané. Il faut attendre qu'un "bloc" soit miné (environ toutes les 10 minutes à quelques heures selon la congestion). Votre preuve devient "absolue" une fois confirmée par le réseau.


### 💻 Utilisation en Local (Self-Hosting)
Si vous téléchargez le code source pour utiliser l'outil hors de la version web hébergée, un simple double-clic sur le fichier `dtrinity.html` bloquera l'extension Nostr (sécurité liée aux fichiers `file:///`).

Pour l'utiliser en local, vous devez servir la page via un mini-serveur HTTP :
1. Ouvrez un terminal dans le dossier du projet.
2. Lancez la commande suivante (Python requis) :
   ```bash
   python -m http.server 8000
3. Ouvrez votre navigateur et accédez à : http://localhost:8000/index.html
---

## 🛠️ Prérequis pour l'utilisation

Trinity est une application purement statique. Aucune donnée n'est envoyée à un serveur central.

* **Pour le Créateur (Scellement) :** Un navigateur web moderne et l'extension Nostr **nos2x** configurée avec votre clé.
* **Pour le Lecteur (Audit) :** Un simple navigateur web suffit. Aucune extension ou installation n'est requise. Le code tourne 100% localement sur votre machine.

---

## ✍️ Guide 1 : Comment Sceller un Document (Étape 1 & 2)

*Ce processus génère vos preuves mathématiques. Votre fichier original ne quitte jamais votre ordinateur. L'outil ne lit que son empreinte.*

**Étape 1 : Le Scellement Initial**
1. Allez sur l'onglet **1. SCELLEMENT**.
2. Cliquez sur **Choisir un fichier** et sélectionnez le document à protéger (PDF, MP4, code source, etc.).
3. Cliquez sur **Lancer le Scellement Initial**. L'outil interrogera les calendriers mondiaux.
4. La fenêtre de votre extension nos2x va s'ouvrir. Autorisez la signature mathématique de l'empreinte.
5. Téléchargez les deux fichiers générés : le Certificat (`.json`) et la Preuve Temporelle en attente (`.ots`).

**Étape 2 : La Finalisation (L'Ancrage)**
1. Attendez que le réseau Bitcoin traite la demande (de quelques minutes à 24h).
2. Allez sur l'onglet **2. FINALISATION (OTS)**.
3. Glissez votre fichier `.ots` en attente.
4. Cliquez sur **Vérifier & Finaliser l'Ancrage**. Trinity ira chercher les preuves de minage.
5. Si l'ancrage est confirmé, téléchargez votre preuve absolue : le fichier `_confirm_final.ots`.

*Astuce : Distribuez toujours votre document original accompagné de son `.json` et de son `_confirm_final.ots`.*

---

## 🔍 Guide 2 : Comment Auditer un Document (Étape 3)

Vous avez reçu un fichier et vous souhaitez vérifier de manière absolue qui en est l'auteur et s'il n'a pas été modifié ? Laissez les mathématiques vérifier pour vous, sans aucune connexion serveur requise.

1. Allez sur l'onglet **3. AUDIT COMPLET**.
2. Importez les 3 fichiers que l'auteur vous a fournis :
   * **1. Le document original** (ex: `manuscrit.pdf`).
   * **2. Le certificat d'identité** (ex: `manuscrit.provenance.json`).
   * **3. La preuve temporelle finale** (ex: `manuscrit_confirm_final.ots`).
3. Cliquez sur **Lancer l'Audit de Vérité**.
4. Le rapport s'affiche instantanément :
   * Si les 3 piliers sont au vert ✅, le document est pur, la signature est authentique (le profil de l'auteur s'affiche), et l'ancrage Bitcoin est validé localement.
   * Si une ligne est au rouge ❌, le document a été falsifié, usurpé, ou la preuve est incomplète.

![Signature](https://github.com/pascalranaora/D-Trinity/blob/main/img/schnorrsig.png)


# 🛡️ Trinity: The Decentralized Trinity

Welcome to **Trinity**. This sovereign portal allows you to seal information into digital eternity. It combines three decentralized forces to create a universal proof of truth.

**Zero central servers. Zero trusted third parties. 100% Client-Side. Truth through mathematics.**

Access the tool: https://pascalranaora.github.io/Trinity
---

## 💡 The Concept: The Trinity of Trust

Trinity relies on three infallible cryptographic pillars:

1. **The What (Integrity):** The local `SHA-256` fingerprint. 
2. **The Who (Identity):** The `Nostr` protocol. 
3. **The When (Time):** The `OpenTimestamps` protocol anchored to `Bitcoin`.

![The Trinity of Trust](https://github.com/pascalranaora/D-Trinity/blob/main/img/trinity.png)

---

## 🟣 1. Identity with Nostr: What is Nostr and how to create your identity?

![Nostr - Sovereign Digital Identity](https://github.com/pascalranaora/D-Trinity/blob/main/img/nostrillustration.png)

If you have never heard of Nostr or cryptography, don't panic. It is much simpler than it looks.

### 1. What is Nostr?
[Nostr](https://nostr.com/) is not a company (like Twitter, Google, or Facebook). It is a **public and open protocol** (just like email). There is no CEO, no central servers, and no one can censor or delete your account. It is an open, decentralized, and censorship-resistant social network.

Because it does not rely on any central trusted server, it is resilient; built on cryptographic keys and signatures, it is tamper-proof; and avoiding complex P2P overhead, it just works.

On Nostr, you do not ask a corporation for permission to exist. You do not suffer through an algorithm dictating your Feed. Your identity is literally generated by a mathematical equation on your own computer. You absolutely **own** your account. You see only the content you want to see.

### 2. The Two Keys (The Fundamental Principle)
Instead of a classic "Email / Password" duo, creating a Nostr identity generates two "keys" (which look like long strings of letters and numbers):

* **The Public Key (starts with `npub...`):** This is your public username. It is what you share with the world so people can find you, and it is what our portal uses to prove that you are indeed the author of the document.
* **The Private Key (starts with `nsec...`):** This is your absolute secret. **NEVER give it to anyone, and never type it directly into a website.** This key is what allows you to apply the mathematical signature to your documents. 
    * *⚠️ Warning: If you lose this key, there is no "Forgot Password" button. Back it up safely!*

### 3. Create your identity in 2 minutes with nos2x (The Vault)
To use our sealing portal securely, you should never type your private key into the web page. You must store it in a minimalist, open-source browser extension that acts as a "vault" (NIP-07 standard).

1. **Install the extension:** On your browser (Chrome, Brave, Chromium), download the free **[nos2x](https://github.com/fiatjaf/nos2x)** extension.
2. **Generate your identity:** Click on the nos2x extension icon and choose to generate a new key pair (**Generate**).
3. **Keep your secret safe:** The extension will reveal your private key (`nsec...`). Copy it immediately to a safe place (password manager, paper).
4. **You're all set!** Your browser is now equipped with your sovereign identity. The extension will silently sign your documents whenever you authorize it.

---

## 🧡 2. Time with OpenTimestamps (OTS)

![The Bitcoin Anchor](https://github.com/pascalranaora/D-Trinity/blob/main/img/antiautodafe.png)

If Nostr proves **Who** signed it, OpenTimestamps proves **When** the document existed. 

### What is OpenTimestamps?
OpenTimestamps is a protocol that uses the colossal computing power of the **Bitcoin** network as an unforgeable "universal clock". 

### Why Bitcoin?
To prove a document existed at a specific date, you could ask a notary or a web server. But a notary can lie, and a server can be hacked to alter its system time. 
**Bitcoin is different:** to alter a date in the Bitcoin blockchain, one would have to spend billions of dollars in electricity, making any falsification physically impossible. Bitcoin is the strongest anchor of reality ever created by humankind.

### How it works (without costing you a penny)
1. **The Hash:** Our tool takes the fingerprint of your file (32 bytes).
2. **The Merkle Tree:** This fingerprint is combined with thousands of others in a mathematical structure called a "Merkle Tree".
3. **The Anchoring:** Only the root of this tree (a unique code representing thousands of documents) is written into the Bitcoin blockchain. 
4. **The .ots file:** This is your receipt. It contains the "mathematical path" proving that your document is part of that specific root registered on Bitcoin.

**Note:** Sealing on Bitcoin is not instantaneous. You have to wait for a "block" to be mined (ranging from 10 minutes to a few hours depending on network congestion). Your proof becomes "absolute" once confirmed by the network.

### 💻 Local Use (Self-Hosting)
If you download the source code to use the tool outside of the hosted web version, simply double-clicking the `dtrinity.html` file will block the Nostr extension (a security restriction related to browser `file:///` protocols).

To use it locally, you must serve the page via a local HTTP server:
1. Open a terminal in the project folder.
2. Run the following command (Python required):
   ```bash
   python -m http.server 8000
   ```
3. Open your browser and navigate to: http://localhost:8000/dtrinity.html

---

## 🛠️ Prerequisites for Use

Trinity is a purely static application. No data is ever sent to a central server.

* **For the Creator (Sealing):** A modern web browser and the **nos2x** Nostr extension configured with your key.
* **For the Reader (Auditing):** A simple web browser is enough. No extension or installation required. The code runs 100% locally on your machine.

---

## ✍️ Guide 1: How to Seal a Document (Steps 1 & 2)

*This process generates your mathematical proofs. Your original file never leaves your computer. The tool only reads its hash fingerprint.*

**Step 1: Initial Sealing**
1. Go to the **1. SEALING** tab.
2. Click on **Choose File** and select the document to protect (PDF, MP4, source code, etc.).
3. Click on **Launch Initial Sealing**. The tool will query global calendars.
4. Your nos2x extension window will pop up. Authorize the mathematical signature of the hash.
5. Download the two generated files: the Certificate (`.json`) and the pending Time Proof (`.ots`).

**Step 2: Finalization (Anchoring)**
1. Wait for the Bitcoin network to process the request (from a few minutes to 24 hours).
2. Go to the **2. FINALIZATION (OTS)** tab.
3. Drag and drop your pending `.ots` file.
4. Click on **Verify & Finalize Anchoring**. Trinity will fetch the mining proofs.
5. If the anchoring is confirmed, download your absolute proof: the `_confirm_final.ots` file.

*Tip: Always distribute your original document accompanied by its `.json` and `_confirm_final.ots` files.*

---

## 🔍 Guide 2: How to Audit a Document (Step 3)

Have you received a file and want to verify with absolute certainty who wrote it and that it hasn't been modified? Let mathematics do the verifying for you, with no server connection required.

1. Go to the **3. COMPLETE AUDIT** tab.
2. Import the 3 files provided by the author:
   * **1. The original document** (e.g., `manuscript.pdf`).
   * **2. The identity certificate** (e.g., `manuscript.provenance.json`).
   * **3. The final time proof** (e.g., `manuscript_confirm_final.ots`).
3. Click on **Launch Truth Audit**.
4. The report appears instantly:
   * If all 3 pillars are green ✅, the document is untampered, the signature is authentic (the author's profile will be displayed), and the Bitcoin anchoring is validated locally.
   * If any line is red ❌, the document has been altered, impersonated, or the proof is incomplete.

![Signature](https://github.com/pascalranaora/D-Trinity/blob/main/img/schnorrsig.png)
