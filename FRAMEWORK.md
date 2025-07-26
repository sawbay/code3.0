# Components

## Models
```
// models
class Expense = Model.new({
  name: "Expense",
  fields: {
    id: "string",
    amount: "number",
    date: "date",
    description: "string",
  },
  validation: { ... }
});

const reactor = new Reactor({
  name: "INPUT_REACTOR",
  systemPrompt: "
    You receive create expense request in different formats. If it's
    - in text: extract information and create Expense model
    - in image: extract information using VisionReactor and create Expense model
    - in voice: extract information using AudioReactor and create Expense model
  ",
  models: [Expense],
});

const restTool = new Tool<RestfulAPI>();
restTool.endpoint({
  method: "POST",
  path: "expense/new",
});
const storageTool = new Tool<Storage>();


const agent2AgentTool = new Tool<A2A>();
agent2AgentTool.equipFor(reactor, reactor_specs);
agent2AgentTool.equipFor(reactor2, reactor2_specs);

```
