SRCS := ./main/main.go

all: $(SRCS)
	go mod tidy
	GOOS=linux GOARCH=amd64 go build -o main_linux_x86_64 $(SRCS)
	GOOS=darwin GOARCH=arm64 go build -o main_darwin_arm64 $(SRCS)


clean:
	rm -f main_*