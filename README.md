# spacelift-hello-world
 
A minimal Terraform config for a first Spacelift stack. No cloud account or
credentials required — it only uses the `random` provider to generate a
random pet name.
 
## How to use this with Spacelift
 
1. Create a new (empty) repo on GitHub, e.g. `spacelift-hello-world`.
2. Add these two files (`main.tf`, this `README.md`) to it and push to `main`.
3. In Spacelift: connect the GitHub repo (Source Control integration, if not
   already connected), then **Create Stack** and point it at this repo.
   Leave everything else at the defaults — no worker pool setup needed, the
   public worker pool handles this fine.
4. Trigger a run (push a commit, or trigger manually from the Spacelift UI).
5. Watch the run go through **Initializing → Planning → Applying**. The
   Plan phase shows "1 to add" (the `random_pet` resource); confirming it
   runs Apply, which actually creates it and prints the `pet_name` output.
## What to look at while it runs
 
- The **Space** the stack lives in (likely a default root space).
- The **Run** page — phases, logs, and the plan/apply diff.
- The **Queue** tab under whichever worker pool picked it up.
Nothing here is destructive or costs anything — `random_pet` is just a
generated string, safe to create and destroy freely.
