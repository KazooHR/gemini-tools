# Ticket Creation

## Useful Context

When creating tickets in Jira
- These are the custom fields, what they map to, and an example input:
    - **customfield_10209**: Acceptance Criteria field
        - {
            "type": "doc",
            "version": 1,
            "content": [...] # Atlassian Document Format
        }
        - Input all Acceptance Criteria here, not under Description
    - **customfield_10013**: Epic Link field
    - **customfield_10140**: Layer Cake field
        - "customfield_10140": {"value": "Strategic Roadmap"}
    - **customfield_10001**: Team field
        - "customfield_10001": "team-uuid-here"
    - **customfield_10047**: Story Points field
        - "customfield_10047": 2
    - **customfield_10061**: Technical Details field (implementation specifics, technical requirements)
        - {
            "type": "doc",
            "version": 1,
            "content": [...] # Atlassian Document Format
        }
        - Input all Technical Details here, not under Description
    - "components": Components
        - "components": [{"name": "..."}]

## Steps

- Use the atlassian-rovo-mcp to interact with Confluence and Jira
- Ask the user to paste in any Confluence documents they would like to use for context. Verify they have given you all the context they want to before proceeding.
- Read the documents you were given and see if any have a list of tickets. Use the documents to generate a list of tickets, and provide the user with a 1 line summary of each possible ticket.
- Ask the user if they would like to add any more tickets to the list or remove any of the ones we gave them.
- Once the user is finished adjusting the tickets, tell them that we are going to create a Confluence page that they can edit with the tickets listed out. Ask the user for a parent page to put the new page under.
  - Query the parent page to get its SpaceId
  - When listing the tickets, each will need the following fields populated. Type, Title, Description, Technical Details, Acceptance Criteria. Add a Story Points field and Blocker field as well for the user to fill out in the Confluence page before you create the tickets.
    - Description should have a general description of the ticket. Use the Document to guide writing a useful description for each ticket.
    - Technical Details should contain any implementation details for this ticket. Use the technical documentation to help generate useful and detailed details here.
    - Acceptance Criteria should be a short list of testable bullet points for the ticket.
    - Type will be either Task or Story. Tasks are for small pieces of work, Stories are for broader user-impacting pieces of work. For instance, implementing a Backend endpoint would be a Task, but integrating it with a Frontend would be a story, as it affects our users.
    - The tickets should be listed in an ordered list with sub-points for each field. Don't use a table.
    - Keep track of each ticket's ticket number as they're created. At the end, we'll need to alert the user to which tickets they need to set blockers for, as the Jira tools don't support you doing it.
  - Create the Confluence page. Return a link to it for the user to click.
- Ask the user to read the Confluence page and make any edits they deem necessary to the ticket list. They can also ask you for help, and you can edit the Confluence page for them. Ask them if they're ready to continue.
- Once they've indicated they're ready for you to continue, we're going to convert the Confluence page into Jira tickets.
  - Ask the user to provide a link to an Epic that you can put the tickets under. You will use the Layer Cake, Team, and Components values from this Epic for every ticket you create. These fields are required.
  - Ask the user if they would like you to edit the Description of the Epic with a summary of the project, and links to the Confluence documents they provided earlier in the process.
  - Now, re-read the Confluence page to get the updates, and create the other tickets under the epic.
- Ask the user if they would like help making any changes. If not, thank them and render ASCII art of a cute animal.