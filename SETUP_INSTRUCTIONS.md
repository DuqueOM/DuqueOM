# Instrucciones para Configurar tu Perfil de GitHub

## ¿Qué es el README de Perfil de GitHub?

GitHub tiene una función especial: si creas un repositorio con **exactamente tu mismo nombre de usuario**, el `README.md` de ese repo se muestra en tu perfil público.

Tu usuario es `DuqueOM`, así que necesitas crear el repo `DuqueOM/DuqueOM`.

---

## Pasos para Configurar

### 1. Crear el Repositorio Especial

```bash
# Desde tu terminal, crea el nuevo repositorio
cd ~/projects
mkdir DuqueOM
cd DuqueOM
git init
```

### 2. Copiar el README

Copia el archivo `README.md` que creamos:

```bash
cp ~/projects/ML-MLOps-Portfolio/docs/github-profile/README.md ./README.md
```

### 3. Hacer el Primer Commit

```bash
git add README.md
git commit -m "feat: add GitHub profile README"
```

### 4. Crear el Repo en GitHub

1. Ve a [github.com/new](https://github.com/new)
2. Nombre del repositorio: `DuqueOM` (exactamente igual a tu username)
3. Descripción: `My GitHub profile`
4. Selecciona **Public**
5. **NO** inicialices con README (ya lo tienes)
6. Click en **Create repository**

### 5. Configurar el Token de Métricas (Vital para los gráficos)

Para que los gráficos de estadísticas funcionen y no se rompan (como pasaba con Vercel), usamos un **GitHub Action** que requiere permisos.

1.  Ve a **Settings** (de tu usuario) -> **Developer settings** -> **Personal access tokens** -> **Tokens (classic)**.
2.  Click **Generate new token (classic)**.
3.  Ponle de nombre: `METRICS_TOKEN`.
4.  Selecciona los permisos (scopes):
    *   `public_repo` (o `repo` si quieres contar commits privados)
    *   `read:user`
    *   `read:org`
5.  Click **Generate token** y **copia el código** (empieza con `ghp_...`).
6.  Ahora ve a tu **Repositorio DuqueOM** -> **Settings** -> **Secrets and variables** -> **Actions**.
7.  Click **New repository secret**.
8.  Name: `METRICS_TOKEN`.
9.  Secret: Pega el código que copiaste.
10. Click **Add secret**.

### 6. Conectar y Subir

```bash
git remote add origin https://github.com/DuqueOM/DuqueOM.git
git branch -M main
git push -u origin main
```

### 6. Verificar

Ve a [github.com/DuqueOM](https://github.com/DuqueOM) y deberías ver tu nuevo README renderizado en tu perfil.

---

## Mantenimiento

### Mantén tu Perfil Activo

- **Commits regulares:** Haz al menos 1-2 commits por semana en cualquier repo para mantener tu gráfica de contribuciones verde.
- **Actualiza el README:** Cuando obtengas la certificación AWS, actualízalo.
- **Pinea tu portafolio:** En tu perfil de GitHub, asegúrate de que `ML-MLOps-Portfolio` esté "pinned" (fijado) como primer repositorio.

### Cómo Pinear Repositorios

1. Ve a tu perfil: [github.com/DuqueOM](https://github.com/DuqueOM)
2. Click en **Customize your pins**
3. Selecciona `ML-MLOps-Portfolio` como el primero
4. Guarda

---

## Notas sobre las Estadísticas

El README usa servicios externos para mostrar estadísticas:

- **GitHub Stats:** `github-readme-stats.vercel.app` - Muestra tus estadísticas generales
- **Top Languages:** Muestra los lenguajes más usados en tus repos
- **Streak Stats:** Muestra tu racha de commits

Estos servicios son gratuitos y se actualizan automáticamente.

---

## Certificación AWS - Recomendación

**Certificación recomendada:** AWS Solutions Architect – Associate (SAA-C03)

**¿Por qué esta y no la Cloud Practitioner?**
- Cloud Practitioner es muy básica (nivel comercial/ventas)
- Solutions Architect Associate demuestra conocimiento técnico real de arquitectura
- Es el estándar de la industria para roles de infraestructura/DevOps/MLOps
- Los reclutadores técnicos la respetan más

**Recursos para estudiar:**
1. AWS Skill Builder (gratis): https://skillbuilder.aws/
2. Stephane Maarek en Udemy (curso más popular)
3. Tutorials Dojo (practice exams)

**Costo del examen:** ~$150 USD

**Tiempo de preparación:** 4-6 semanas estudiando 2-3 horas diarias
