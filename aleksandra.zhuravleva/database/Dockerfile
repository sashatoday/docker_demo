FROM postgres:9.6

LABEL maintainer "Aleksandra Zhuravleva <guravleva.aleksandra@gmail.com>"

# PostgreSQL environment variables
ENV POSTGRES_USER spa
ENV POSTGRES_DB q1
ENV POSTGRES_PASSWORD 123

# Add folder with database to $PGDATA 
ADD data /var/lib/postgresql/data

# Listen on 5432 port at runtime (contact the application)
EXPOSE 5432

# Launch postgres daemon
ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["postgres"]