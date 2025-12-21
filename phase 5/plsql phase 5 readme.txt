# PHASE V: Table Implementation & Data Insertion

## Project Information
- **Student:** Regis
- **Student ID:** 28757
- **Project:** Medaid Connect - Emergency First Aid Platform
- **Phase:** V - Table Implementation & Data Insertion
- **Date:** November 2025

## Overview
This phase involves creating all 10 database tables and populating them with realistic data (100-500+ rows per main table) with Rwanda context.

## Tables Created (10 Total)

### Phase V Tables (7):
1. `EMERGENCIES` - 52 emergency types
2. `FIRST_AID_GUIDES` - 350+ guide steps
3. `USERS` - 450+ anonymous users
4. `LOCATIONS` - 120+ Rwandan locations
5. `TIME_DIMENSION` - 1,095 time records (3 years)
6. `GUIDE_USAGE` - 5,200+ usage records
7. `FEEDBACK` - 3,200+ feedback entries

### Phase VII Tables (3):
8. `HOLIDAYS` - 9 Rwanda public holidays
9. `SYSTEM_USERS` - 35 user roles
10. `AUDIT_LOG` - 50 audit records

## Files in This Phase

### 1. Main Table Creation
**File:** `phase_v_create_tables.sql`
- Creates all 10 tables with proper constraints
- Includes indexes for performance
- Drops existing tables if they exist
- Enables all constraints after creation

### 2. Data Insertion
**File:** `phase_v_insert_data.sql`
- Inserts realistic data meeting 100-500+ rows requirement
- Rwanda-specific data (cities, provinces, holidays)
- Includes edge cases (NULL values)
- Maintains referential integrity
- Commits in batches for performance

### 3. Validation Script
**File:** `phase_v_validation.sql`
- Verifies table row counts
- Checks data integrity
- Validates business rules
- Provides sample data views
- Generates summary report

## Data Statistics

### Row Counts:
| Table | Target | Actual | Status |
|-------|--------|--------|--------|
| EMERGENCIES | 50+ | 52 | ✅ |
| FIRST_AID_GUIDES | 100+ | 350+ | ✅ |
| USERS | 400+ | 450 | ✅ |
| LOCATIONS | 100+ | 120+ | ✅ |
| TIME_DIMENSION | 1,000+ | 1,095 | ✅ |
| GUIDE_USAGE | 5,000+ | 5,200+ | ✅ |
| FEEDBACK | 3,000+ | 3,200+ | ✅ |

### Total Records: ~11,000+

## Data Characteristics

### 1. Realistic Data
- **Emergencies:** 52 common emergency types in Rwanda
- **Guides:** Step-by-step instructions for each emergency
- **Users:** Anonymous tracking with demographics
- **Locations:** All 5 Rwandan provinces covered
- **Time:** 3 years of time dimension data

### 2. Edge Cases Included
- NULL values in appropriate columns
- Mixed demographic distributions
- Various completion rates (70% completed)
- Different feedback ratings (1-5 stars)

### 3. Rwanda Context
- Rwandan cities and provinces
- Rwanda public holidays
- Emergency number 112 referenced
- Common Rwandan emergencies (snake bites, etc.)

## Execution Instructions

### Step 1: Create Tables
```sql
-- Connect to your PDB
ALTER SESSION SET CONTAINER = tue_28757_Regis_medaid_db;

-- Run table creation
@phase_v_create_tables.sql