---
title: HTTP Listener fails to initialize
description: Provides a solution to an issue that HTTP Listener fails to initialize when user lacks SeChangeNotifyPrivilege.
ms.date: 09/25/2020
author: Deland-Han 
ms.author: delhan
manager: dscontentpm
audience: itpro
ms.topic: troubleshooting
ms.prod: windows-server
localization_priority: medium
ms.reviewer: kaushika
ms.prod-support-area-path: Multilingual User Interface (MUI) and Input Method Editor (IME)
ms.technology: windows-server-application-compatibility
---
# HTTP Listener fails to initialize when lacking SeChangeNotifyPrivilege

This article provides a solution to an issue that HTTP Listener fails to initialize when user lacks SeChangeNotifyPrivilege.

_Applies to:_ &nbsp; Windows Server 2016, Windows Server 2019  
_Original KB number:_ &nbsp; 4570992

## Symptoms

When initializing a new HTTP Listener using the `HttpInitialize` function or the .NET `HttpListener` class, the operation fails and you receive this error message:

> HttpInitialize failed with 5 ( -access denied)

## Cause

This issue occurs when the account running the code lacks the **SeChangeNotifyPrivilege** privilege.

## Workaround

Grant the [Bypass traverse checking](/windows/security/threat-protection/security-policy-settings/bypass-traverse-checking) user right to the relevant account.

This privilege is granted to the Everyone group by default.
