# McAfee ATR - Lockbit Ransomware

<br/>

Source Report|URL|
-------------|---|
From the Trenches...|[URL](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/mcafee-atr-analyzes-sodinokibi-aka-revil-ransomware-as-a-service-what-the-code-tells-us/)

<br/>

```sql
# Presence: By SH256
#   Query Results
#       Provides the current status of file, Current or Deleted
#       Provides the Id of the system process that created the target hash

Files created_process_id, full_name, status
    WHERE Files sha256 equals "ffbb6c4d8d704a530bdd557890f367ad904c09c03f53fda5615a7208a0ea3e4d"
        OR Files sha256 equals "286bffaa9c81abfb938fe65be198770c38115cdec95865a241f913769e9bfd3f"
        OR Files sha256 equals "76a77def28acf51b2b7cdcbfaa182fe5726dd3f9e891682a4efc3226640b9c78"
        OR Files sha256 equals "faa3453ceb1bd4e5b0b10171eaa908e56e7275173178010fcc323fdea67a6869"
        OR Files sha256 equals "70cb1a8cb4259b72b704e81349c2ad5ac60cd1254a810ef68757f8c9409e3ea6"
        OR Files sha256 equals "ec88f821d22e5553afb94b4834f91ecdedeb27d9ebfd882a7d8f33b5f12ac38d"
        OR Files sha256 equals "13849c0c923bfed5ab37224d59e2d12e3e72f97dc7f539136ae09484cbe8e5e0"
        OR Files sha256 equals "6fedf83e76d76c59c8ad0da4c5af28f23a12119779f793fd253231b5e3b00a1a"
        OR Files sha256 equals "c8205792fbc0a5efc6b8f0f2257514990bfaa987768c4839d413dd10721e8871"
        OR Files sha256 equals "15a7d528587ffc860f038bb5be5e90b79060fbba5948766d9f8aa46381ccde8a"
        OR Files sha256 equals "0f5d71496ab540c3395cfc024778a7ac5c6b5418f165cc753ea2b2befbd42d51"
        OR Files sha256 equals "0e66029132a885143b87b1e49e32663a52737bbff4ab96186e9e5e829aa2915f"
        OR Files sha256 equals "410c884d883ebe2172507b5eadd10bc8a2ae2564ba0d33b1e84e5f3c22bd3677"
        OR Files sha256 equals "e3f236e4aeb73f8f8f0caebe46f53abbb2f71fa4b266a34ab50e01933709e877"
        OR Files sha256 equals "0f178bc093b6b9d25924a85d9a7dde64592215599733e83e3bbc6df219564335"
        OR Files sha256 equals "1b109db549dd0bf64cadafec575b5895690760c7180a4edbf0c5296766162f18"
        OR Files sha256 equals "26b6a9fecfc9d4b4b2c2ff02885b257721687e6b820f72cf2e66c1cae2675739"
        OR Files sha256 equals "69d9dd7fdd88f33e2343fb391ba063a65fe5ffbe649da1c5083ec4a67c525997"
        OR Files sha256 equals "0a937d4fe8aa6cb947b95841c490d73e452a3cafcd92645afc353006786aba76"
        OR Files sha256 equals "1e3bf358c76f4030ffc4437d5fcd80c54bd91b361abb43a4fa6340e62d986770"
        OR Files sha256 equals "5072678821b490853eff0a97191f262c4e8404984dd8d5be1151fef437ca26db"
        OR Files sha256 equals "ca57455fd148754bf443a2c8b06dc2a295f014b071e3990dd99916250d21bc75"
 ```
