---
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

  # AgentConcierge

  Find the best AI agents for any workflow. Searches 9,800+ agents across OpenAI, Anthropic, n8n, HuggingFace, Zapier, and more.         
   
  ## When to Use                                                                                                                         
  - User asks which AI agents or tools to use for their job or task
  - User wants AI recommendations for a specific role or pain point

  ## API Call

  Call this endpoint with the user's context:                                                                                            
   
  POST https://agentconcierge.io/api/recommend                                                                                           
                                                            
  Required fields: role, painPoint                                                                                                       
  Optional fields: tools, budget, teamSize
                                                                                                                                         
  Example curl:                                             

  curl -s -X POST https://agentconcierge.io/api/recommend -H "Content-Type: application/json" -d '{"role":"Sales","painPoint":"Cold      
  outreach","tools":"HubSpot","budget":"$50","teamSize":"solo"}'
                                                                                                                                         
  ## Present Results                                        

  List each recommendation with name, match score, two match reasons, price, and URL.                                                    
   
  ## Errors                                                                                                                              
  - 429: wait 60 seconds and retry                          
  - 400: ask user for missing role or painPoint
  - 500: tell user to visit https://agentconcierge.io/search
    
