# power-optimisation
Code and Services related to optimising power usage around the house

# Setting Up a Python Virtual Environment on a Mac

To set up a Python virtual environment on a Mac, follow these steps:

1. **Open Terminal**: Open the Terminal application on your Mac.

2. **Navigate to Your Project Directory**: Use the `cd` command to navigate to your project directory. For example:
    ```sh
    cd {working path}/power-optimisation
    ```

3. **Create a Virtual Environment**: Use the `python3` command to create a virtual environment. Replace `venv` with your desired environment name:
    ```sh
    python3 -m venv venv
    ```

4. **Activate the Virtual Environment**: Activate the virtual environment using the following command:
    ```sh
    source venv/bin/activate
    ```

5. **Install Dependencies**: Once the virtual environment is activated, install the required dependencies using `pip`:
    ```sh
    pip install -r requirements.txt
    ```

6. **Deactivate the Virtual Environment**: When you are done working in the virtual environment, you can deactivate it using the following command:
    ```sh
    deactivate
    ```

# Building and Running the Container Using Podman

To build and run the Docker container using Podman, follow these steps:

1. **Install Podman**: If you don't have Podman installed, you can install it using Homebrew:
    ```sh
    brew install podman
    ```

2. **Build the Docker Image**: Navigate to your project directory and build the Docker image using the following command:
    ```sh
    cd {working dir}/power-optimisation
    podman build -t power-optimisation:latest .
    ```

3. **Run the Docker Container**: Run the Docker container using the following command:
    ```sh
    podman run -d -p 8080:8080 --name power-optimisation power-optimisation:latest
    ```

4. **Access the Application**: You can now access the application by sending HTTP requests to `http://localhost:8080`.

5. **Stop the Docker Container**: To stop the running container, use the following command:
    ```sh
    podman stop power-optimisation
    ```

6. **Remove the Docker Container**: To remove the stopped container, use the following command:
    ```sh
    podman rm power-optimisation
    ```

By following these steps, you will be able to build and run your Docker container using Podman.

# Posting Data to the Application Using curl

To post "Hello, World!" to the application running on `localhost:8080` using `curl`, follow these steps:

1. **Ensure the Docker Container is Running**: Make sure the Docker container is running. You can start it using the following command if it's not already running:
    ```sh
    podman run -d -p 8080:8080 --name power-optimisation power-optimisation:latest
    ```

2. **Post Data Using curl**: Use the `curl` command to send a POST request with the data "Hello, World!" to the application:
    ```sh
    curl -X POST -H "Content-Type: application/json" -d '{"message": "Hello, World!"}' http://localhost:8080
    ```

3. **Verify the Response**: You should receive a response echoing back the posted data:
    ```json
    {
        "message": "Hello, World!"
    }
    ```

By following these steps, you will be able to post data to the application and receive a response using `curl`.

