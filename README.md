# Plan

## Extract general trends

- nombre de mesures
- diff := mesure - limite > 0 ? mesure - limite : 0
- proportion de dépassement général / par limite
- 50eme, 75eme, 95eme percentiles général / inférieur / supérieur
-

## Miller

### Add diff field
mlr --fs=";" --csv put '$diff = ($mesure - $limite > 0 ? $mesure - $limite : 0)' sample.csv

### Get limite;mesure_median;mesure_p75;mesure_p90
mlr --fs=";" --csv stats1 -a median,p75,p90 -f mesure -g limite sample.csv

limite;mesure_median;mesure_p75;mesure_p90
90;82;90;96
80;74;82;90
110;86;109;128
70;67;74;81
130;103;123;136
50;98;107;115


# Resources

CSV manipulation: https://miller.readthedocs.io