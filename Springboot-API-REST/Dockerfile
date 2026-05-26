# ============================================
# Dockerfile - Backend Ventas (Multi-stage)
# ============================================

# Stage 1: Build
FROM maven:3.9-eclipse-temurin-17-alpine AS builder
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests

# Stage 2: Runtime
FROM eclipse-temurin:17-jre-alpine
WORKDIR /app

# Crear usuario no-root
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

# Copiar JAR desde el builder
COPY --from=builder /app/target/*.jar app.jar

# Cambiar a usuario no-root
USER appuser

# Variables de entorno para RDS (se inyectan en docker-compose)
ENV DB_ENDPOINT=localhost \
    DB_PORT=3306 \
    DB_NAME=itpcargo \
    DB_USERNAME=admin \
    DB_PASSWORD=itpcargo2025

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]
