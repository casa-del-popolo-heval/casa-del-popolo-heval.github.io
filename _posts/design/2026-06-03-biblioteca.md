---
layout: page
title: "Catalogo della Biblioteca"
permalink: /biblioteca/
---

In questa pagina è possibile consultare l'elenco completo dei libri disponibili presso la nostra biblioteca.

<!-- Barra di ricerca rapida -->
<div style="margin-bottom: 25px;">
  <input type="text" id="ricercaLibro" onkeyup="filtraLibri()" placeholder="Cerca per titolo, autore, soggetto, editore o collocazione..." style="padding: 12px; width: 100%; border: 1px solid #ccc; border-radius: 4px; font-size: 16px;">
</div>

<div style="overflow-x: auto;">
  <table id="tabellaLibri" style="width:100%; border-collapse: collapse; font-size: 15px;">
    <thead>
      <tr style="background-color: #f8f9fa; border-bottom: 2px solid #dee2e6; text-align: left;">
        <th style="padding: 12px; text-align: center; width: 5%;">Stato</th>
        <th style="padding: 12px; width: 25%;">Autore</th>
        <th style="padding: 12px; width: 30%;">Titolo</th>
        <th style="padding: 12px; width: 15%;">Soggetto</th>
        <th style="padding: 12px; width: 13%;">Editore</th>
        <th style="padding: 12px; width: 5%;">Anno</th>
        <th style="padding: 12px; width: 7%;">Collocazione</th>
      </tr>
    </thead>
    <tbody>
      {% assign libri_ordinati = site.data.libri %}
      {% for libro in libri_ordinati %}
      <tr style="border-bottom: 1px solid #eee;">
        <td style="padding: 12px; text-align: center;">
          {% if libro.disponibile == "si" %}
            <span style="color: #2ecc71; font-size: 1.4em; cursor: help;" title="Disponibile">●</span>
          {% else %}
            <span style="color: #e74c3c; font-size: 1.4em; cursor: help;" title="In prestito">●</span>
          {% endif %}
        </td>
        <td style="padding: 12px;">{{ libro["autore"] }}</td> <!-- MODIFICATO QUI -->
        <td style="padding: 12px; font-weight: 500; color: #222;">{{ libro.titolo }}</td>
        <td style="padding: 12px;"><span style="background: #e9ecef; padding: 3px 8px; border-radius: 4px; font-size: 13px; text-transform: capitalize;">{{ libro.soggetto }}</span></td>
        <td style="padding: 12px;">{{ libro.editore }}</td>
        <td style="padding: 12px; text-align: center;">{{ libro.anno }}</td>
        <td style="padding: 12px; font-family: monospace; font-weight: bold; color: #555;">{{ libro.collocazione }}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>

<!-- Script per la ricerca in tempo reale -->
<script>
function filtraLibri() {
  var input, filter, table, tr, td, i, j, txtValue;
  input = document.getElementById("ricercaLibro");
  filter = input.value.toUpperCase();
  table = document.getElementById("tabellaLibri");
  tr = table.getElementsByTagName("tr");

  for (i = 1; i < tr.length; i++) {
    tr[i].style.display = "none";
    td = tr[i].getElementsByTagName("td");
    for (j = 1; j < td.length; j++) {
      if (td[j]) {
        txtValue = td[j].textContent || td[j].innerText;
        if (txtValue.toUpperCase().indexOf(filter) > -1) {
          tr[i].style.display = "";
          break;
        }
      }
    }
  }
}
</script>
