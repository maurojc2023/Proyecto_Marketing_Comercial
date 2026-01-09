# GUÍA: SUBIR REPOSITORIO A GITHUB
## Smart Graphics Solutions - Proyecto 2026

**Versión**: 1.0
**Fecha**: Enero 2026
**Repositorio local**: `/Users/smart-yellotools/Documents/smart-graphics-2026`

---

## PREREQUISITOS

Antes de comenzar, asegúrate de tener:

1. **Git instalado** en tu computadora
   - Verificar: Abre Terminal y escribe `git --version`
   - Si no está instalado: [Descargar Git](https://git-scm.com/downloads)

2. **Cuenta en GitHub.com**
   - Si no tienes: [Crear cuenta gratis](https://github.com/signup)

3. **Configuración básica de Git** (primera vez solamente)
   ```bash
   git config --global user.name "Tu Nombre"
   git config --global user.email "tu-email@ejemplo.com"
   ```

---

## PASO A PASO: SUBIR REPOSITORIO A GITHUB

### PASO 1: Inicializar repositorio Git local

Abre Terminal y navega a la carpeta del proyecto:

```bash
cd /Users/smart-yellotools/Documents/smart-graphics-2026
```

Inicializa Git en esta carpeta:

```bash
git init
```

**Resultado esperado**:
```
Initialized empty Git repository in /Users/smart-yellotools/Documents/smart-graphics-2026/.git/
```

---

### PASO 2: Crear archivo .gitignore

Antes de agregar archivos, crea un `.gitignore` para excluir archivos innecesarios:

```bash
cat > .gitignore << 'EOF'
# macOS
.DS_Store
.AppleDouble
.LSOverride

# Thumbnails
._*

# Files that might appear in the root of a volume
.DocumentRevisions-V100
.fseventsd
.Spotlight-V100
.TemporaryItems
.Trashes
.VolumeIcon.icns
.com.apple.timemachine.donotpresent

# Directories potentially created on remote AFP share
.AppleDB
.AppleDesktop
Network Trash Folder
Temporary Items
.apdisk

# Node modules (si usas Node.js)
node_modules/
npm-debug.log*

# Environment variables
.env
.env.local
.env.*.local

# IDEs
.vscode/
.idea/
*.swp
*.swo
*~

# Logs
logs/
*.log

# Temporary files
tmp/
temp/
*.tmp

# Credentials y archivos sensibles
credentials.json
secrets.json
config.private.json

# Backups
*.bak
*.backup
EOF
```

---

### PASO 3: Agregar todos los archivos al staging

```bash
git add .
```

**Este comando agrega TODOS los archivos del directorio (excepto los que están en .gitignore)**

Verificar qué archivos se agregaron:

```bash
git status
```

**Resultado esperado**: Lista de archivos en verde (listos para commit)

---

### PASO 4: Crear el primer commit

```bash
git commit -m "Initial commit: Estrategia Digital-First 2026 Smart Graphics Solutions"
```

**Resultado esperado**:
```
[main (root-commit) abc1234] Initial commit: Estrategia Digital-First 2026 Smart Graphics Solutions
 X files changed, XXXX insertions(+)
 create mode 100644 CLAUDE.md
 create mode 100644 GIT.md
 create mode 100644 estrategia-integrada/ESTRATEGIA_DIGITAL_FIRST_2026.md
 ...
```

---

### PASO 5: Crear repositorio en GitHub.com

1. **Ve a GitHub.com** y haz login

2. **Haz clic en el botón "+" (arriba derecha) → "New repository"**

3. **Configura el repositorio**:
   - **Repository name**: `smart-graphics-2026` (o el nombre que prefieras)
   - **Description**: "Estrategia Digital-First 2026 - Smart Graphics Solutions - 4 Productos SaaS"
   - **Visibilidad**:
     - ✅ **Private** (recomendado - información estratégica confidencial)
     - ⚠️ Public (solo si quieres que sea visible para todos)
   - **NO marcar**: "Initialize this repository with a README" (ya tienes archivos locales)

4. **Haz clic en "Create repository"**

---

### PASO 6: Conectar repositorio local con GitHub

Copia la URL de tu repositorio GitHub (aparece después de crearlo).

**Opción A: HTTPS (recomendado para principiantes)**

```bash
git remote add origin https://github.com/TU-USUARIO/smart-graphics-2026.git
```

**Opción B: SSH (requiere configuración previa de claves SSH)**

```bash
git remote add origin git@github.com:TU-USUARIO/smart-graphics-2026.git
```

**Reemplaza `TU-USUARIO` con tu nombre de usuario de GitHub**

Verificar conexión:

```bash
git remote -v
```

**Resultado esperado**:
```
origin  https://github.com/TU-USUARIO/smart-graphics-2026.git (fetch)
origin  https://github.com/TU-USUARIO/smart-graphics-2026.git (push)
```

---

### PASO 7: Renombrar rama a "main" (si es necesario)

GitHub usa "main" como rama principal. Verifica tu rama actual:

```bash
git branch
```

Si dice `master`, renombrar a `main`:

```bash
git branch -M main
```

---

### PASO 8: Subir archivos a GitHub (PUSH)

```bash
git push -u origin main
```

**Si usas HTTPS**, te pedirá credenciales:
- **Username**: tu usuario de GitHub
- **Password**:
  - ⚠️ **NO uses tu contraseña de GitHub** (ya no funciona)
  - ✅ **Usa un Personal Access Token** (ver sección siguiente si no tienes uno)

**Resultado esperado**:
```
Enumerating objects: XX, done.
Counting objects: 100% (XX/XX), done.
Delta compression using up to 8 threads
Compressing objects: 100% (XX/XX), done.
Writing objects: 100% (XX/XX), XXX KiB | XXX MiB/s, done.
Total XX (delta X), reused 0 (delta 0)
To https://github.com/TU-USUARIO/smart-graphics-2026.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

---

### PASO 9: Verificar en GitHub.com

1. Ve a `https://github.com/TU-USUARIO/smart-graphics-2026`
2. Deberías ver todos tus archivos subidos
3. El archivo CLAUDE.md debería ser visible
4. La estructura de carpetas debería estar intacta

---

## CREAR PERSONAL ACCESS TOKEN (Si lo necesitas)

Si GitHub rechaza tu contraseña al hacer `git push`, necesitas un Personal Access Token:

### Pasos:

1. **Ve a GitHub.com** → Settings (tu perfil, arriba derecha)

2. **Developer settings** (menú izquierdo, abajo del todo)

3. **Personal access tokens** → **Tokens (classic)**

4. **Generate new token** → **Generate new token (classic)**

5. **Configuración del token**:
   - **Note**: "Smart Graphics 2026 - Laptop"
   - **Expiration**: 90 days (o más, según prefieras)
   - **Scopes**: Marca ✅ **repo** (acceso completo a repositorios)

6. **Generate token**

7. **COPIA EL TOKEN** (solo se muestra UNA VEZ)
   - Ejemplo: `ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx`

8. **Guarda el token en un lugar seguro** (gestor de contraseñas)

### Usar el token:

Cuando Git pida contraseña, pega el token (no tu contraseña de GitHub).

**Opcional - Guardar credenciales** (para no escribir el token cada vez):

```bash
git config --global credential.helper osxkeychain
```

La próxima vez que hagas `git push`, macOS guardará el token en el Keychain.

---

## COMANDOS ÚTILES PARA EL DÍA A DÍA

### Ver estado del repositorio

```bash
git status
```

Muestra:
- Archivos modificados
- Archivos nuevos
- Archivos listos para commit

---

### Agregar cambios nuevos

**Agregar archivo específico**:
```bash
git add nombre-archivo.md
```

**Agregar todos los cambios**:
```bash
git add .
```

---

### Crear commit (guardar cambios)

```bash
git commit -m "Descripción clara de los cambios"
```

**Ejemplos de buenos mensajes**:
- `git commit -m "Actualizar estrategia de contenido para Febrero"`
- `git commit -m "Agregar plan de ventas Q1 2026"`
- `git commit -m "Corregir typos en documento de marketing"`

---

### Subir cambios a GitHub

```bash
git push
```

(No necesitas `-u origin main` después del primer push)

---

### Descargar cambios desde GitHub

Si trabajas desde otra computadora o alguien más actualizó el repositorio:

```bash
git pull
```

---

### Ver historial de commits

```bash
git log
```

**Versión compacta**:
```bash
git log --oneline
```

---

### Ver diferencias antes de commit

```bash
git diff
```

---

### Deshacer cambios (ANTES de commit)

**Deshacer cambios en un archivo específico**:
```bash
git checkout -- nombre-archivo.md
```

**Quitar archivo del staging (antes de commit)**:
```bash
git reset nombre-archivo.md
```

---

## WORKFLOW DIARIO RECOMENDADO

### Cada vez que modifiques archivos:

```bash
# 1. Ver qué cambió
git status

# 2. Agregar cambios
git add .

# 3. Commit con mensaje descriptivo
git commit -m "Descripción de cambios"

# 4. Subir a GitHub
git push
```

---

## ESTRUCTURA RECOMENDADA DE COMMITS

### Frecuencia:

- **Diario**: Commit al final del día con cambios del día
- **Por tarea**: Commit cuando completes una tarea específica
- **Antes de cambios grandes**: Commit para tener punto de restauración

### Buenos mensajes de commit:

✅ **BIEN**:
- "Agregar calendario de contenido Enero 2026"
- "Actualizar pricing Agente Chat IA"
- "Corregir errores en plan de ventas B2B"
- "Documentar proceso de onboarding clientes"

❌ **MAL**:
- "cambios"
- "update"
- "fix"
- "asdf"

---

## TRABAJAR EN EQUIPO

### Clonar repositorio en otra computadora:

```bash
git clone https://github.com/TU-USUARIO/smart-graphics-2026.git
cd smart-graphics-2026
```

---

### Sincronizar antes de trabajar (importante):

**Siempre antes de empezar a trabajar**:
```bash
git pull
```

**Después de trabajar**:
```bash
git add .
git commit -m "Descripción"
git push
```

---

### Resolver conflictos (si aparecen):

Si dos personas modifican el mismo archivo:

1. Git mostrará error al hacer `git pull`
2. Abre el archivo con conflicto
3. Verás marcadores como:
   ```
   <<<<<<< HEAD
   Tu versión
   =======
   Versión del servidor
   >>>>>>> abc1234
   ```
4. Edita manualmente para quedarte con la versión correcta
5. Elimina los marcadores `<<<<<<<`, `=======`, `>>>>>>>`
6. Guarda el archivo
7. Haz commit:
   ```bash
   git add .
   git commit -m "Resolver conflicto en archivo X"
   git push
   ```

---

## BUENAS PRÁCTICAS

### 1. Commit frecuente
- No esperes días para hacer commit
- Mejor muchos commits pequeños que uno gigante

### 2. Mensajes descriptivos
- Explica QUÉ cambiaste y POR QUÉ
- Futuro tú te lo agradecerá

### 3. Pull antes de Push
- Siempre `git pull` antes de empezar a trabajar
- Evita conflictos

### 4. No commitear archivos sensibles
- Contraseñas, tokens, credenciales → NUNCA
- Usa .gitignore para excluirlos

### 5. Backup regularmente
- GitHub es tu backup en la nube
- Haz `git push` diario mínimo

---

## COMANDOS DE EMERGENCIA

### "Cometí un error en el último commit"

**Si NO has hecho push todavía**:
```bash
# Deshacer último commit pero mantener cambios
git reset --soft HEAD~1

# Hacer cambios necesarios
# Luego commit de nuevo
git add .
git commit -m "Mensaje corregido"
```

---

### "Quiero volver a una versión anterior"

```bash
# Ver historial
git log --oneline

# Volver a commit específico (SIN borrar commits posteriores)
git revert COMMIT-ID

# O crear rama nueva desde commit antiguo
git checkout -b nueva-rama COMMIT-ID
```

---

### "Borré archivos por error"

**Si NO has hecho commit**:
```bash
git checkout -- nombre-archivo.md
```

**Si YA hiciste commit**:
```bash
git log --all --full-history -- nombre-archivo.md
git checkout COMMIT-ID -- nombre-archivo.md
```

---

## RESUMEN: PRIMEROS PASOS (CHECKLIST)

- [ ] 1. Verificar Git instalado: `git --version`
- [ ] 2. Configurar nombre y email (primera vez)
- [ ] 3. `cd /Users/smart-yellotools/Documents/smart-graphics-2026`
- [ ] 4. `git init`
- [ ] 5. Crear `.gitignore`
- [ ] 6. `git add .`
- [ ] 7. `git commit -m "Initial commit"`
- [ ] 8. Crear repositorio en GitHub.com (Private)
- [ ] 9. `git remote add origin URL-DEL-REPO`
- [ ] 10. `git branch -M main`
- [ ] 11. `git push -u origin main`
- [ ] 12. Verificar en GitHub.com que archivos subieron

---

## RECURSOS ADICIONALES

### Documentación oficial:
- **Git**: https://git-scm.com/doc
- **GitHub**: https://docs.github.com

### Tutoriales visuales:
- **GitHub Desktop** (alternativa gráfica, sin comandos): https://desktop.github.com
- **GitKraken** (otra alternativa gráfica): https://www.gitkraken.com

### Cheat Sheet:
- https://education.github.com/git-cheat-sheet-education.pdf

---

## SOPORTE

### Si tienes problemas:

1. **Error de autenticación**:
   - Verifica que usas Personal Access Token (no contraseña)
   - Regenera token si es necesario

2. **Error "permission denied"**:
   - Verifica que tienes permisos en el repositorio
   - Verifica que la URL del remote es correcta

3. **Conflictos de merge**:
   - Lee los marcadores en el archivo
   - Edita manualmente
   - Haz commit después de resolver

4. **"Repository not found"**:
   - Verifica la URL: `git remote -v`
   - Corrige: `git remote set-url origin URL-CORRECTA`

---

**¡Éxito con tu repositorio! 🚀**

---

**Fin del documento**
