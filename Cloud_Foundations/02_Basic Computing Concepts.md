# Software Development Life Cycle (SDLC)

## What is SDLC?

The **Software Development Life Cycle (SDLC)** is a structured process used to develop, deploy, and maintain software in an organized manner.

### Benefits
- Produces high-quality software
- Meets customer requirements
- Improves project management
- Reduces development risks

---

# SDLC Phases

1. Plan
2. Analyze
3. Design
4. Develop
5. Test
6. Implement
7. Maintain

> SDLC is a continuous cycle used to create, update, fix, and improve applications. :contentReference[oaicite:0]{index=0}

---

# 1. Plan Phase

### Purpose
Identify project goals and required resources.

### Activities
- Define project objectives
- Estimate costs
- Allocate resources
- Determine tools and technologies
- Plan quality assurance

### Output
**Project Plan**

### Key Question
**What problem needs to be solved and what resources are required?**

---

# 2. Analyze Phase

### Purpose
Understand and document user requirements.

### Activities
- Gather customer requirements
- Analyze business needs
- Define system functionality

### Output
**Software Requirements Specification (SRS)**

### Key Question
**What do users want from the solution?**

---

# 3. Design Phase

### Purpose
Convert requirements into a technical design.

### Activities
- Evaluate architectures
- Create design alternatives
- Design user interfaces
- Assess risks, budget, and timelines
- Select the best design

### Output
**Design Specification Document**

### Includes
- Functional descriptions
- System architecture
- UI design
- Technical specifications

### Key Question
**How will the solution be built?**

---

# 4. Develop Phase

### Purpose
Build the software.

### Activities
- Write source code
- Follow coding standards
- Select programming language
- Implement design specifications

### Output
**Working Software/Application**

### Key Question
**Build what was designed.**

---

# 5. Test Phase

### Purpose
Verify that the application works correctly.

### Importance
- Finds bugs and defects
- Ensures software quality
- Reduces future maintenance costs

### Automated Testing
Testing code can be written to test other code automatically.

### Types of Testing

#### Unit Testing
- Tests individual program components
- Usually performed by developers

#### Integration Testing
- Tests interaction between components
- Ensures modules work together

#### Security Testing
- Identifies vulnerabilities
- Protects against threats

#### Performance Testing
- Measures speed and efficiency
- Validates performance requirements

### Key Question
**Did we build the correct solution?**

---

# 6. Implement Phase

### Also Known As
**Deployment**

### Activities
- Customer approval/sign-off
- Release application
- Move to production environment
- Make application available to users

### Output
**Production System**

### Key Question
**How do users start using the software?**

---

# 7. Maintain Phase

### Purpose
Monitor and improve software after deployment.

### Activities
- Monitor system performance
- Fix defects
- Update functionality
- Improve reliability

---

# Types of Maintenance

## 1. Corrective Maintenance

### Purpose
Fix existing problems and bugs.

### Example
Fixing a login error.

---

## 2. Adaptive Maintenance

### Purpose
Modify software due to environmental changes.

### Example
Updating software after a database upgrade.

---

## 3. Perfective Maintenance

### Purpose
Add or improve features.

### Example
Redesigning the user interface based on user feedback.

---

## 4. Preventive Maintenance

### Purpose
Prevent future issues.

### Example
Refactoring code for easier maintenance.

---

# SDLC Flow Diagram

```text
Plan
  ↓
Analyze
  ↓
Design
  ↓
Develop
  ↓
Test
  ↓
Implement
  ↓
Maintain
  ↓
(Repeat Cycle)
```

---

# Additional Concepts

## Server

A **server** is a computer that provides data or services to other computers.

### Examples
- Web Server
- Database Server
- File Server

---

## Data Center

A **data center** is a physical facility that houses:
- Servers
- Storage devices
- Networking equipment

Purpose:
- Store and process organizational data

---

## Hardware Virtualization

### Definition
Technology that allows multiple **Virtual Machines (VMs)** to run on a single physical computer.

### Importance
- Fundamental technology in cloud computing
- Improves resource utilization
- Reduces hardware costs

---

# Quick Revision Table

| SDLC Phase | Main Purpose | Output |
|------------|-------------|---------|
| Plan | Define goals and resources | Project Plan |
| Analyze | Gather requirements | SRS |
| Design | Create technical solution | Design Specification |
| Develop | Write code | Software Product |
| Test | Verify functionality | Tested Software |
| Implement | Deploy software | Production Application |
| Maintain | Improve and support | Updated Software |

---

# Exam Tips

### Remember the SDLC Sequence

**P → A → D → D → T → I → M**

**Plan → Analyze → Design → Develop → Test → Implement → Maintain**

### Maintenance Types Shortcut

| Type | Purpose |
|--------|---------|
| Corrective | Fix errors |
| Adaptive | Adjust to environment changes |
| Perfective | Improve functionality |
| Preventive | Avoid future issues |

### One-Liners

- **Server:** Provides services to other computers.
- **Data Center:** Physical location containing computing infrastructure.
- **Virtualization:** Creates multiple VMs on one physical machine.
- **Testing:** Finds defects before release.
- **Implementation:** Deployment to production.