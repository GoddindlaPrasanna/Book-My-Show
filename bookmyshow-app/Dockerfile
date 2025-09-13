
# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install --legacy-peer-deps

# Add a non-root user
RUN useradd -ms /bin/bash appuser
RUN chown -R appuser:appuser /app

# Copy all project files
COPY . .

# Switch to non-root user
USER appuser

# Expose the port and start the app
EXPOSE 3000
CMD ["npm", "start"]
