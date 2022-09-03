FROM golang:1.16-alpine as dependencies

WORKDIR /app

COPY go.mod ./
RUN go mod download 
COPY *.go ./

FROM dependencies as builder
RUN go build -o shouter

FROM scratch
COPY --from=builder /app/shouter ./
ENTRYPOINT [ "./shouter" ]
CMD ["Code.education Rocks!"] 