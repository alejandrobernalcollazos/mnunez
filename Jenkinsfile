// This shows a simple example of how to archive the build output artifacts.
node {
    stage "Build"

    // Checkout repository
    checkout scm

    // Make the output directory
    sh "echo I am building"
    
    // Making the image for the frontend with version v1
    sh "docker build -t frontend:v1 ."
    
    stage "Unit Tests"
    
    // Make the output directory
    sh "echo I am executing unit tests"
    
    stage "Static Code Analysis"
    
    // Make the output directory
    sh "echo Static Code Analysis my friends"
    
    stage "Automated Testing"
    
    // Make the output directory.
    sh "echo I am executing the automated tests"
 
    stage "Running Chayane page "
    // Eliminar el contenedor que esta corriendo actualmente
    try {
          sh "docker rm frontendcontainer -f"
        }
        catch (exc) {
            echo 'No pude borrar el contenedor'
        }

    // Subir el contenedor nuevo
    sh "docker run -d -p 8888:80 --name frontendcontainer frontend:v1 "

}
