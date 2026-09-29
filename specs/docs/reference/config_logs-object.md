---
updatedAt: 2025-05-29T17:01:33.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Object

Config Log

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Field
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        **id**
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        Unique identifier for the object.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **text**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        Text describing the event.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **html**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        HTML describing the event.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **diff**\
        *object*
      </td>

      <td style={{ textAlign: "left" }}>
        Diff object containing the following fields: 

        ```json
        [
           {
               "name": "<SECRET NAME>",
               "added": "<VALUE ADDED>",
               "removed": "<VALUE REMOVED>"
           }
        ]
        ```
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **rollback**\
        *boolean*
      </td>

      <td style={{ textAlign: "left" }}>
        Is this config log a rollback of a previous log.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **user**\
        *object*
      </td>

      <td style={{ textAlign: "left" }}>
        User object containing the following fields: 

        ```json
        {
            "email": Email,
            "name": String,
            "profile_image_url": String
        }
        ```
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **project**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        Unique identifier for the project object.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **environment**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        Unique identifier for the environment object.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **config**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        The config's name.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **created\_at**\
        *date*
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time of the object's creation.
      </td>
    </tr>
  </tbody>
</Table>