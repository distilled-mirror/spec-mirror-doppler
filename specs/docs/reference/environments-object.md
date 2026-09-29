---
updatedAt: 2025-05-29T17:01:25.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Object

Environment

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
        An identifier for the object.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **name**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        Name of the environment.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **project**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        Identifier of the project the environment belongs to.
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

    <tr>
      <td style={{ textAlign: "left" }}>
        **initial\_fetch\_at**\
        *date*
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time of the first secrets fetch from a config in the environment.
      </td>
    </tr>
  </tbody>
</Table>