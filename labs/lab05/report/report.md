---
## Front matter
title: "Лабораторная работа 5"
subtitle: "Модель хищник-жертва"
author: "Бабенко Артём Сергеевич"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Научиться строить график зависимости численности хищников от численности жертв, график изменения численности хищников и численности жертв при 
различных начальных условиях. Научиться находить стационарное 
состояние системы.


# Теоретическое введение

Простейшая модель взаимодействия двух видов типа «хищник — жертва» -
модель Лотки-Вольтерры. Данная двувидовая модель основывается на 
следующих предположениях:
1. Численность популяции жертв x и хищников y зависят только от времени 
(модель не учитывает пространственное распределение популяции на 
занимаемой территории)
2. В отсутствии взаимодействия численность видов изменяется по модели 
Мальтуса, при этом число жертв увеличивается, а число хищников падает
3. Естественная смертность жертвы и естественная рождаемость хищника 
считаются несущественными
4. Эффект насыщения численности обеих популяций не учитывается
5. Скорость роста численности жертв уменьшается пропорционально 
численности хищников.
Стационарное состояние системы (1) (положение равновесия, не зависящее 
от времени решение) будет в точке: x0 = c/d, y0 = a/b.
Если начальные значения задать в стационарном состоянии x(0)=x0, y(0)=y0, то в любой момент времени численность популяций изменяться не будет. При малом отклонении от положения равновесия численности как хищника, так и жертвы с течением времени не возвращаются к равновесным значениям, а совершают периодические колебания вокруг стационарной точки. 

# Выполнение лабораторной работы

Задание звучит следующим образом:
![](image/0.png) 

Написал код на Julia: 
![](image/1.png)

Программа выдала следующие результаты:
график зависимости численности хищников от численности жертв:
![](image/2.png) 
график изменения численности хищников и численности жертв при 
заданных начальных условиях:
![](image/3.png)

Код для определения стационарного состояния системы:
![](image/4.png)
такой график получился:
![](image/5.png)



Написал код на OpenModelica: 

![](image/6.png)

Программа выдала следующие результаты:
график зависимости численности хищников от численности жертв:
![](image/7.png) 
график изменения численности хищников и численности жертв при 
заданных начальных условиях:
![](image/8.png)
стационарное состояние системы:
![](image/9.png)


# Выводы

Я научился строить график зависимости численности хищников от численности жертв, график изменения численности хищников и численности жертв при 
различных начальных условиях. Научился находить стационарное 
состояние системы.

# Список литературы{.unnumbered}

1. Документация по Julia: https://docs.julialang.org/en/v1/

2. Документация по OpenModelica: https://openmodelica.org/

3. Решение дифференциальных уравнений: https://www.wolframalpha.com/

4. Бутиков И. Е. Собственные колебания линейного осциллятора. 2011.