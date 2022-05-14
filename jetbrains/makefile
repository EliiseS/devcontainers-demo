start: stop
	docker build -t my_rd . && docker run --rm --name my_rd -p 5993:5993 my_rd

stop:
	- docker stop -t 0 my_rd