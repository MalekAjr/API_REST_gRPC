# API_REST_gRPC
My project is a project that implements a microservice architecture using gRPC and REST with Node.js. The project includes an API gateway (apigateway.js) that handles communication between clients and the underlying microservices.

# Project Structure
The project has the following structure:

markdown
Copy code
- grpc/
  - statu.proto
- apigateway.js
The grpc/ directory contains the statu.proto file, which defines the gRPC service and message structures.

The apigateway.js file serves as the API gateway for the project. It handles client requests and forwards them to the appropriate microservices.

# Dependencies
The project relies on the following dependencies:

@grpc/grpc-js: A JavaScript gRPC library for Node.js.
@grpc/proto-loader: A utility to load gRPC proto files.
# Getting Started
To get started with the project, follow these steps:

Clone the project repository.

## Install the project dependencies by running the following command:

shell
Copy code
npm install

Make sure you have the necessary protoc compiler installed. If not, follow the installation instructions for your operating system from the gRPC documentation.

Generate the gRPC server and client code from the statu.proto file using the protoc compiler. Run the following command:

shell
Copy code
protoc -I=./grpc --js_out=import_style=commonjs,binary:./grpc --grpc_out=./grpc --plugin=protoc-gen-grpc=`which grpc_tools_node_protoc_plugin` ./grpc/statu.proto
This command generates the necessary JavaScript files for gRPC.

Start the API gateway by running the following command:

shell
Copy code
node apigateway.js
The API gateway will start running on port 30045.

gRPC Service
The project implements a gRPC service for managing status entities. The statu.proto file defines the service and message structures.

Service Methods
The gRPC service provides the following methods:

getstatus: Retrieves the status entity based on an ID.
getstatu: Retrieves the status entity based on a status value.
getmessage: Retrieves the status entity based on a message value.
Message Structure
The status message structure has the following fields:

id: The ID of the status entity.
message: The message associated with the status entity.
idUser: The ID of the user associated with the status entity.
REST API
The API gateway also provides a REST API that serves as an alternative to the gRPC service. The REST endpoints map to the corresponding gRPC service methods.

REST Endpoints
GET /status/:id: Retrieves the status entity by ID.
GET /status?status=value: Retrieves the status entity by status value.
GET /status?message=value: Retrieves the status entity by message value.
Conclusion
This README provides an overview of the project and the necessary steps to get started. For more details about the implementation, please refer to the source code and the statu.proto file.

### ToRun the ^project:::
npm run start
npm run micro
