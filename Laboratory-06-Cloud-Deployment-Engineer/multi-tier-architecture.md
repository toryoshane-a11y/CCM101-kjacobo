# Multi-Tier Architecture

## What is a Two-Tier Architecture?
A two-tier architecture splits an application into two separate layers, each with its own job. The first tier handles everything the user interacts with, and the second tier handles the storage of data. In this laboratory, the two tiers are the Nextcloud web container and the MariaDB database container.

## The Web/Application Tier
The web/application tier is the part of the system that users connect to. Its role is to serve the user interface, handle HTTP requests from browsers, and run the application logic. In this deployment, the Nextcloud container fills this role. It shows the login and file pages, processes uploads and downloads, and asks the database tier for any information it needs.

## The Database Tier
The database tier is responsible for storing persistent data. Its role is to keep user accounts, login credentials, and file metadata safe and organized, and to answer queries from the application tier. In this deployment, the MariaDB container fills this role. Users never connect to it directly, which also makes the system more secure.

## Why Separate Them?
Separating the web server and the database into two containers lets each one be updated, restarted, scaled, or fixed without affecting the other. For example, the web tier can be scaled up to handle more visitors without touching the data. If one container crashes, the other keeps running, and each container stays small and focused on one job. This makes the system easier to maintain, more secure, and more reliable than packing everything into one container.

