Full-Stack Image Processing PipelineThis project is a modern, full-stack application built for efficient image handling, storage, and processing. It features a professional dashboard layout, client-side cropping, and server-side operations, demonstrating knowledge of both asynchronous processing and distributed storage solutions.✨ FeaturesClient-Side Cropping: Users can select an area of the image for immediate cropping before upload using the React-Image-Crop library.Dynamic Processing: Supports on-demand conversion of saved images to Grayscale and custom Resizing via the gallery dashboard.Secure File Handling: Files are stored in secure, production-ready S3-compatible storage (MinIO) and served via temporary pre-signed download URLs.Modern UI/UX: Features a professional Dashboard Layout with a functional sidebar, global Dark/Light Mode toggles, and an Automatic Gallery Refresh system powered by the React Context API.CRUD Operations: Full Create, Read, Update (processing), and Delete functionality for all image assets.🛠️ Technology StackLayerTechnologyRoleFrontendReact.js (Vite), Axios, React RouterInteractive UI, component routing, and API communication.BackendNode.js (Express), MulterREST API endpoints, file handling, and server logic.Image ProcessingSharp.jsHigh-speed, high-performance image manipulation (resizing, grayscale, thumbnail generation).StorageMinIO (Docker)S3-compatible object storage for all image files and thumbnails.DatabaseMongoDB (Mongoose)Stores image metadata, filenames, and processing history.🚀 Setup and InstallationThis project requires Node.js, npm, and Docker to run the MinIO server.1. Backend & Frontend SetupClone the repository and navigate to the project root:Bashgit clone <YOUR_REPO_URL>
cd project
Install dependencies for both projects:Bashnpm install --prefix backend
npm install --prefix frontend
2. Configure MinIO StorageStart the local MinIO server using Docker. This command sets the default credentials needed by the backend.Bashdocker run -d -p 9000:9000 -p 9001:9001 --name minio-server -e "MINIO_ROOT_USER=minioadmin" -e "MINIO_ROOT_PASSWORD=minioadmin" minio/minio server /data --console-address ":9001"
Once running, go to http://localhost:9001 and log in (minioadmin/minioadmin) to create the images bucket.3. Environment VariablesCreate a .env file inside the backend folder and populate it with your specific credentials:Code snippet# SERVER
PORT=8000

# MONGODB (BytexlDB Credentials)
MONGODB_URI=mongodb://user_443rfc224:p443rfc224@bytexldb.com:5050/db_443rfc224

# MINIO (Default Docker credentials)
MINIO_ENDPOINT=localhost
MINIO_PORT=9000
MINIO_USE_SSL=false
MINIO_ACCESS_KEY=minioadmin
MINIO_SECRET_KEY=minioadmin
MINIO_BUCKET_NAME=images
4. Running the ProjectOpen two separate terminal windows (one for the backend, one for the frontend).ProjectCommandPortBackendnpm run dev --prefix backendhttp://localhost:8000Frontendnpm run dev --prefix frontendhttp://localhost:5173Open http://localhost:5173 in your browser to begin using the application.👤 Author[Aman Sharma] - [https://github.com/aman7114]Project Status: Completed and fully operational.