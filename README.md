  # evisions — internal code & automation                                                                         
                                                                                                                  
  This GitHub account hosts internal tools, documentation, and automation built by the **evisions** agency for our
   own team and (occasionally) our clients. Most repositories here are **private**.                               
                                                                                                                  
  ## Repo naming convention                                                                                       
                                                                                                                  
  All repos follow the pattern:                                                                                   
                                                                                                                  
  -                                                                                                               
                                                                                                                  
  **`<scope>`** is one of:                                                                                        
                                                                                                                  
  | Scope | For |                                                                                                 
  |---|---|                                                                                                       
  | `hr` / `scs` / `ppc` / `seo` / `krea` / `ux` / `analytics` / `pr` / `c-level` / `ai` | Department-specific
  tool or project |                                                                                               
  | `shared` | Cross-team resources used across the agency |
  | `client` | Client-facing work — literal `client-` prefix, **never the client's actual name** (keeps client    
  relationships private) |                                                                                        
                                                                                                                  
  **`<descriptor>`** is the product or topic name. **Do not include `evisions-` in the descriptor** — the account 
  name already says it; avoid duplication.
                                                                                                                  
  ### Examples    

  - `hr-vibes` — HR internal survey platform                                                                      
  - `scs-sales-dashboard` — SCS sales reporting dashboard                                           
                                                                                                                  
  ## House rules                                                                                                  
                                                                                                                  
  - **No keys or secrets on GitHub, ever.** This includes API tokens, OAuth secrets, service-account JSON keys,   
  database passwords, SSH keys. Verify `.gitignore` covers `.env*`, `*-sa.json`, `*.key`, `*.pem`, `rclone.conf`
  before the first push. If a secret ever lands in history, rotate it *and* purge history (`git filter-repo` /    
  BFG) before making the repo accessible to anyone else.
  - **Documentation expected.** Every shipped app should have a `README.md` and a `CLAUDE.md` at root, plus a
  `docs/` folder covering runbook, env reference, user guide (if applicable), and security notes. Significant     
  design decisions go in `docs/adr/` as Architecture Decision Records.
  - **Bus-factor rule.** A repo for evisions work is "shipped" only when `ai-evisions` has access to it. You can  
  either:                                                                                                         
    - keep ownership on your personal GitHub account and add `ai-evisions` as a collaborator, **or**
    - transfer the repo to `ai-evisions` entirely (encouraged for fully centralized work, not required).          
                                                                                                                  
    Either works — but neither is optional. Personal-only repos aren't discoverable or recoverable if you leave.  
  - **Pull requests + CI before merging.** Work on a branch and open a pull request; never push or commit directly to `main`. If the repo has CI (GitHub Actions), its checks must pass before merging — no merging on red. On plans that allow it (GitHub Pro/Team for private repos) this is enforced server-side by a branch-protection rule on `main` (require a PR + passing CI, block force-pushes and direct pushes); until then it is an honored team convention.
  - **Data-security incidents**: contact **Petr Hlaváč** (COO, evisions).                                         
                                                                                                                  
  ## Tooling      
                                                                                                                  
  Apps here are typically scaffolded with an internal **`/appdoc`** skill (Claude Code) that creates a consistent 
  documentation structure. Reach out to the AI team if you're starting a new project and want the scaffolding.
                                                                                                               
