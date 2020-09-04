---
layout: tunnel
title: "Ecart de taux d'augmentations individuelles entre les femmes et les hommes"
---

<h1>{{ page.title }}</h1>

<fieldset>
  <div class=row>
    <div>{% include radios.html name='augmentation-calculable' label="L'indicateur sur les taux d'augmentations individuelles est-il calculable" required="true" %}</div>
  </div>
</fieldset>

<fieldset>
  <div class=row>{% include select.html name="augmentation-precision-motif" empty="true" label="Précision du motif" %}</div>
</fieldset>

<fieldset>
  <div class=row>{% include textarea.html name="augmentation-precision-autre-motif" label='Préciser "autres motifs"' %}</div>
</fieldset>

<fieldset>
  <div class=row>{% include input.html type="number" name="augmentation-resultat-pourcentage" label="Résultat final en pourcentage (%)" min=0 max=40 %}</div>
</fieldset>

<fieldset>
  <div class=row>{% include input.html type="number" name="augmentation-resultat-nombre-salaries" label="Résultat final en nombre de salariés" min=0 max=40 %}</div>
</fieldset>

<fieldset>
  <div class=row>{% include select.html name="augmentation-favorable" empty="true" label="Population envers laquelle l'écart est favorable" %}</div>
</fieldset>

<fieldset class="note subnote">
  <div class=row>{% include input.html type="number" name="augmentation-resultat-pourcentage" label="Nombre de points obtenus sur le résultat final en pourcentage" min=0 max=40 %}</div>
</fieldset>

<fieldset class="note subnote">
  <div class=row>{% include input.html type="number" name="augmentation-resultat-nombre-salaries" label="Nombre de points obtenus sur le résultat final en nombre de salariés" min=0 max=40 %}</div>
</fieldset>

<fieldset class=note>
  <div class=row>{% include input.html type="number" name="remuneration-note" label="Nombre de points obtenus sur l'indicateur" min=0 max=35 %}</div>
</fieldset>

<script>
  document.onready = () => {
    const calculOptions = [
      {value: "calculable", label: "oui"},
      {value: "nc", label: "non"},
    ]
    buildRadioOptions(document.querySelector('#field--augmentation-calculable'), calculOptions)
    const motifsOptions = [
      { value: 'asbaugi', label: "Absence d'augmentations individuelles"},
      { value: 'xxxxxx', label: "L'entreprise ne comporte pas au moins 5 femmes et 5 hommes"},
      { value: 'autre', label: "Autres motifs"},
    ]
    buildSelectOptions(document.querySelector('#field--augmentation-precision-motif'), motifsOptions)
    const favorableOptions = [
      { value: 'femmes', label: "Femmes" },
      { value: 'hommes', label: "Hommes" }
    ]
    buildSelectOptions(document.querySelector('#field--augmentation-favorable'), favorableOptions)
  }
</script>