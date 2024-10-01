TARGET 	:= dev
PROFILE	:= DEFAULT
SRCS		:= $(shell find . -name "*.go" | grep -v /tests | grep -v /xcpb | grep -v /gpb | grep -v /generated)
OUTPUT	:= ./src/gosrc/main_darwin_arm64 ./src/gosrc/main_linux_x86_64


./src/gosrc/main_darwin_arm64: $(SRCS)
	cd src/gosrc && go mod tidy && GOOS=darwin GOARCH=arm64 go build -o main_darwin_arm64 ./main/main.go

./src/gosrc/main_linux_x86_64: $(SRCS)
	cd src/gosrc && go mod tidy && GOOS=linux GOARCH=amd64 go build -o main_linux_x86_64 ./main/main.go

build: $(OUTPUT)

validate:
	databricks --profile $(PROFILE) bundle validate


deploy: $(OUTPUT)
	databricks --profile $(PROFILE) bundle deploy

run: deploy
	databricks --profile $(PROFILE) bundle run


clean:
	rm $(OUTPUT)

