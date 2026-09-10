---
updatedAt: 2025-05-29T17:01:28.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Object

Config

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
        **name**
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        Name of the config.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **project**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        Identifier of the project that the config belongs to.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **environment**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        Identifier of the environment that the config belongs to.
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
        Date and time of the first secrets fetch.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **last\_fetch\_at**\
        *date*
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time of the last secrets fetch.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **root**\
        *boolean*
      </td>

      <td style={{ textAlign: "left" }}>
        Whether the config is the root of the environment.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **locked**\
        *boolean*
      </td>

      <td style={{ textAlign: "left" }}>
        Whether the config can be renamed and/or deleted.
      </td>
    </tr>
  </tbody>
</Table>