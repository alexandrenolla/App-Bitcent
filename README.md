<p align="center">

 ## 💻 Project

Web application for personal finance control with landing page and dashboard. The project uses Firebase for authentication and data storage.

Project was developed during Cod3r's bootcamp, which took place on May 8-14, 2023.
</p>

## Technologies

List of technologies used in the project:

- [React](https://reactjs.org)
- [Next.js](https://nextjs.org/)
- [Firebase](https://firebase.google.com/)
- [TypeScript](https://www.typescriptlang.org/)
- [TailwindCSS](https://tailwindcss.com/)
- [Mantine](https://mantine.dev/)

## Running the project

1. Clone the repository:

```bash
$ git clone https://github.com/alexandrenolla/App-Bitcent
$ cd Web-App-Bitcent
```


2. Create a project in Firebase and enable Firestore and Google Authentication.

- Firestore permissions:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
    	allow read, write: if false;
    }

    match /financas/{email}/transacoes/{id} {
  		allow read: if (request.auth != null && request.auth.token.email == email);
      allow write: if (request.auth != null && request.auth.token.email == email);
    }
    
    match /usuarios/{email} {
  		allow read: if (request.auth != null && request.auth.token.email == email);
      allow write: if (request.auth != null && request.auth.token.email == email);
    }
  }
}
```





3. You need to create a `.env.local` file in the project root with the following variables:

```bash
NEXT_PUBLIC_FIREBASE_PROJECT_ID=
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=
NEXT_PUBLIC_FIREBASE_API_KEY=
```
Use your project's Firebase credentials.

4. Inside the project folder, run the following commands:

```bash
# Install the dependencies
$ npm install

# Start the project
$ npm run dev
```
The app will be available at http://localhost:3000.
