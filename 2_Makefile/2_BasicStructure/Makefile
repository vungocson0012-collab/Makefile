###############
## TARGETS   ##
###############
# target: prerequisites
#	commands

# The commands are a series of steps typically to make the target,
# 	need to start with a tab character, not space
# The prerequisites are file names, separated by spaces.
# 	These files need to exist before the commands for the target are run.

build: my_lib.o main.o	# kiểm tra target my_lib.o và main.o đc tạo chưa
# đc tạo rồi thì chạy target build
	g++ main.o my_lib.o -o main

main.o:	#target có thể đặt giống tên file, đặt cho có ý nghĩa
	g++ main.cc -c

#Form đặt: 
#	file_đầu_ra: các_file_đầu_vào
#		lệnh tạo file_đầu_ra

my_lib.o:
	g++ my_lib.cc -c

execute:
	./main

clean:
	rm -f *.o
	rm -f main