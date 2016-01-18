Archiva Docker image
====================

# Usage
## Simple
	docker run -p 8080:8080 -d jdauphant/archiva
## Advanced
    docker run -d -v /var/archiva --name archiva-data jdauphant/archiva echo Data-only container for archiva
    docker run --name archiva -p 8080:8080 -d --volumes-from archiva-data jdauphant/archiva
