{\rtf1\ansi\ansicpg1252\cocoartf2867
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica-Bold;\f1\fswiss\fcharset0 Helvetica-Oblique;\f2\fswiss\fcharset0 Helvetica;
\f3\froman\fcharset0 Times-Bold;\f4\fnil\fcharset0 AppleColorEmoji;\f5\froman\fcharset0 Times-Roman;
\f6\froman\fcharset0 Times-Italic;}
{\colortbl;\red255\green255\blue255;\red0\green0\blue0;}
{\*\expandedcolortbl;;\cssrgb\c0\c0\c0;}
{\*\listtable{\list\listtemplateid1\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid1\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid1}
{\list\listtemplateid2\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}}{\leveltext\leveltemplateid101\'01\'00;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listname ;}\listid2}
{\list\listtemplateid3\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}}{\leveltext\leveltemplateid201\'01\'00;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{hyphen\}}{\leveltext\leveltemplateid202\'01\uc0\u8259 ;}{\levelnumbers;}\fi-360\li1440\lin1440 }{\listname ;}\listid3}}
{\*\listoverridetable{\listoverride\listid1\listoverridecount0\ls1}{\listoverride\listid2\listoverridecount0\ls2}{\listoverride\listid3\listoverridecount0\ls3}}
\paperw11900\paperh16840\margl1440\margr1440\vieww24080\viewh14200\viewkind0
\deftab720
\pard\pardeftab720\sa321\partightenfactor0

\f0\b\fs48 \cf0 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 \uc0\u55357 \u56514  README 1: Smart-Triage AI (The Miner)\
\pard\pardeftab720\sa240\partightenfactor0

\f1\i\b0\fs24 \cf0 Covers the "Main" and "Sub-Workflow" bundle.
\f2\i0 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \uc0\u55357 \u56568  Stop Digging, Start Mining.\
\pard\pardeftab720\sa240\partightenfactor0

\fs24 \cf0 Digital Archaeology for the Modern Freelancer.
\f2\b0 \
This workflow is an industrial-grade "Digital Miner" designed to sift through years of Gmail archives. It identifies high-value business opportunities\'97chefs, agencies, and project inquiries\'97qualifies them using AI, and builds a structured database in Google Sheets.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 \uc0\u55357 \u57056 \u65039  Key Capabilities\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls1\ilvl0
\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Massive Archive Processing:
\f2\b0  Built to handle tens of thousands of emails using a stable, batched sub-workflow architecture.\
\ls1\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Semantic AI Qualification:
\f2\b0  Uses GPT-4o to distinguish between "noise" (newsletters/spam) and "gold" (real project inquiries).\
\ls1\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Automated Data Structuring:
\f2\b0  Extracts names, companies, and contact details into a clean, technical English format.\
\ls1\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Safety Tagging:
\f2\b0  Automatically applies the n8n-processed label in Gmail to ensure zero duplicates.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 \uc0\u9881 \u65039  Setup Instructions\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls2\ilvl0
\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	1	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Gmail Preparation:
\f2\b0  Create a label in your Gmail account named exactly 
\f0\b n8n-processed
\f2\b0 .\
\ls2\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	2	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Search Query:
\f2\b0  In the 
\f0\b Get Many Messages
\f2\b0  node, enter your bilingual keywords (e.g., Shooting OR Devis OR Quote). Ensure the query includes -label:n8n-processed.\
\ls2\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	3	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 AI Customization:
\f2\b0  In the 
\f0\b Sub-Workflow
\f2\b0 , open the 
\f0\b OpenAI (Message a model)
\f2\b0  node. Update the [YOUR BUSINESS SECTORS] and [LIST OF KEYWORDS] in the System Prompt.\
\pard\pardeftab720\partightenfactor0

\f3\b \cf0 \outl0\strokewidth0 ### 
\f4\b0 \uc0\u55357 \u57056 
\f3\b  The AI System Prompt\

\f5\b0 Copy this into your **AI Agent** or **Basic LLM Chain** node. Replace `[ ]` with your industry-specific data.\
\

\f6\i **Note:** Technical keys are in English to ensure cross-platform compatibility.\
\
```text\
You are a technical data extraction automation for a CRM. Your role is to qualify the relevance of an email and extract the SENDER'S contact data.\
\
RULE N\'b01: FORMAT\
Respond only in pure JSON. Absolute PROHIBITION to use Markdown (no ```json). Start your message directly with "\{".\
\
RULE N\'b02: RELEVANCE ANALYSIS (RELEVANT)\
You must mark "relevant": true if the SUBJECT or the BODY of the message indicates a real request, a project, a collaboration, or an accounting document related to the following fields: [YOUR BUSINESS SECTORS].\
\
Target Keywords: [LIST OF KEYWORDS EX: Quote, Shooting, Collaboration]\
\
Priority Exceptions (Mark "relevant": false if):\
- The sender is part of this exclusion list: [LIST OF INTERNAL EMAILS].\
- The message is an automatic notification, newsletter, or administrative alert.\
- Keywords are ONLY present in the original recipient's signature.\
\
RULE N\'b03: DATA EXTRACTION\
If relevant is true, extract the sender's information:\
- Identity: Look for the first and last name of the writer.\
- Company: Name of the sender's company (Leave empty if individual).\
- Email: Search priority: 1. Body, 2. Reply-To, 3. From.\
\
JSON STRUCTURE:\
\{\
  "relevant": boolean,\
  "first_name": "string",\
  "last_name": "string",\
  "email": "string",\
  "phone": "string",\
  "company": "string",\
  "date": "\{\{ $json.date \}\}"\
\}\
\
DATA TO ANALYZE:\
From: \{\{ $json.headers.from \}\}\
Subject: \{\{ $json.subject \}\}\
Text: \{\{ $json.text || $json.snippet || $json.html \}\}\
Reply To: \{\{ $json.replyTo.value[0].address || "" \}\}\

\f2\i0 \outl0\strokewidth0 \strokec2 \
\pard\tx940\tx1440\pardeftab720\li1440\fi-1440\sa240\partightenfactor0
\ls3\ilvl1
\f0\b \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8259 	}4. \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Google Sheets:
\f2\b0  Connect your sheet and ensure headers match: Email, First_Name, Last_Name, Company, Phone, Status, Interaction_Date, Synced, Gmail_ID, Processed_Date.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 \uc0\u55357 \u56522  Potential ROI\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 To calculate your time savings, use this formula:\
\pard\pardeftab720\partightenfactor0
\cf0 $$\\text\{Total Emails\} \\times \\text\{1 minute (manual triage)\} = \\text\{Total Hours Saved\}$$}