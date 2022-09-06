# isabelle-parallel-corpus

This is the first release of the Isabelle Parallel Corpus (IPC).

The zip file expands to three objects:
- an index file (index.dat) that lists all data points in the corpus (520 Isabelle artefacts linked to their textual source and natural language statements). See below for a description of this file's format.
- The 'statements' folder with the statement sentences for each artefact. This folder is atomically indexed by the file 'entries.dat' for easier machine-readable access to the statement data.
- The 'pairs' folder, which contains an initial seed of 19 Isabelle-NL pairs. This folder is also automatically indexed by an 'entries.dat' file.
  Each pair is composed of three files:
  (a) A '*_statement.latex' file containing a copy of the natural language sentences of its statement.
  (b) A '*_proof.sentences' file containing the sentences of the proof. Each sentence in this file is separated by a <s id="x"></s> tag block.
  (c) A '*_isabelle.proof' file containing the raw Isabelle code for the artefact.
  
## The index.dat file

The main index file contains a header and is composed of the following fields:

- id: the annotation ID for the artefact.
- factkey: A unique key that identifies the Isabelle artefact.
- factname: The name of the Isabelle artefact.
- theory: The source theory of the Isabelle artefact.
- session: The Isabelle session the source theory belongs to.
- locale: The locale, if any, that the artefact belongs to.
- kind: The kind of the artefact (e.g., theorem, lemma, definition, etc).
- source: The title of the natural language resource from which the text for the proof comes from.
- source_type: The type of the natural language resource (e.g., book).
- source_url: A URL to the natural language resource.
