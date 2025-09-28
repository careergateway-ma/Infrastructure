# CareerGateway Infrastructure

Enterprise microservices infrastructure for Morocco's hiring platform.

## Overview

CareerGateway is a complete hiring SaaS platform built with Spring Boot microservices. Companies get instant career portals, automated hiring workflows, and team collaboration tools through a subscription-based service.

## Platform Structure

The platform is organized across multiple domains:

- **careergateway.ma** - Main landing page and marketing site
- **app.careergateway.ma** - Company dashboard for HR teams
- **{company}.careergateway.ma** - Automatic career portals for each company
- **careers.{company}.com** - Custom domain support for enterprise clients

## Subscription Plans

We offer four subscription tiers:

- **Free** - 1 job posting, basic features, company subdomain
- **Starter** (99 MAD/month) - 3 job postings, team collaboration, custom branding
- **Professional** (299 MAD/month) - 10 job postings, custom domains, analytics
- **Enterprise** (999 MAD/month) - Unlimited everything, white-label, API access

## Services Architecture

### Core Services

**API Gateway** (Port 8080)
- Single entry point for all frontend applications
- Handles REST to gRPC translation
- Manages authentication and routing

**Auth Service** (gRPC 50051, HTTP 8081)
- User registration and authentication
- JWT token management
- Company-user relationships
- User invitations

**Company Service** (gRPC 50052, HTTP 8082)
- Company profile management
- Branding configuration
- Company settings and preferences

**Domain Service** (gRPC 50053, HTTP 8083)
- Automatic subdomain generation
- Custom domain verification
- Domain-to-company mapping

### Business Logic Services

**Job Service** (gRPC 50054, HTTP 8084)
- Job posting creation and management
- Job categorization and search
- Job status and expiration handling

**Form Service** (gRPC 50055, HTTP 8085)
- Dynamic form builder (no-code)
- Question types and validation
- Form response scoring

**Pipeline Service** (gRPC 50056, HTTP 8086)
- Hiring workflow automation
- Pipeline stages and transitions
- Automated actions and notifications

**Application Service** (gRPC 50057, HTTP 8087)
- Candidate application processing
- Application scoring and ranking
- Stage movement tracking

### Supporting Services

**Permission Service** (gRPC 50058, HTTP 8088)
- Role-based access control
- Job-level permissions
- Team access management

**Team Service** (gRPC 50059, HTTP 8089)
- Team member management
- Collaboration features
- Activity tracking

**Subscription Service** (gRPC 50060, HTTP 8090)
- Plan management and limits
- Feature gating
- Usage tracking

**Payment Service** (gRPC 50061, HTTP 8091)
- Subscription billing
- Payment processing
- Invoice generation

**Notification Service** (gRPC 50062, HTTP 8092)
- Email automation
- SMS notifications
- Template management

**Analytics Service** (gRPC 50063, HTTP 8093)
- Hiring metrics and insights
- Performance tracking
- Custom reports

**File Service** (gRPC 50064, HTTP 8094)
- Document upload and storage
- CV and resume handling
- Secure file access

## Getting Started

### Requirements

You need Docker and Docker Compose installed on your machine.

### Development Setup

Clone the repository:
```bash
git clone https://github.com/careergateway-ma/infrastructure.git
cd infrastructure
```
Copy the environment file:
```bash
cp .env.example .env
```
Start all services:
```bash
docker-compose up -d
```
Check that everything is running:
```bash
docker-compose ps
```
