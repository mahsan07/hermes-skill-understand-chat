# How Understand Chat Works

Ask targeted questions about a codebase using its knowledge graph rather than guessing from filenames.

![Detailed systems blueprint for Understand Chat](../assets/system-blueprint.png)

## Stages

### 1. Translate the question into graph entities

**Primary surface:** `Developer question`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 2. Locate relevant components and symbols

**Primary surface:** `Existing code knowledge graph`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 3. Traverse calls imports and data paths

**Primary surface:** `Entity and path search`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 4. Open the minimum supporting source excerpts

**Primary surface:** `Evidence bundle`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 5. Compose an answer from graph evidence

**Primary surface:** `Grounded answer`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 6. Cite files symbols and uncertainty

**Primary surface:** `Grounded answer`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.

## Failure handling

- **Authorization failure:** do not probe credentials or broaden access; report the missing authority.
- **Target ambiguity:** stop before mutation and request the minimum identifying information.
- **Tool or service failure:** retain error evidence, retry only safe transient failures, and cap retries.
- **Verification failure:** classify the run as incomplete even when the preceding operation returned success.

## Completion evidence

The handoff should contain the original request, inspection state, preview or plan, exact execution result, direct verification, and a final receipt naming limitations and withheld actions.
