graph TD
    README[README.md<br/>Project overview / intent]

    PROMPT[Tamogatchi-prompt-template.md<br/>Core system prompt / behavior rules]
    STATE[Tamogatchi-state-injection.md<br/>Runtime creature state]
    MEM[dagotachi-memories.md<br/>Long-term memory inputs]
    EVO[dagotachi-evolution.md<br/>Personality vector / trait drift]
    EVENT[dagotacthi-user-turn.md<br/>Current user/event turn]

    COG[dagotachi-cognitive-layer.md<br/>Intermediate internal reasoning/state]
    SCHEMA[Tamogatchi-output-schema.md<br/>Required JSON output contract]
    EXAMPLE[dagotachi-example-output.md<br/>Example final JSON response]

    README --> PROMPT
    README --> STATE
    README --> MEM
    README --> EVO
    README --> EVENT
    README --> SCHEMA
    README --> EXAMPLE
    README --> COG

    STATE --> PROMPT
    MEM --> PROMPT
    EVO --> PROMPT
    EVENT --> PROMPT

    STATE --> COG
    MEM --> COG
    EVO --> COG
    EVENT --> COG

    PROMPT --> COG
    PROMPT --> SCHEMA

    COG --> SCHEMA
    SCHEMA --> EXAMPLE

    MEM -.influences behavior.-> COG
    EVO -.modulates personality.-> COG
    EVENT -.triggers response.-> COG
    STATE -.grounds choices.-> COG
