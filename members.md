---
layout: page
title: Members
permalink: /members/
order: 11
---

Welcome to the list of our active members. You can use the search box below to filter by **name**, **surname**, or **affiliation**.

Researchers who are interested in becoming TC15 members are invited to send an email to chair at iapr-tc15.org.

**This page is under construction**

<input type="text" id="search" placeholder="Search name, surname or affiliation" style="margin-bottom:1rem; width:100%; max-width:400px; padding:.5rem; border:1px solid #ccc; border-radius:.25rem;" />

<table id="members-table" border="1" cellspacing="0" cellpadding="5">
  <thead>
    <tr>
      <th>Name</th>
      <th>Surname</th>
      <th>Affiliation</th>
    </tr>
  </thead>
  <tbody>
    {% for m in site.data.members %}
    <tr>
      <td>{{ m.name }}</td>
      <td>{{ m.surname }}</td>
      <td>{{ m.affiliation }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<script>
document.addEventListener('DOMContentLoaded', function () {
  const input = document.getElementById('search');
  const rows = document.querySelectorAll('#members-table tbody tr');

  input.addEventListener('input', function () {
    const query = this.value.toLowerCase();
    rows.forEach(row => {
      const rowText = row.innerText.toLowerCase();
      row.style.display = rowText.includes(query) ? '' : 'none';
    });
  });
});
</script>

