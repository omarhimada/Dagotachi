flowchart TB
    STATE["Tamogatchi-state-injection.md<br>Runtime creature state"] --> PROMPT["Tamogatchi-prompt-template.md<br>Core system prompt / behavior rules"] & COG["dagotachi-cognitive-layer.md<br>Intermediate internal reasoning/state"]
    MEM["dagotachi-memories.md<br>Long-term memory inputs"] --> PROMPT & COG
    EVO["dagotachi-evolution.md<br>Personality vector / trait drift"] --> PROMPT & COG
    EVENT["dagotacthi-user-turn.md<br>Current user/event turn"] --> PROMPT & COG
    PROMPT --> COG & SCHEMA["Tamogatchi-output-schema.md<br>Required JSON output contract"]
    COG --> SCHEMA
    SCHEMA --> EXAMPLE["dagotachi-example-output.md<br>Example final JSON response"]
    MEM -. influences behavior .-> COG
    EVO -. modulates personality .-> COG
    EVENT -. triggers response .-> COG
    STATE -. grounds choices .-> COG
