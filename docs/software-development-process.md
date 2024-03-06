# Software development process

## Terms

### Application

Performs business logic. It is part of the domain.

### Build

Specific version of the application. It is part of the version.

### Domain

Encapsulates the domain area of the system. The domain contains set of applications. It is part of the system.

### Release

Specific version of the system. The release contains set of builds.

### System

Final solution delivered to the client. The system contains set of domains.

## Roles

### Software Engineer

Implements and deliveres user stories and bug fixes to the client.

#### Activities

* Create feature branch for User story.
* Create bug branch for Bug.
* Write code and tests.
* Create pull request for User story.
* Create pull request for Bug.
* Review code and tests written by other Software Engineers.
* Create Release.
* Deploy Release.

## Entities

### Sprint

Sprint is fixed-duration timebox during which Team members deliver value to Customer.

### Release

Release entity helps monitor current state of value delivery.

#### Release workflow

``` mermaid
stateDiagram-v2
  [*] --> Created
  Created --> Accumulating
  Accumulating --> Accumulated
  Accumulated --> Building
  Building --> ReadyForTesting
  ReadyForTesting --> Testing
  Testing --> ReadyForRelease
  ReadyForRelease --> Release
  Release --> Released
  Release --> Declined
  Released --> [*]
  Declined --> [*]
```

### Epic

Epic is set of User stories and Bugs releated to completed functionality delivered to Customer.

#### Epic workflow

``` mermaid
stateDiagram-v2
  [*] --> Created
  Created --> Groomed
  Groomed --> Planned
  Planned --> InProgress
  InProgress --> Released
  InProgress --> Declined
  Released --> [*]
  Declined --> [*]
```

### User story

User story is unit of value delivered to Customer.

#### User story workflow

``` mermaid
stateDiagram-v2
  [*] --> Created
  Created --> Groomed
  Groomed --> Planned
  Planned --> Coding
  Coding --> CodeReview
  CodeReview --> ReadyForTesting
  ReadyForTesting --> Testing
  Testing --> Release
  Release --> Released
  Release --> Declined
  Released --> [*]
  Declined --> [*]
```

### Bug

Bug contains information about error in functionality and expected behavior after fixing the error.

#### Bug workflow

``` mermaid
stateDiagram-v2
  [*] --> Created
  Created --> Groomed
  Groomed --> Planned
  Planned --> Coding
  Coding --> CodeReview
  CodeReview --> ReadyForTesting
  ReadyForTesting --> Testing
  Testing --> Release
  Release --> Released
  Release --> Declined
  Released --> [*]
  Declined --> [*]
```
