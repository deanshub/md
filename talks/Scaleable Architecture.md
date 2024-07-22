
# Scalable architecture
## *what is it and how to do it right*

---

# [Dean Shub](x.com/deanshub)
VP R&D @ OpenWeb

---

# Agenda

- ⁠Scaling stories from real companies
- Identifying bottlenecks (interactive session)
- The basics: Horizontal and vertical scaling\ microservices\ languages\ DBs\ ...
- Simple app from basic to super scale
- ⁠Considering the right elements (What not to do)

---

# Scaling stories
- Sisense %%  Multi Build & Partial build %%
- Wix %% Module Federation %%
- OpenWeb %% Microservices A\C %%
- Wiki\Netflix %% Elastic %%
- Rabbitmq\Whatsapp %% Erlang %%
- Google %% k8s %%

%% what is scaling? not just a system needs scale, monitoring logging  and team solutions %%

---

Let's solve a scale issue

%% 
1. I explain a system, and that the users are upset of how slow it is: Fun Run - Web Game
2. Identify (ask questions and seek the biggest bottleneck)
3. Diagnose -> Track -> Fix 
4. web, react + go + auth service + socring service
5. Summarize
%%

---

Basic method of solving any scale issue
1. Identify & Diagnose
2. Monitor
3. Plan & Suggest
4. Change & Asses
5. Iterate (got to 1)

---

# Break

---
# The Basics

- Stateless vs Stateful
- Horizontal and vertical scaling
- Microservices
- Communication (API, GQL, Message Q, RPC)
- Languages (go, node, rust)
- DBs (s3, elastic, graph, nosql, sql)
- Caching - varnish\ CDN \ redis \ nginx \ cady (ML guesstimations)

---
# Super Scale your SaaS

%% 
- Networking
- DNS
- loadbalancer
- CDN
- Cache
- API GW
- Compute
- MQ
- DB
- Multi region
- Recovery
- Security
- Monitoring
%%

---

# A time and a place for everything

Considering the right elements (What not to do)
- ML
- Do the simplest thing that solves the problem (problem should describe the amount of users)
- Scaling is not just about system - Conway law
- use the tools you already have (opensource, org, techleads)
- Multiple ways to solve the same problem
- Resources (Money, devs, QA, support), workarounds

---
### Random links
- https://samwho.dev/load-balancing/
- https://s3.amazonaws.com/OM-SHARE/AWSOFA-Print-27x240.pdf