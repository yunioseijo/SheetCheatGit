# Git Cheat Sheet: Los 100 Comandos Más Importantes

---

## Configuración Inicial
1. `git config --global user.name "Tu Nombre"`
   - Configura tu nombre de usuario globalmente.

2. `git config --global user.email "tu.email@dominio.com"`
   - Configura tu correo electrónico globalmente.

3. `git config --list`
   - Lista toda la configuración actual de Git.

4. `git config --global core.editor "nombre_editor"`
   - Configura el editor de texto por defecto.

5. `git config --global alias.st status`
   - Crea un alias para un comando (en este caso, `git status` como `git st`).

---

## Inicialización y Clonación
6. `git init`
   - Inicializa un nuevo repositorio Git en el directorio actual.

7. `git clone URL`
   - Clona un repositorio desde una URL.

8. `git clone -b rama URL`
   - Clona un repositorio y verifica una rama específica.

---

## Básicos del Ciclo de Vida
9. `git status`
   - Muestra el estado de los archivos en el directorio de trabajo.

10. `git add archivo`
    - Añade un archivo específico al área de preparación (staging).

11. `git add .`
    - Añade todos los archivos modificados al área de preparación.

12. `git commit -m "mensaje"`
    - Guarda los cambios en el repositorio con un mensaje descriptivo.

13. `git commit -am "mensaje"`
    - Añade y comete todos los archivos modificados en un solo paso.

14. `git diff`
    - Muestra los cambios no preparados.

15. `git diff --staged`
    - Muestra los cambios que están en el área de preparación.

16. `git reset archivo`
    - Retira un archivo del área de preparación.

17. `git reset --hard`
    - Resetea el directorio de trabajo y el área de preparación al último commit.

18. `git rm archivo`
    - Elimina un archivo del directorio y del control de versiones.

---

## Ramas (Branching)
19. `git branch`
    - Lista todas las ramas locales.

20. `git branch nombre-rama`
    - Crea una nueva rama.

21. `git branch -d nombre-rama`
    - Elimina una rama local.
21.2 `git push origin --delete nombre-rama`
    - Elimina una rama del repositorio remoto.
      
22. `git checkout nombre-rama`
    - Cambia a una rama específica.

23. `git checkout -b nombre-rama`
    - Crea y cambia a una nueva rama.

24. `git merge nombre-rama`
    - Fusiona la rama especificada en la rama actual.

25. `git branch -m nombre-antiguo nombre-nuevo`
    - Renombra una rama.

---

## Sincronización con Repositorio Remoto
26. `git remote -v`
    - Lista las URLs de los remotos configurados.

27. `git remote add nombre URL`
    - Añade un nuevo repositorio remoto.

28. `git fetch remoto`
    - Descarga objetos y referencias de un repositorio remoto.

29. `git pull`
    - Actualiza tu rama local con las confirmaciones del remoto.

30. `git push`
    - Envía tus commits locales al repositorio remoto.

31. `git push -u origin nombre-rama`
    - Sube una rama y la configura para seguir una rama remota.

32. `git remote rename antiguo-nombre nuevo-nombre`
    - Renombra un repositorio remoto.

33. `git remote remove nombre`
    - Elimina un repositorio remoto.

---

## Inspección del Repositorio
34. `git log`
    - Muestra el historial de commits.

35. `git log --oneline`
    - Muestra el historial de commits en una línea por commit.

36. `git log --graph`
    - Muestra un gráfico ASCII del historial de ramas.

37. `git show commit`
    - Muestra los detalles de un commit específico.

38. `git blame archivo`
    - Muestra qué cambios se realizaron en un archivo y por quién.

39. `git reflog`
    - Muestra el historial de referencias (inclusive ramas eliminadas).

---

## Deshacer Cambios
40. `git revert commit`
    - Revierta un commit específico creando uno nuevo que lo deshaga.

41. `git reset --soft HEAD~1`
    - Deshace el último commit, pero mantiene los cambios en el área de preparación.

42. `git reset --hard HEAD~1`
    - Deshace el último commit y elimina los cambios.

43. `git checkout -- archivo`
    - Descartar cambios en un archivo específico.

44. `git clean -fd`
    - Elimina archivos no rastreados del directorio de trabajo.

---

## Stashing (Almacenamiento Temporal)
45. `git stash`
    - Guarda temporalmente los cambios no confirmados.

46. `git stash list`
    - Lista todos los stashs guardados.

47. `git stash apply`
    - Aplica los cambios del stash más reciente sin eliminarlo.

48. `git stash pop`
    - Aplica los cambios del stash más reciente y lo elimina de la lista.

49. `git stash drop`
    - Elimina un stash específico.

50. `git stash clear`
    - Elimina todos los stashs guardados.

---

## Etiquetas (Tags)
51. `git tag`
    - Lista todas las etiquetas en el repositorio.

52. `git tag nombre-tag`
    - Crea una nueva etiqueta.

53. `git tag -a nombre-tag -m "mensaje"`
    - Crea una etiqueta anotada.

54. `git tag -d nombre-tag`
    - Elimina una etiqueta local.

55. `git push origin nombre-tag`
    - Envía una etiqueta específica al remoto.

56. `git push origin --tags`
    - Envía todas las etiquetas al remoto.

---

## Rebase
57. `git rebase rama`
    - Rebasea la rama actual sobre otra rama.

58. `git rebase --abort`
    - Cancela un rebase en curso.

59. `git rebase --continue`
    - Continúa el proceso de rebase después de resolver conflictos.

60. `git rebase -i HEAD~n`
    - Rebase interactivo para los últimos `n` commits.

---

## Trabajo con Submódulos
61. `git submodule add URL ruta`
    - Añade un submódulo al repositorio.

62. `git submodule update --init`
    - Inicializa y actualiza los submódulos.

63. `git submodule foreach git pull origin master`
    - Actualiza todos los submódulos a la última versión.

64. `git submodule deinit ruta`
    - Desinicializa un submódulo.

65. `git submodule status`
    - Muestra el estado de los submódulos.

---

## Guardado y Restauración
66. `git archive --format=zip --output=archivo.zip HEAD`
    - Crea un archivo zip del estado actual del repositorio.

67. `git bisect start`
    - Inicia una búsqueda binaria para encontrar el commit que introdujo un bug.

68. `git bisect good commit`
    - Marca un commit como "bueno" durante un bisect.

69. `git bisect bad commit`
    - Marca un commit como "malo" durante un bisect.

70. `git bisect reset`
    - Finaliza el bisect y vuelve a la rama original.

---

## Manejo de Conflictos
71. `git merge --abort`
    - Cancela un merge en curso si hay conflictos.

72. `git diff --name-only --diff-filter=U`
    - Lista archivos con conflictos después de un merge.

73. `git log --merge`
    - Muestra los commits que causaron conflictos en un merge.

74. `git reset --merge`
    - Resetea la fusión (merge) pero deja los archivos sin modificar.

---

## Exclusión de Archivos
75. `echo "archivo" >> .gitignore`
    - Añade un archivo al `.gitignore`.

76. `git rm --cached archivo`
    - Elimina un archivo del repositorio pero lo mantiene en el directorio de trabajo.

77. `git check-ignore -v archivo`
    - Verifica si un archivo está siendo ignorado y por qué regla.

78. `git ls-files -i --exclude-standard`
    - Lista todos los archivos ignorados.

---

## Historial y Comparación
79. `git cherry-pick commit`
    - Aplica el cambio de un commit específico en la rama actual.

80. `git grep "texto"`
    - Busca una cadena de texto en el historial de commits.

81. `git shortlog`
    - Resumen del historial de commits, agrupado por autor.

82. `git log --since="2 weeks ago"`
    - Muestra el historial de commits desde una fecha específica.

83. `git log --author="nombre"`
    - Muestra el historial de commits de un autor específico.

84. `git diff HEAD~1 HEAD`
    - Compara cambios entre el commit anterior y el actual.

85. `git diff rama1 rama2`
    - Compara dos ramas.

86. `git diff --stat`
    - Muestra un resumen estadístico de los cambios.

---

## Optimización y Limpieza
87. `git gc`
    - Realiza una recolección de basura para optimizar el repositorio.

88. `git prune`
    - Elimina referencias no utilizadas.

89. `git fsck`
    - Verifica la integridad y busca problemas en el repositorio.

90. `git clean -n`
    - Muestra qué archivos no rastreados se eliminarían con `git clean`.

91. `git clean -f`
    - Elimina archivos no rastreados.

---

## Trabajo en Equipo
92. `git cherry`
    - Lista los commits que están en la rama actual y no en la rama objetivo.

93. `git fetch --all`
    - Descarga objetos y referencias de todos los remotos.

94. `git pull --rebase`
    - Actualiza la rama local y rebasea en lugar de fusionar.

95. `git push --force`
    - Fuerza un push al repositorio remoto, sobrescribiendo cambios.

96. `git push --force-with-lease`
    - Empuja de manera segura, verificando primero si la rama ha cambiado.

97. `git log --follow archivo`
    - Muestra el historial de un archivo, incluyendo cambios de nombre.

98. `git worktree add ruta rama`
    - Crea un nuevo árbol de trabajo (worktree) para una rama específica.

99. `git worktree list`
    - Lista todos los árboles de trabajo actuales.

100. `git worktree remove ruta`
    - Elimina un árbol de trabajo.

---

