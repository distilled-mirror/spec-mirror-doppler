---
updatedAt: 2025-05-29T17:01:53.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Object

Service Token

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
        Name of the service token.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **slug**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        A unique identifier of the service token.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **key**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        An API key that is used for authentication.\
        **Only available when creating the token.**
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

    <tr>
      <td style={{ textAlign: "left" }}>
        **expires\_at**\
        *date*
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time of the token's expiration, or `null` if token does not auto-expire.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **access**\
        *string*
      </td>

      <td style={{ textAlign: "left" }}>
        One of `read`, `read/write`.
      </td>
    </tr>
  </tbody>
</Table>