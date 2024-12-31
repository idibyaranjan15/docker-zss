# Stage 1: Build Stage
FROM node:22.12.0-alpine AS builder

WORKDIR /build

# Copy and install dependencies
COPY package*.json ./
RUN npm install --only=production

# Copy the source code and build the application
COPY . . 
RUN npm run build

# Stage 2: Runner Stage
FROM node:22.12.0-alpine AS runner

WORKDIR /app

# Copy only the production dependencies and built code
COPY --from=builder /build/node_modules ./node_modules
COPY --from=builder /build/package.json ./
COPY --from=builder /build/dist ./dist



# Default command
CMD ["npm", "start"]
