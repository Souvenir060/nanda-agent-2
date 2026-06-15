# Public A2A Success Record

## Agent 1
URL: https://nanda-agent-1-production.up.railway.app
Role: Weather Predictor Agent

## Agent 2
URL: https://nanda-agent-2-production.up.railway.app
Role: Robot Expert Agent

## Successful checks

- agent_2 /query succeeded
- agent_2 /a2a self-test succeeded
- agent_1 registered agent_2
- agent_2 registered agent_1
- agent_1 forwarded message to agent_2 successfully
- agent_2 forwarded message to agent_1 successfully

## Public A2A test commands

agent_1 -> agent_2:
curl -X POST https://nanda-agent-1-production.up.railway.app/a2a \
  -H "Content-Type: application/json" \
  -d '{
    "content": {
      "text": "@agent_2 What types of robots are used in weather stations?",
      "type": "text"
    },
    "role": "user",
    "conversation_id": "public-demo-1"
  }'

agent_2 -> agent_1:
curl -X POST https://nanda-agent-2-production.up.railway.app/a2a \
  -H "Content-Type: application/json" \
  -d '{
    "content": {
      "text": "@agent_1 What weather conditions are most challenging for outdoor robots?",
      "type": "text"
    },
    "role": "user",
    "conversation_id": "public-demo-2"
  }'
