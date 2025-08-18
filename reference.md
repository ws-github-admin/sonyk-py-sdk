# Reference
## Agents
<details><summary><code>client.agents.<a href="src/sonyk_sdk/agents/client.py">list_agents</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all agents for the organization
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.agents.list_agents()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number for pagination
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Number of items per page
    
</dd>
</dl>

<dl>
<dd>

**search:** `typing.Optional[str]` — Search agents by name
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="src/sonyk_sdk/agents/client.py">create_agent</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new AI voice agent with specified configuration
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import (
    AgentConfiguration,
    AgentConfigurationLlm_Openai,
    AgentConfigurationStt_Deepgram,
    AgentConfigurationTts_Elevenlabs,
    SonykClient,
)

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.agents.create_agent(
    agent_name="Restaurant Receptionist",
    agent_json=AgentConfiguration(
        llm=AgentConfigurationLlm_Openai(
            model="gpt-5",
            system_prompt="# Role\nYou are Georgia, a friendly and professional receptionist at the  restaurant.\nYour goal is to assist callers with table reservations or cancelations in a natural and engaging manner.\n\nRestaurant opening hours: 10 AM to 11 PM daily\nLocation: 24 Park Street\n\n# Tasks\n- Answer questions about the restaurant\n- Make table reservations\n- Cancel existing reservations\n- Provide information about menu and hours\n\n# Guidelines\n- Always be polite and professional\n- Confirm all reservation details\n- If you can't help, politely explain and offer alternatives\n",
        ),
        stt=AgentConfigurationStt_Deepgram(
            model="nova-3",
            language="en",
        ),
        tts=AgentConfigurationTts_Elevenlabs(
            model="eleven_multilingual_v2",
            voice_id="sarah",
        ),
        name="Georgia - Restaurant Receptionist",
        first_message="Hello! Welcome to  restaurant. I'm Georgia, how can I help you today?",
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_name:** `str` — Human-readable name for the agent
    
</dd>
</dl>

<dl>
<dd>

**agent_json:** `AgentConfiguration` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="src/sonyk_sdk/agents/client.py">get_agent</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a specific agent by ID with full configuration
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.agents.get_agent(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` — Agent identifier
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="src/sonyk_sdk/agents/client.py">update_agent</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update agent configuration. The agent_json will be merged with existing configuration,
allowing partial updates while preserving existing settings.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.agents.update_agent(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**agent_name:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**agent_json:** `typing.Optional[AgentConfiguration]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="src/sonyk_sdk/agents/client.py">delete_agent</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete an agent (permanent deletion)
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.agents.delete_agent(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="src/sonyk_sdk/agents/client.py">get_agent_tools</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all tools assigned to a specific agent
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.agents.get_agent_tools(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="src/sonyk_sdk/agents/client.py">assign_tool_to_agent</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Assign an existing tool to an agent
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.agents.assign_tool_to_agent(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    tool_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**tool_id:** `str` — Tool identifier to assign
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="src/sonyk_sdk/agents/client.py">unassign_tool_from_agent</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Remove a tool assignment from an agent
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.agents.unassign_tool_from_agent(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    tool_id="toolId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**tool_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Phones
<details><summary><code>client.phones.<a href="src/sonyk_sdk/phones/client.py">list_phones</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all phone numbers for the organization
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.phones.list_phones(
    provider="twilio",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number for pagination
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Number of items per page
    
</dd>
</dl>

<dl>
<dd>

**provider:** `typing.Optional[str]` — Filter by phone provider
    
</dd>
</dl>

<dl>
<dd>

**is_active:** `typing.Optional[bool]` — Filter by active status
    
</dd>
</dl>

<dl>
<dd>

**agent_id:** `typing.Optional[str]` — Filter by assigned agent
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="src/sonyk_sdk/phones/client.py">create_phone</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add a new phone number to the organization
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.phones.create_phone(
    phone_number="+xxxxxxxxxx",
    provider="twilio",
    twilio_sid="ACxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    twilio_token="xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_number:** `str` — Phone number in E.164 format
    
</dd>
</dl>

<dl>
<dd>

**provider:** `str` — Phone service provider
    
</dd>
</dl>

<dl>
<dd>

**twilio_sid:** `str` — Twilio SID
    
</dd>
</dl>

<dl>
<dd>

**twilio_token:** `str` — Twilio Token
    
</dd>
</dl>

<dl>
<dd>

**nickname:** `typing.Optional[str]` — Optional friendly name for the phone
    
</dd>
</dl>

<dl>
<dd>

**agent_id:** `typing.Optional[str]` — Optional agent to assign the phone to
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="src/sonyk_sdk/phones/client.py">get_phone</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a specific phone by ID
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.phones.get_phone(
    phone_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="src/sonyk_sdk/phones/client.py">update_phone</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update phone details or agent assignment
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.phones.update_phone(
    phone_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**nickname:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**agent_id:** `typing.Optional[str]` — Agent ID to assign (null to unassign)
    
</dd>
</dl>

<dl>
<dd>

**is_active:** `typing.Optional[bool]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="src/sonyk_sdk/phones/client.py">delete_phone</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deactivate a phone number
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.phones.delete_phone(
    phone_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="src/sonyk_sdk/phones/client.py">map_phone_to_agent</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Assign a phone number to a specific agent
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.phones.map_phone_to_agent(
    phone_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    agent_id="agentId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**agent_id:** `str` — Agent ID to assign the phone to
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="src/sonyk_sdk/phones/client.py">unmap_phone_from_agent</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Remove agent assignment from a phone number
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.phones.unmap_phone_from_agent(
    phone_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Tools
<details><summary><code>client.tools.<a href="src/sonyk_sdk/tools/client.py">list_tools</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all available tools for the organization
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.tools.list_tools()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number for pagination
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Number of items per page
    
</dd>
</dl>

<dl>
<dd>

**search:** `typing.Optional[str]` — Search tools by name or description
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.tools.<a href="src/sonyk_sdk/tools/client.py">create_tool</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new tool/function that can be assigned to agents
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.tools.create_tool(
    tool_name="make_reservation",
    tool_description="Creates a new restaurant reservation with the specified date, time, party size, and customer details",
    server_url="https://api.restaurant.com/reservations",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tool_name:** `str` 

Unique name for the tool. This will be the function name that the agent uses.
Use snake_case format (e.g., make_reservation, get_weather, send_email).
    
</dd>
</dl>

<dl>
<dd>

**tool_description:** `str` 

Detailed description of what the tool does. The agent uses this to understand
when and how to use the tool. Be specific about the tool's purpose and behavior.
    
</dd>
</dl>

<dl>
<dd>

**server_url:** `str` 

The API endpoint URL that will be called when the agent uses this tool.
This should be a complete, accessible URL that accepts the specified HTTP method.
    
</dd>
</dl>

<dl>
<dd>

**parameters:** `typing.Optional[typing.Sequence[CreateToolParameterRequest]]` 

Parameters that the tool accepts. Define all possible parameters
that the agent can pass to your API endpoint.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.tools.<a href="src/sonyk_sdk/tools/client.py">get_tool</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a specific tool by ID
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.tools.get_tool(
    tool_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tool_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.tools.<a href="src/sonyk_sdk/tools/client.py">update_tool</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update tool configuration
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.tools.update_tool(
    tool_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    tool_name="make_reservation",
    tool_description="Creates a new restaurant reservation with the specified date, time, party size, and customer details",
    server_url="https://api.restaurant.com/reservations",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tool_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**tool_name:** `str` 

Unique name for the tool. This will be the function name that the agent uses.
Use snake_case format (e.g., make_reservation, get_weather, send_email).
    
</dd>
</dl>

<dl>
<dd>

**tool_description:** `str` 

Detailed description of what the tool does. The agent uses this to understand
when and how to use the tool. Be specific about the tool's purpose and behavior.
    
</dd>
</dl>

<dl>
<dd>

**server_url:** `str` 

The API endpoint URL that will be called when the agent uses this tool.
This should be a complete, accessible URL that accepts the specified HTTP method.
    
</dd>
</dl>

<dl>
<dd>

**parameters:** `typing.Optional[typing.Sequence[CreateToolParameterRequest]]` 

Parameters that the tool accepts. Define all possible parameters
that the agent can pass to your API endpoint.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.tools.<a href="src/sonyk_sdk/tools/client.py">delete_tool</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a tool
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.tools.delete_tool(
    tool_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tool_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Assets
<details><summary><code>client.assets.<a href="src/sonyk_sdk/assets/client.py">list_agent_assets</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all knowledge base assets for a specific agent with pagination and filtering.

Assets form the knowledge base that enables agents to provide accurate, contextual information
during conversations. The system supports multiple asset types and intelligent processing:

## Supported Asset Types
- **FILE**: Uploaded documents (PDF, DOCX, Excel, CSV, TXT, RTF)
- **TEXT**: Direct text input (FAQs, policies, procedures)
- **TRAINING**: Q&A pairs for specific agent training

## Processing Pipeline
1. **Secure Upload**: Files validated and stored safely
2. **Text Extraction**: Advanced parsers extract clean text from files
3. **AI Enhancement**: OCR errors corrected, formatting cleaned
4. **Smart Chunking**: Content divided into optimal retrieval segments
5. **Vector Embeddings**: Semantic search capabilities enabled
6. **Cloud Storage**: Secure storage with version control

## Use Cases
- Product documentation and manuals
- Company policies and procedures
- FAQ and help content
- Training materials and scripts
- Customer service knowledge base
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.assets.list_agent_assets(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    search="product documentation",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` — Agent ID to retrieve assets for
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number for pagination
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Number of items per page
    
</dd>
</dl>

<dl>
<dd>

**type:** `typing.Optional[ListAgentAssetsRequestType]` — Filter by asset type
    
</dd>
</dl>

<dl>
<dd>

**search:** `typing.Optional[str]` — Search assets by title or content
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="src/sonyk_sdk/assets/client.py">get_agent_asset_details</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve comprehensive information about a specific asset including processing details and content chunks.

## Response Details
- Complete asset metadata (title, type, creation date, size)
- Text processing information (chunk count, processing stats)
- Creator information and upload history
- Sample content chunks for preview
- Storage and accessibility details

## Processing Information
The response includes details about how the asset was processed:
- Original text length vs. processed length
- Number of chunks created for search
- Embedding model used for semantic search
- Text sanitization and enhancement applied
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.assets.get_agent_asset_details(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    asset_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**asset_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="src/sonyk_sdk/assets/client.py">update_agent_asset</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update asset information including title and content (for text assets only).

## Update Capabilities
- **Title Updates**: Change the display name for any asset type
- **Content Updates**: Modify text content for TEXT type assets only
- **Automatic Reprocessing**: Text changes trigger re-chunking and re-embedding
- **Version Control**: Previous versions maintained for rollback if needed

## File Assets
File assets (PDF, DOCX, etc.) cannot have their content updated through this endpoint.
To update file content, delete the existing asset and upload a new file.

## Processing Impact
When text content is updated:
- Existing chunks are replaced with new ones
- Vector embeddings are regenerated
- Search index is updated immediately
- Agent has access to updated information within seconds
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.assets.update_agent_asset(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    asset_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**asset_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**title:** `typing.Optional[str]` — New title for the asset
    
</dd>
</dl>

<dl>
<dd>

**text:** `typing.Optional[str]` 

Updated text content (TEXT assets only).

**Requirements:**
- Minimum 10 characters
- Maximum 50,000 characters
- Only applies to TEXT type assets
- Triggers automatic reprocessing
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="src/sonyk_sdk/assets/client.py">delete_agent_asset</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently delete an asset from the agent's knowledge base.

## Deletion Process
1. **Immediate Removal**: Asset becomes unavailable to the agent instantly
2. **Chunk Cleanup**: All text chunks removed from search database
3. **Storage Cleanup**: Files deleted from cloud storage
4. **Permanent Action**: Deletion cannot be undone

## Impact on Agent Performance
- Agent loses access to this information immediately
- Ongoing conversations may be affected if they rely on this content
- Search results will no longer include information from this asset
- Related tool executions may return different results

## Best Practices
- Ensure the asset is no longer needed before deletion
- Consider updating content instead of deleting when possible
- Test agent performance after removing significant knowledge sources
- Maintain backups of important content outside the system
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.assets.delete_agent_asset(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    asset_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**asset_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="src/sonyk_sdk/assets/client.py">upload_agent_asset</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Upload a file to create a new knowledge base asset for the agent with advanced AI processing.

## Supported File Types & Processing

### Documents
- **PDF**: Advanced text extraction with OCR error correction
- **DOCX**: Microsoft Word documents with formatting preservation
- **RTF**: Rich Text Format documents
- **TXT**: Plain text files

### Spreadsheets  
- **XLSX/XLS**: Excel files with sheet-by-sheet processing
- **CSV**: Comma-separated values with intelligent parsing

## AI-Enhanced Processing Pipeline

### 1. Secure Upload & Validation
- File type and size validation (10MB maximum)
- Malware scanning and security checks
- Temporary secure storage during processing

### 2. Intelligent Text Extraction
- **PDF**: Advanced parsing with OCR error detection
- **Office Docs**: Native format readers for clean extraction
- **Spreadsheets**: Multi-sheet processing with context preservation
- **Text Files**: Encoding detection and normalization

### 3. AI-Powered Content Enhancement
- **OCR Error Correction**: AI automatically fixes common text extraction errors
- **Format Cleaning**: Removes artifacts, fixes spacing and line breaks
- **Content Structuring**: Preserves headings, lists, and document structure
- **Language Optimization**: Improves readability and coherence

### 4. Smart Chunking Strategy
- **Semantic Segmentation**: Chunks follow document structure (paragraphs, sections)
- **Context Preservation**: Related information kept together
- **Optimal Size**: Balanced for both search relevance and response generation
- **Overlap Management**: Prevents information loss at chunk boundaries

### 5. Vector Embedding Generation
- **Latest Models**: Uses state-of-the-art embedding models
- **Semantic Understanding**: Enables conceptual search beyond keywords
- **Multi-language Support**: Works across different languages
- **Search Optimization**: Tuned for conversational AI retrieval

### 6. Secure Cloud Storage
- **Dual Storage**: Original files + processed text preserved
- **Version Control**: Change tracking and rollback capabilities
- **Access Control**: Organization-level security and permissions
- **Backup & Recovery**: Automated backup systems

## Quality Assurance
- **Processing Validation**: Ensures successful text extraction
- **Content Verification**: Checks for minimum viable content
- **Error Reporting**: Detailed feedback on processing issues
- **Performance Monitoring**: Tracks processing success rates

## Use Cases
- **Product Manuals**: Technical documentation and user guides
- **Policy Documents**: Company policies and procedures
- **Training Materials**: Educational content and SOPs
- **FAQ Collections**: Customer service knowledge bases
- **Research Papers**: Academic and technical documents
- **Spreadsheet Data**: Product catalogs, pricing, specifications
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.assets.upload_agent_asset(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**file:** `from __future__ import annotations

core.File` — See core.File for more documentation
    
</dd>
</dl>

<dl>
<dd>

**title:** `typing.Optional[str]` 

Optional custom title for the asset.
If not provided, the filename will be used.

**Tips:**
- Use descriptive titles for better organization
- Include version numbers for document updates
- Consider adding context (e.g., "Product Manual v2.1")
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="src/sonyk_sdk/assets/client.py">create_agent_text_asset</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new knowledge base asset directly from text content with intelligent processing.

## Ideal Use Cases

### Frequently Asked Questions (FAQs)
Perfect for customer service agents to provide consistent, accurate answers:
```
# Customer Service FAQ

## Q: What are your business hours?
A: We are open Monday to Friday, 9 AM to 6 PM EST.

## Q: How can I return a product?
A: Visit our returns page or call customer service within 30 days.
```

### Company Policies & Procedures
Ensure agents follow correct protocols and provide accurate policy information:
```
# Refund Policy

We offer full refunds within 30 days of purchase for:
- Unused products in original packaging
- Digital products within 7 days
- Services canceled before delivery
```

### Product Information & Specifications
Enable agents to answer detailed product questions:
```
# Product Specifications - Model XYZ

## Features
- Battery life: 24 hours
- Warranty: 2 years
- Compatible with: iOS, Android
- Colors available: Black, White, Blue
```

### Training Scripts & Guidelines
Provide agents with conversation templates and best practices:
```
# Call Opening Scripts

## For New Customers
"Thank you for calling [Company]. I'm [Name], and I'm here to help you today."

## For Returning Customers  
"Welcome back to [Company]! How can I assist you today?"
```

## Processing Features

### Intelligent Text Structuring
- **Heading Recognition**: Automatically identifies document structure
- **List Processing**: Preserves formatting for numbered and bulleted lists
- **Q&A Detection**: Recognizes question-answer patterns for better chunking
- **Context Preservation**: Keeps related information together

### Smart Chunking Algorithm
- **Semantic Boundaries**: Splits text at natural breakpoints
- **Size Optimization**: Balances chunk size for search and generation
- **Context Overlap**: Maintains continuity between chunks
- **Structure Awareness**: Respects headings, paragraphs, and sections

### Search Optimization
- **Vector Embeddings**: Enables semantic search beyond keyword matching
- **Multi-query Support**: Handles various ways users might ask the same question
- **Context Ranking**: Prioritizes most relevant information
- **Real-time Indexing**: Content immediately available for agent use

## Content Guidelines

### Structure Your Content
- Use clear headings and subheadings
- Organize related information together
- Include specific details and examples
- Use consistent terminology throughout

### Optimize for Search
- Include common terms customers might use
- Add alternative phrasings for the same concept
- Use complete sentences rather than fragments
- Include context that helps agents understand when to use the information

### Keep It Current
- Regular updates ensure accuracy
- Version control helps track changes
- Remove outdated information promptly
- Test agent responses after updates
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.assets.create_agent_text_asset(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    text="# Customer Service FAQ - Updated January 2025\n\n## Business Information\n\n### Q: What are your business hours?\nA: We are open Monday to Friday from 9 AM to 6 PM EST. Weekend support is available via email only.\n\n### Q: Where are you located?\nA: Our headquarters is at 123 Business St, City, State 12345. We also have locations in Chicago and Miami.\n\n## Product Support\n\n### Q: How do I return a product?\nA: Returns are easy! Visit our website's return portal, print a shipping label, and send the item back within 30 days. Refunds are processed within 5-7 business days.\n\n### Q: What's your warranty policy?\nA: All products come with a standard 1-year warranty. Extended warranties up to 3 years are available for purchase.\n\n## Account Management\n\n### Q: How do I reset my password?\nA: Click 'Forgot Password' on the login page, enter your email, and follow the instructions sent to your inbox. The reset link expires in 24 hours.\n\n### Q: Can I change my subscription plan?\nA: Yes! Log into your account, go to Settings > Subscription, and select your new plan. Changes take effect immediately.\n",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**text:** `str` 

The text content to add to the agent's knowledge base.

**Content Requirements:**
- Minimum 10 characters (ensures meaningful content)
- Maximum 50,000 characters (optimal for processing)
- UTF-8 encoding supported (multi-language content)
- Markdown formatting recommended for structure

**Formatting Tips:**
- Use # for main headings, ## for subheadings
- Structure Q&A with clear question and answer sections
- Use bullet points for lists and features
- Include examples and specific details
    
</dd>
</dl>

<dl>
<dd>

**title:** `typing.Optional[str]` 

Descriptive title for the text asset.

**Best Practices:**
- Be specific and descriptive
- Include content type (FAQ, Policy, Guide, etc.)
- Add version numbers for updates
- Use consistent naming conventions
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="src/sonyk_sdk/assets/client.py">get_agent_asset_content</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve the full text content of an asset for review, editing, or developer processing.

## Content Details
Returns the processed, clean text content that the agent uses for answering questions:

### For File Assets (PDF, DOCX, etc.)
- **Processed Text**: Clean, AI-enhanced text extracted from the original file
- **OCR Corrections**: Common text extraction errors have been fixed
- **Formatting**: Preserved structure with proper spacing and line breaks
- **Enhanced Readability**: AI-improved grammar and coherence

### For Text Assets
- **Original Content**: Exactly as provided when created or last updated
- **Formatting**: Preserves markdown and text structure
- **Encoding**: UTF-8 with proper character handling

## Use Cases

### Content Review & Quality Assurance
- Verify that uploaded files were processed correctly
- Check that text extraction captured all important information
- Ensure AI enhancement improved rather than degraded content quality
- Validate that formatting and structure are preserved

### Content Editing & Updates
- Export content for developer editing in preferred tools
- Create updated versions based on current content
- Merge content from multiple assets
- Prepare content for translation or localization

### Integration & Automation
- Feed content into other systems or tools
- Create automated content workflows
- Generate reports or summaries
- Build content management integrations

### Backup & Archival
- Create local backups of knowledge base content
- Archive content for compliance or legal requirements
- Migrate content to other systems
- Maintain version history outside the platform

## Response Information
The response includes both the content and useful metadata:
- **Content Length**: Character count for processing planning
- **Creation Date**: When the asset was originally created
- **Asset Type**: Whether it's a file upload or direct text input
- **Processing Status**: Information about how the content was processed
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.assets.get_agent_asset_content(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    asset_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**asset_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="src/sonyk_sdk/assets/client.py">search_agent_assets</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Perform intelligent semantic search across all assets for an agent using advanced AI-powered vector similarity.

## How Semantic Search Works

Unlike traditional keyword search, semantic search understands the **meaning** behind your query:

### Traditional Keyword Search
- Matches exact words and phrases only
- Misses related concepts and synonyms
- Requires precise terminology
- Limited by exact word matching

### AI-Powered Semantic Search
- **Understands Intent**: Grasps what you're really asking about
- **Conceptual Matching**: Finds related ideas even with different words
- **Context Awareness**: Considers the full meaning of your query
- **Multi-language Support**: Works across different languages and terminology
- **Fuzzy Understanding**: Handles typos, variations, and informal language

## Search Examples

### Query: "How do I reset my password?"
**Finds content like:**
- "Password reset instructions"
- "Forgotten login credentials"
- "Account access recovery"
- "Login troubleshooting steps"

### Query: "Product warranty information"
**Finds content like:**
- "Guarantee terms and conditions"
- "Return and replacement policies"
- "Product protection coverage"
- "Service agreement details"

### Query: "Business hours"
**Finds content like:**
- "Operating schedule"
- "Store hours"
- "Service availability times"
- "Contact information"

## Retrieval-Augmented Generation (RAG)

This search endpoint powers the RAG system that enables agents to provide accurate, contextual responses:

### 1. Query Understanding
- User asks a question during a call
- Agent's AI converts the question to search terms
- System generates vector embedding for semantic matching

### 2. Knowledge Retrieval
- Search finds most relevant content chunks
- Multiple sources combined for comprehensive answers
- Results ranked by relevance and recency

### 3. Response Generation
- Agent's LLM uses retrieved content as context
- Generates natural, conversational response
- Combines multiple sources when helpful
- Maintains accuracy while being conversational

## Search Parameters & Tuning

### Similarity Threshold (0.0 - 1.0)
Controls how closely results must match your query:
- **0.5-0.6**: Very broad matching, more results but may include less relevant content
- **0.7-0.8**: Balanced matching, good mix of relevance and recall **(recommended)**
- **0.9-1.0**: Strict matching, only very closely related content returned
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.assets.search_agent_assets(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    query="How do I reset my password?",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**query:** `str` — Search query for finding relevant content
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Maximum number of results to return
    
</dd>
</dl>

<dl>
<dd>

**threshold:** `typing.Optional[float]` 

Minimum similarity score for results (0.0 = any match, 1.0 = perfect match).
Higher values return fewer, more relevant results.
    
</dd>
</dl>

<dl>
<dd>

**type:** `typing.Optional[SearchAgentAssetsRequestType]` — Filter results by chunk type (optional)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Calls
<details><summary><code>client.calls.<a href="src/sonyk_sdk/calls/client.py">initiate_call</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Proxy endpoint to initiate calls through the Sonyk Core API system.
Validates permissions and credits, then forwards request to core.sonyk.io.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from sonyk_sdk import SonykClient

client = SonykClient(
    api_key="YOUR_API_KEY",
)
client.calls.initiate_call(
    agent_id="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    to_number="+xxxxxxxxxx",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agent_id:** `str` — UUID of the agent to use for the call
    
</dd>
</dl>

<dl>
<dd>

**to_number:** `str` — Phone number to call (E.164 format)
    
</dd>
</dl>

<dl>
<dd>

**variables:** `typing.Optional[typing.Dict[str, typing.Optional[typing.Any]]]` — Optional JSON object containing custom variables to pass to the agent during the call
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

