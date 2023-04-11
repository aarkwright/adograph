# ado
An Azure DevOps pipeline dependecy mapper. See templating dependencies between Azure pipelines.

## Reqs

python >= 3.8

# Flow

0. receive input: yaml file
1. validate yaml (implied in safe_load() )
2. assert type of azure pipeline; can be:
   - list of jobs
   - list of stages
   - list of steps
   - list of tasks
3. read non-"action" elements like:
   - global pipeline parameters
   - global pipeline variables
   - global triggers

4. Identify series/parallel actions and map

5. Identify remote pipeline calls ("template:" keyword or @<some other repo> references)

6. Identify parameter overwrites