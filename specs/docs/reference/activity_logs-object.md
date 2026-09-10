---
updatedAt: 2025-05-29T17:01:16.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Object

Activity Log

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