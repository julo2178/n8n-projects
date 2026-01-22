{\rtf1\ansi\ansicpg1252\cocoartf2867
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica-Bold;\f1\fnil\fcharset0 AppleColorEmoji;\f2\fswiss\fcharset0 Helvetica;
\f3\froman\fcharset0 Times-Bold;\f4\froman\fcharset0 Times-Roman;}
{\colortbl;\red255\green255\blue255;\red0\green0\blue0;}
{\*\expandedcolortbl;;\cssrgb\c0\c0\c0;}
\paperw11900\paperh16840\margl1440\margr1440\vieww21200\viewh13440\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\b\fs48 \cf0 # 
\f1\b0 \uc0\u55357 \u56580 
\f0\b  Smart-Sync AI: CRM Synchronization & Stability\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f2\b0\fs24 \cf0 \
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\b\fs36 \cf0 ## 
\f1\b0 \uc0\u55357 \u56534 
\f0\b  Description (English)
\f2\b0\fs24 \
\
This workflow is the "Refiner" that bridges your Google Sheet database with your marketing ecosystem (Brevo). It is designed with industrial-grade stability to process up to 20,000+ leads without hitting server timeouts or memory crashes.\
\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\b \cf0 **Key Capabilities:**\

\f2\b0 * **Batch Orchestration:** Uses a "Split-in-Batches" logic to process leads in manageable groups (e.g., 10 at a time), crucial for high-volume freelancers.\
* **Smart Segmentation:** Automatically detects if a contact is a "Prospect" or "Client" and routes them to the correct marketing list for tailored campaigns.\
* **Feedback Loop:** Updates your Google Sheet with `Synced: Yes`, providing a clear audit trail.\
* **API Efficiency:** Strips unnecessary payloads before transmission to keep data lightweight.\
\
---\
\

\f0\b ### \uc0\u9881 \u65039  Node-by-Node Configuration\

\f2\b0 \

\f0\b | Node Name | What to Configure | Node Note (Inside n8n) |\

\f2\b0 | :--- | :--- | :--- |\
| **Get Rows** | Document: Empty (User selection). Filter: `Synced` is empty OR `Synced` equals `No`. | **Note:** Select your lead sheet. Fetches unsynced leads only. |\
| **Split-Batches** | Batch Size: `10`. | **Note:** ESSENTIAL for stability. Processes in small groups. |\
| **HTTP Request** | URL: Brevo API. Auth: Predefined. | **Note:** Change list IDs 6 and 8 in the JSON body to match your Brevo lists. |\
| **Update Row** | Operation: `Update`. Lookup: `Email`. | **Note:** Select your sheet. Sets `Synced` column to `Yes` after successful sync. |\
\

\f0\b ### \uc0\u55357 \u56522  Google Sheet Template (Technical English)\

\f2\b0 `Email, First_Name, Last_Name, Company, Phone, Status, Interaction_Date, Synced, Gmail_ID, Processed_Date`\
\

\f0\b ### 
\f1\b0 \uc0\u9881 \u65039 
\f0\b  Stability Configuration: The "Batch" Logic\

\f2\b0 To process massive volumes without server crashes:\
1. **The Retrieval:** Fetch 100 rows per execution.\
2. **The Split:** Use a **Split-in-Batches** node to process items in groups of 10.\
3. **The Buffer:** A 5-minute Cron trigger provides "breathing room" for the API.\
4. **Data Pruning:** The "Edit Fields" node removes heavy HTML code immediately after extraction to save memory.\
\
\
\pard\pardeftab720\sa319\partightenfactor0

\f3\b \cf0 \expnd0\expndtw0\kerning0
### 
\f1\b0 \uc0\u55357 \u56826 
\f3\b  Technical Data Mapping\
To ensure the data is correctly transferred from the AI's JSON output to your Google Sheet, use an **Edit Fields** (Set) node or the **Google Sheets** node with the following expressions.\
| Google Sheet Header | n8n Expression (JSON Logic) |\
| :--- | :--- |\

\f4\b0 | **Email** | `\{\{ JSON.parse($json.output[0].content[0].text).email ?? "" \}\}` |\
| **First_Name** | `\{\{ JSON.parse($json.output[0].content[0].text).first_name ?? "" \}\}` |\
| **Last_Name** | `\{\{ JSON.parse($json.output[0].content[0].text).last_name ?? "" \}\}` |\
| **Company** | `\{\{ JSON.parse($json.output[0].content[0].text).company ?? "" \}\}` |\
| **Phone** | `\{\{ JSON.parse($json.output[0].content[0].text).phone ?? "" \}\}` |\
| **Status** | `Lead` (Static Value) |\
| **Interaction_Date** | `\{\{ JSON.parse($json.output[0].content[0].text).date ?? "" \}\}` |\
| **Synced** | `No` (Static Value) |\
| **Gmail_ID** | `\{\{ $node["Gmail Trigger"].json["id"] \}\}` |\
| **Processed_Date** | `\{\{ $now.format('dd/MM/yyyy HH:mm:ss') \}\}` |
\f2 \kerning1\expnd0\expndtw0 \
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\b \cf0 ### 
\f1\b0 \uc0\u55357 \u56481 
\f0\b  ROI Calculation
\f2\b0 \
$$\\text\{20,000 emails\} \\times \\text\{1 minute/email\} = \\text\{333.33 hours saved\}$$\
\
\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\b\fs36 \cf0 ## 
\f1\b0 \uc0\u55357 \u56534 
\f0\b  Description (Fran\'e7ais)
\f2\b0\fs24 \
Ce workflow est le "Synchroniseur". Il r\'e9cup\'e8re les prospects de votre Google Sheet et les synchronise avec vos outils marketing (ex: Brevo). Il est optimis\'e9 pour les volumes industriels (20 000+ leads).\
\
\
### 
\f1 \uc0\u9881 \u65039 
\f2  Configuration de Stabilit\'e9\
1. **Micro-Batching :** Le flux est divis\'e9 en petits lots de 10 pour \'e9viter les saturations m\'e9moire.\
2. **Nettoyage :** Suppression automatique du contenu HTML lourd apr\'e8s analyse pour garder un workflow fluide.\
3. **Synchronisation :** Segmentation automatique entre "Prospects" et "Clients Existants" avant l'envoi vers Brevo.\
\
---\
\
#### **Fran\'e7ais : Correspondance des Champs**\
Pour garantir que les donn\'e9es soient correctement transf\'e9r\'e9es de l'IA vers votre Google Sheet, utilisez un n\'9cud **Edit Fields** avec les expressions suivantes.\
\
* **Cl\'e9s Anglaises :** Nous utilisons des en-t\'eates en anglais dans le Google Sheet pour une compatibilit\'e9 technique accrue.\
* **S\'e9curit\'e9 Anti-Erreur :** La syntaxe `?? ""` (Nullish Coalescing) est utilis\'e9e pour \'e9viter que le workflow ne s'arr\'eate si l'IA ne trouve pas d'information (ex: num\'e9ro de t\'e9l\'e9phone manquant).\
* **Filtrage :** Assurez-vous d'ajouter un n\'9cud **Filter** apr\'e8s l'IA pour ne traiter que les lignes o\'f9 `relevant` est \'e9gal \'e0 `true`.\
\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\b \cf0 **Contact :**
\f2\b0 \
Reach out for custom AI automation! / Contactez-moi pour vos besoins d'automatisation IA !}