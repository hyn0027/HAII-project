# HAII-project

## Code structure

This project is a web application composed of two separate repositories: a backend (Django REST server) and a frontend (Next.js web application).

### Running the Application

#### Backend

```bash
cd HAII-project-backend

pip install -r requirements.txt

cd backend

python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

### Frontend

```bash
cd HAII-project-frontend/frontend

npm install
npm run build
npm run start
```

## Use of External Code

No external code was reused beyond standard open-source dependencies.

- Backend dependencies: <https://github.com/hyn0027/HAII-project-backend/blob/fcdbc58cd7a752e62f444b353067e87f36b7c323/requirements.txt￼>
- Frontend dependencies: <https://github.com/hyn0027/HAII-project-frontend/blob/bf792157d9edc9879d157d75b182685f0d3ef2eb/frontend/package.json￼>

Overview:

- Backend: Django-based REST API built in Python, integrating the OpenAI Chat Completions API.
- Frontend: Next.js with React and TypeScript. UI components and styling use Mantine, Tailwind CSS, and Lucide icons.
