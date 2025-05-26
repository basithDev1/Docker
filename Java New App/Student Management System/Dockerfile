
# ===== Stage 1: Build =====

FROM openjdk AS builder


WORKDIR /app/student-management

COPY . /app

RUN javac App.java packages/fileHandler/*.java packages/system/*.java

# ===== Stage 2: Runtime =====

FROM gcr.io/distroless/java17

WORKDIR /app

COPY --from=builder /app/student-mangagement  /app

CMD ["App"]
