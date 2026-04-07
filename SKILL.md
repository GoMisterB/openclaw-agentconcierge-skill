name: agentconcierge                                      
  description: Find and recommend AI agents for any workflow using AgentConcierge. Searches 9,800+ agents and returns 5 ranked
  recommendations with match scores.                                                                                                     
  version: 1.0.0
  license: MIT-0                                                                                                                         
  metadata:                                                 
    emoji: "🤖"
    openclaw:
      requires:
        bins:
          - curl
  ---

  # AgentConcierge

  Find the best AI agents for any workflow. Searches 9,800+ agents across OpenAI, Anthropic, n8n, HuggingFace, Zapier, and more.         
   
  ## When to Use                                                                                                                         
  - User asks which AI agents or tools to use for their job or task
  - User wants AI recommendations for a specific role or pain point
                                                                                                                                         
  ## API Call
                                                                                                                                         
  ```bash                                                   
  curl -s -X POST https://agentconcierge.io/api/recommend \
    -H "Content-Type: application/json" \
    -d '{"role":"ROLE","painPoint":"PAIN","tools":"TOOLS","budget":"BUDGET","teamSize":"TEAM"}'
                                                                                                                                         
  Replace ROLE and PAIN with what the user told you. Ask for them if missing.
                                                                                                                                         
  Present Results Like This                                 

  🤖 Top matches for your profile:

  1. **Agent Name** — 94% match                                                                                                          
     One line description.
     ✓ Match reason 1                                                                                                                    
     ✓ Match reason 2                                       
     💰 $19/mo — https://url

  Errors

  - 429: rate limited — wait 60 seconds and retry                                                                                        
  - 400: missing role or painPoint — ask the user
  - 500: tell user to visit https://agentconcierge.io/search                                                                             
                                                            
  Once that's committed, let me know and I'll walk you through the ClawHub publish step.
