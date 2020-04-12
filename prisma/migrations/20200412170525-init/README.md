# Migration `20200412170525-init`

This migration has been generated by Edgar Cumbreras at 4/12/2020, 5:05:25 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql

```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration 20200412155953-init..20200412170525-init
--- datamodel.dml
+++ datamodel.dml
@@ -1,7 +1,7 @@
 datasource db {
   provider = "postgresql"
-  url = "***"
+  url      = env("DATABASE_URL")
 }
 generator client {
   provider = "prisma-client-js"
@@ -24,9 +24,9 @@
   createdAt      DateTime @default(now())
   updatedAt      DateTime @updatedAt
   message        String
   date           String
-  userFrom       User     @relation("kudosSent", fields: [userSentId], references: [id])
+  userSent       User     @relation("kudosSent", fields: [userSentId], references: [id])
   userSentId     Int
   userReceived   User     @relation("kudosReceived", fields: [userReceivedId], references: [id])
   userReceivedId Int
 }
```

