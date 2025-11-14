# Instrucciones Sobre GIT
- Git es un sistema de control de versiones distribuido que permite a los desarrolladores colaborar en proyectos de software, En git todo es comprobado mediante un checksum antes de ser almacenado y a partir de ese momento es identificado con dicha suma, Etepa de controles es Working Directory -> Staging Area -> Repositorio.

## Ventajas de Git
- Control de versiones distribuido
- Colaboración en proyectos de software
- Seguimiento de cambios en archivos
- Ramas para trabajar en paralelo
- Repositorios remotos para compartir código
- Historial de cambios en los archivos
- Etiquetas para identificar versiones
- Integración con GitHub, GitLab, Bitbucket

## Métodologías de Trabajo con GIT FLOW y TRUNK BASED DEVELOPMENT

## Git Flow
- Es una metodología de trabajo con ramas que se basa en tener una rama principal (main) y ramas de soporte (feature, develop, release, hotfix).
- Ramas:
    - Main: Rama principal del repositorio
    - Develop: Rama de desarrollo
    - Feature: Rama de funcionalidad
    - Release: Rama de lanzamiento
    - Hotfix: Rama de corrección de errores
- Casos de Uso:
    - Govierno centralizado
    - Alta rotación en los equipos
    - Mayor número de desarrolladores
- Ventajas:
    - Organización de ramas
    - Control de versiones
    - Seguimiento de cambios
    - Integración continua
    - Despliegue continuo

## Trunk Based Developmen
- Es una metodología de trabajo con ramas que se basa en tener una rama principal (main) y ramas de soporte (feature).

## Configurar Credenciales
- git config --global user.name "example" : Configura el nombre de usuario
- git config --global user.email "example@vallegrande.edu.pe" : Configura el correo electrónico
- git config --list : Muestra la lista de configuraciones locales
- git config --global --list : Muestra la lista de configuraciones globales
- git config --global core.editor "vim" : Configura el editor de texto

## Crear un repositorio
- git init : Inicializa un repositorio en la carpeta actual
- git config --global init.defaultBranch main : Configura la rama principal como main
- git branch -M main : Cambia la rama principal a main

## Área de Staging: Archivos preparados para ser confirmados
- git add . : Agrega todos los archivos al Staging Area
- git add nombre_archivo : Agrega un archivo específico al Staging Area
- git add *.txt : Agrega todos los archivos con extensión .txt al Staging Area
- git add carpeta/ : Agrega todos los archivos de una carpeta al Staging Area
- git rm --cached nombre_archivo : Elimina un archivo del Staging Area
- git rm --force nombre_archivo : Elimina un archivo del Staging Area y del Working Directory

## git reset : el comando reset te devuelve a un commit anterior, eliminando los cambios en el historial como si nunca hubieran existido.
- git reset --soft HEAD~1 : Elimina el último commit pero mantiene todos sus cambios en el área de staging, listos para un nuevo commit
- git reset --mixed : Elimina el último commit y mueve los cambios del staging area al working directory
- git reset --hard : Elimina el último commit Y DESCARTA todos los cambios, tanto del área de staging como del directorio de trabajo
- git reset id_commit : Regresa a un commit específico
- git reset --hard HEAD~1 : Elimina el último commit y los cambios en el Working Directory 
- git reset --hard HEAD^ : ^ es equivalente a ~1 
- git reset --hard id_commit o name_tag : Elimina un commit específico
- git push --force-with-lease origin main : --force-with-lease permite forzar el envío, pero con una verificación adicional para evitar conflictos con otros cambios en el repositorio remoto.
- git push --force origin main : --force permite forzar el envío, pero sin verificar si hay otros cambios en el repositorio remoto.

## git revert : Crea un nuevo commit que revierte los cambios realizados por un commit específico.
- git revert HEAD : Revierte el último commit
- git revert HEAD~1 : Revierte el commit anterior
- git revert id_commit : Revierte un commit específico

## git restore : el comando restore te permite regresar los archivos a un estado anterior.
- git restore --staged nombre_archivo : Regresa un archivo al Working Directory
- git restore nombre_archivo : Regresa un archivo al estado anterior
- git restore . : Regresa todos los archivos al estado anterior
- git restore --source HEAD~1 nombre_archivo : Regresa un archivo al estado anterior del commit anterior

## stash : el comando stash te permite ocultar los cambios en el Working Directory para trabajar en otra tarea y luego recuperarlos.
- git stash : Oculta los cambios en el Working Directory
- git stash list : Muestra la lista de cambios ocultos
- git stash apply : Recupera los cambios ocultos
- git stash pop : Recupera y elimina los cambios ocultos
- git stash drop : Elimina los cambios ocultos

## log : el comando log te permite ver el historial de commits en el repositorio.
- git log : Muestra el historial de commits
- git log --oneline : Muestra el historial de commits en una línea
- git log --graph : Muestra el historial de commits en forma de gráfico
- git diff : Muestra las diferencias entre el Working Directory y el Staging Area
- git diff --staged : Muestra las diferencias entre el Staging Area y el repositorio
- git diff HEAD~1 : Muestra las diferencias entre el commit anterior y el Working Directory

## commit : el comando commit te permite guardar los cambios en el repositorio.
- git commit -m "Mensaje" : Confirma los archivos en el repositorio
- git commit -am "Mensaje" : Agrega y confirma los archivos en el repositorio
- git commit --amend -m "Mensaje" : Modifica el mensaje del último commit

## push : el comando push te permite subir los cambios al repositorio remoto.
- git push -u origin main : Sube los cambios al repositorio remoto por primera vez
- git push origin main : Sube los cambios al repositorio remoto
- git pull origin main : Descarga los cambios del repositorio remoto
- git fetch origin main : Descarga los cambios del repositorio remoto
- git log main..origin/main : Muestra los commits que faltan por subir al repositorio remoto
- git merge origin/main : Fusiona los cambios del repositorio remoto con el repositorio local

## ramas : el comando branch te permite crear y gestionar ramas en el repositorio.
- git branch : Muestra las ramas del repositorio
- git branch -a : Muestra todas las ramas del repositorio
- git branch -l : Muestra las ramas locales del repositorio
- git ls-remote --heads origin : Muestra las ramas remotas del repositorio 
- git branch -v : Muestra las ramas con los últimos commits
- git branch -r : Muestra las ramas remotas del repositorio y los que cree en el archivo .git/config
- git remote prune origin : Elimina las ramas remotas que ya no existen en el repositorio remoto
- git branch -vv : Muestra las ramas remotas con los últimos commits
- git branch nombre_rama : Crea una nueva rama 
- git checkout nombre_rama : Cambia a una rama existente o commit específico
- git checkout -b nombre_rama : Crea y cambia a una nueva rama
- git switch nombre_rama : Cambia a una rama existente
- git branch -d nombre_rama : Elimina una rama
- git branch -D nombre_rama : Elimina una rama forzadamente
- git branch --merged : Muestra las ramas fusionadas
- git branch --no-merged : Muestra las ramas no fusionadas
- git branch -d nombre_rama : Elimina una rama fusionada
- git push origin --delete nombre_rama : Elimina una rama del repositorio remoto
- git branch -d nombre_rama : Elimina una rama del repositorio local

## switch : el comando switch te permite cambiar entre ramas y commits.
git switch -c nombre_rama -> Crea y cambia a una nueva rama
git switch nombre_rama -> Cambia a una rama existente
git switch -c nombre_rama origin/nombre_rama -> Crea una rama local a partir de una rama remota
git switch --detach nombre_commit -> Cambia a un commit específico
git switch --discard -> Descarta los cambios en el Working Directory

## merge : el comando merge te permite fusionar los cambios de una rama con otra.
- git merge nombre_rama : Fusiona los cambios de una rama con la rama actual
- git merge --no-ff : Fusiona los cambios de una rama con otra sin avance rápido
- git merge --squash : Fusiona los cambios de una rama con otra en un solo commit
- git merge --abort : Cancela la fusión de los cambios de una rama con otra
- git merge nombre_rama -m "feat: add new feature button cancel" : Fusiona los cambios de una rama con la rama actual y agrega un mensaje al commit



** Tag **
--- Un tag es como una etiqueta que puedes aplicar a un commit para identificarlo fácilmente en el futuro.
git tag -> Muestra los tags del repositorio
- git tag -a nombre_tag -m "Mensaje" : -a es para crear un tag anotado y -m es para agregar un mensaje
git tag -d nombre_tag -> Elimina un tag
git tag nombre_tag id_commit -> Crea un tag en un commit específico
git ls-remote --tags origin -> Muestra los tags remotos

git show nombre_tag -> Muestra la información de un tag
git push origin nombre_tag -> Sube un tag al repositorio remoto
git push origin --tags -> Sube todos los tags al repositorio remoto

** ver tag remoto **

** Github Flow **
Es un flujo de trabajo basado en ramas que se utiliza en GitHub para colaborar en proyectos de código abierto.
Main -> crear una rama feature de rama main -> hacer cambios en la rama feature -> abrir un pull request -> revisar y aprobar el pull request -> fusionar la rama feature con la rama main -> eliminar la rama feature

## Ramas de apoyo
- feature : Estas ramas tienen que surgir de la rama develop y deben ser utilizadas para desarrollar nuevas funcionalidades.
- release : Estas ramas también surgen de la rama develop, contienen los cambios que se van a liberar en producción.
- hotfix : Estas ramas se utilizan para corregir errores críticos en producción, incluyendo las ramas main, develop y feature.

### Comandos Para Git Flow
git switch -c develop 
git switch -c feature/0001-nombre_feature 
git add . 
git commit -m "feat: add new feature button cancel"
git push -u origin feature/0001-create-button-cancel 
git switch develop 
git pull origin develop
git merge feature/0001-create-button-cancel -m "feat: add new feature button cancel"
git push origin develop
git branch -d feature/0001-create-button-cancel 

### Conventional Commits
- Nos permite estandarizar los mensajes de los commits para que sean más descriptivos y fáciles de entender, siguiendo un formato específico.
- Tipos de commits:
    - feat: Nueva funcionalidad
    - fix: Corrección de errores
    - docs: Cambios en la documentación
    - style: Cambios en el estilo del código
    - refactor: Refactorización del código
    - test: Cambios en las pruebas
    - chore: Tareas de mantenimiento
    - build: Cambios en la configuración del proyecto
    - ci: Cambios en la configuración de integración continua
- Estructura del mensaje con ejemplos:
    <tipo_commit>(alcance): <mensaje> [opcional: cuerpo] [opcional: pie de página]
    
    - feat: add new feature button component (#123) 
    - fix: resolve issue with login form validation (#456)
    - docs: update README with installation instructions (#789)
    - style: change color of header background (#012)
    - refactor: extract common logic to utils file (#345)
    - test: add unit tests for login form (#678)
    - chore: update dependencies to latest version (#901)
Commit Type	Title	Description	Emoji
feat	Features	A new feature	✨
fix	Bug Fixes	A bug Fix	🐛
docs	Documentation	Documentation only changes	📝
style	Styles	Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)	🎨
refactor	Code Refactoring	A code change that neither fixes a bug nor adds a feature	♻️
perf	Performance Improvements	A code change that improves performance	⚡
test	Tests	Adding missing tests or correcting existing tests	✅
build	Builds	Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)	📦️
ci	Continuous Integrations	Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs)	👷
chore	Chores	Other changes that don't modify src or test files	🔧
revert	Reverts	Reverts a previous commit	⏪️
---
convention:
  commitTypes:
  - feat     # Commits, that add or remove a new feature to the API or UI
  - fix      # Commits, that fix a API or UI bug of a preceded feat commit
  - refactor # Commits, that rewrite/restructure your code, however do not change any API or UI behaviour
  - perf     # Commits are special `refactor` commits, that improve performance
  - style    # Commits, that do not affect the meaning (white-space, formatting, missing semi-colons, etc)
  - test     # Commits, that add missing tests or correcting existing tests
  - build    # Commits, that affect build components like build tool, ci pipeline, dependencies, project version, ...
  - ops      # Commits, that affect operational components like infrastructure, deployment, backup, recovery, ...
  - docs     # Commits, that affect documentation only 
  - chore    # Miscellaneous commits e.g. modifying `.gitignore`
  - docs
  - merge
  commitScopes: []
  releaseTagGlobPattern: v[0-9]*.[0-9]*.[0-9]*
changelog:
  commitTypes:
  - feat
  - fix
  - perf
  - merge
  includeInvalidCommits: true
  commitScopes: []
  commitIgnoreRegexPattern: "^WIP "
  headlines:
    feat: Features
    fix: Bug Fixes
    perf: Performance Improvements
    merge: Merges
    breakingChange: BREAKING CHANGES
  commitUrl: https://github.com/qoomon/git-conventional-commits/commit/%commit%
  commitRangeUrl: https://github.com/qoomon/git-conventional-commits/compare/%from%...%to%?diff=split
  issueRegexPattern: "#[0-9]+"
  issueUrl: https://github.com/qoomon/git-conventional-commits/issues/%issue%

ypes of Commit
feat: A new feature for the user or system
Example: feat(auth): add Google login feature

fix: A bug fix for the user or system
Example: fix(button): resolve issue with button hover state

chore: Routine tasks like maintenance or updating dependencies
Example: chore(deps): update react to version 17.0.2

docs: Documentation updates
Example: docs(readme): update installation instructions

style: Changes related to code style (e.g., formatting, missing semi-colons)
Example: style(button): fix button alignment in CSS

refactor: Code change that neither fixes a bug nor adds a feature
Example: refactor(auth): simplify login form validation logic

test: Adding or updating tests
Example: test(auth): add unit tests for login function

build: Changes that affect the build system or external dependencies
Example: build(webpack): add webpack config for production build

ci: Continuous integration-related changes
Example: ci(gitlab): update CI config for deployment pipeline

perf: Code changes that improve performance Example: perf(api): optimize database queries for faster responses

env: Changes related to environment setup or configuration Example: env(docker): update Dockerfile for staging environment

sec: Security fixes or improvements Example: sec(auth): add encryption for user passwords

config: Changes to configuration files Example: config: update .eslint rules for stricter code checks

api: Updates to API contracts or integrations Example: api(user): add new endpoint for user profile updates

Additional Commit Types
revert: Reverts a previous commit

Example: revert(auth): rollback Google login feature

merge: Indicates a merge commit

Example: merge: branch 'feature/auth' into 'main'

deps: Dependency-specific updates

Example: deps: bump axios from 0.21.1 to 0.24.0

design: UI or UX improvements

Example: design(button): update hover effect

** si el nombre del repositorio es diferente al nombre del repositorio remoto **
git remote set-url origin url_repositorio -> Cambia la URL del repositorio remoto

** listar los repositorios remotos **
git remote -v -> Muestra los repositorios remotos

** subir una rama al repositorio remoto **
git push origin nombre_rama -> Sube una rama al repositorio remoto



### Multiples Repositorios Remotos
- Múltiples repositorios remotos se utilizan para colaborar en proyectos con diferentes equipos o empresas.
git remote add myCompany https://github.com/MichaellIbarra/customerback.git
git remote -v -> Muestra los repositorios remotos
git push origin2 main -> Sube los cambios al repositorio remoto de la empresa
git pull myCompany main -> Descarga los cambios del repositorio remoto de la empresa
git remote remove myCompany -> Elimina el repositorio remoto de la empresa
git remote set-url origin url_repositorio -> Cambia la URL del repositorio remoto
git remote rename origin myCompany -> Cambia el nombre del repositorio remoto

### Fork
- Un fork es una copia de un repositorio remoto en un repositorio propio.
- Casos de uso:
    - Contribuir a proyectos de código abierto
    - Realizar cambios en un proyecto sin afectar el repositorio original
    - Crear una versión personalizada de un proyecto


## Comandos Comunes de Linux para Git
- ls : lista los archivos y directorios
- cd : cambia de directorio
- mkdir : crea un directorio
- touch : crea un archivo vacío
- cp : copia archivos y directorios
- mv : mueve archivos y directorios
- rm : elimina archivos y directorios
- cat : muestra el contenido de un archivo
- less : muestra el contenido de un archivo página por página
- grep : busca texto en un archivo

## Comandos para el editor VIM
- i : Insertar texto
- :q -> Salir
- :q! -> Salir sin guardar
- :wq -> Guardar y salir
- dd -> Eliminar línea
- yy -> Copiar línea
- p -> Pegar línea
- u -> Deshacer
- Ctrl + r -> Rehacer
- /palabra -> Buscar palabra
- n -> Siguiente
- N -> Anterior


** Conexión Remota con SSH **
--  Beneficios de usar ssh en lugar de https para la conexión remota con GitHub:
- la seguridad de ssh se basa en la clave pública y privada, mientras que https se basa en el nombre de usuario y la contraseña.

ssh-keygen -t ed25519 -C "michaell.ibarra@vallegrande.edu.pe" -> Genera una nueva clave SSH
eval "$(ssh-agent -s)" -> Inicia el agente SSH en segundo plano 
ssh-add ~/.ssh/id_ed25519 -> Agrega la clave SSH al agente SSH
cat ~/.ssh/id_ed25519.pub -> Muestra la clave pública SSH 
ssh -T git@github.com -> Prueba la conexión SSH con GitHub
git clone 

## configurar el code . en la terminal
configura el editor de texto específicamente de visual studio code para que se abra al ejecutar el comando code . en la terminal
git config --global core.editor "code --wait" -> Configura Visual Studio Code como editor de texto por defecto
## para editor sublime text
git config --global core.editor "subl -w" -> Configura Sublime Text como editor de texto por defecto


git init
git add .
git commit -m "chore(credit): inizialize banking credit service"
git branch -M main
git remote add origin https://token@github.com/mqcdev/banking-credit-service.git
git push -u origin main
** uso de configurar el .git local solo para un repositorio **
git config user.name "example" -> Configura el nombre de usuario solo para el repositorio actual
git config user.email "example@MichaellIbarra.com" -> Configura el correo electrónico solo para el repositorio actual
git config --list --local -> Muestra la lista de configuraciones locales
** configurar el remoto para un repositorio **
git remote set-url origin https://<TOKEN>@github.com/mqcdev/banking-account-service.git
git remote set-url origin https://token@github.com/mqcdev/banking-account-service.git
https://github.com/mqcdev/banking-customer-service.git
https://token@github.com/mqcdev/banking-customer-service.git
https://github.com/mqcdev/banking-eureka-service.git


## Términos comunes en Git
- Working Directory: Directorio de trabajo
- Staging Area: Área de preparación
- Repository: Lugar donde se almacenan los archivos y el historial de cambios
- Branch: Es una copia de la rama principal en la que se pueden hacer cambios sin afectar la rama principal.
- Commit: Es un conjunto de cambios en los archivos que se guardan en el repositorio.
- HEAD: Puntero a la rama actual en la que se encuentra el usuario.
- Origin: Repositorio remoto por defecto
- Remote: Es la conexión con un repositorio remoto
- Clone: clona un repositorio remoto en un repositorio local
- Fork: Bifurcación de un repositorio remoto en un repositorio propio
- Bifurcación : Es una copia de un repositorio remoto en un repositorio propio
- Merge: Fusionar cambios de una rama con otra
- Rebase: Reorganizar los commits de una rama
- Tag: Etiqueta se aplica en cualquier linea del tiempo, se suele usar para marcar un hito en el proyecto
- Conflict: Conflicto que ocurre cuando dos ramas tienen cambios en las mismas líneas de un archivo
- Stash: Ocultar los cambios en el Working Directory
- Checkout: Revisar un commit, rama o tag
- Reflog: Registro de referencia de los cambios realizados en el repositorio
- Fast-Forward: Avance rápido es una fusión que se puede realizar sin problemas porque no hay cambios en la rama base desde que se creó la rama que se va a fusionar.
- No Fast-Forward: No es posible hacer un avance rápido porque hay cambios en la rama base desde que se creó la rama que se va a fusionar.
- --set-upstream: Establecer la rama remota como rama de seguimiento de la rama local.
- ciclo de vida de ramas : Rama principal su ciclo de vida es largo ya que nace y se mantiene durante todo el proyecto, Rama de ciclo de vida corto nace con un objetivo específico y muere al cumplir su objetivo.
- rama main : Es la rama principal de un repositorio, donde se encuentran los cambios estables del proyecto.
- rama develop : Es una rama de desarrollo donde se integran los cambios de las ramas feature antes de ser fusionados con la rama main.
- rama feature : Es una rama que se crea para desarrollar una nueva funcionalidad del proyecto.
- rama release : Es una rama que se crea para preparar la versión del proyecto que se va a lanzar.
- rama hotfix : Es una rama que se crea para corregir errores críticos en producción.
- ciclo de ramas : main -> (develop | hotfix) -> feature -> release
- pull request : Es una solicitud de extracción que se crea para fusionar los cambios de una rama con otra.
- merge request : Es una solicitud de fusión que se crea para fusionar los cambios de una rama con otra.

## Recursos
https://github.com/stevemao/github-issue-templates -> Plantillas de issues
https://github.com/fossapps/Handlebars-Issue-and-Pull-Requests/tree/master/.github
https://github.com/Josee9988/project-template?tab=readme-ov-file -> Plantillas de proyectos
https://github.com/Fernanda-Kipper/Readme-Templates
https://github.com/embeddedartistry/templates/tree/master
https://github.com/im-luka/markdown-cheatsheet/tree/main
https://github.com/homebridge/.github/tree/latest
https://gitmoji.dev/

1. Inicia un rebase interactivo
Dado que el commit que quieres modificar es el tercero más reciente (contando desde HEAD), necesitarás hacer:
pick e3581ff feat(account): configure WebClient for external service communication
pick 8d7ceee feat(dto): create ClientDTO for client data transfer
pick 3c1404d feat(models): add BankAccount and Transaction entities
pick c0e09da feat(account): configure WebClient for external service communication

pick e3581ff feat(account): configure WebClient for external service communication
reword 8d7ceee feat(dto): create ClientDTO for client data transfer
pick 3c1404d feat(models): add BankAccount and Transaction entities
pick c0e09da feat(account): configure WebClient for external service communication

feat(dto): implement ClientDTO for customer data representation

