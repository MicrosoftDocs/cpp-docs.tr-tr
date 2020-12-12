---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4104'
title: Bağlayıcı Araçları Uyarısı LNK4104
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: ab48885a4a8d2806154d3a8911bdc65453359e2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294437"
---
# <a name="linker-tools-warning-lnk4104"></a>Bağlayıcı Araçları Uyarısı LNK4104

' symbol ' sembolünün dışarı aktarılması özel olmalıdır

Aşağıdakilerden `symbol` biri olabilir:

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllGetDocumentation`

- `DllInitialize`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllRegisterServerExW`

- `DllUnload`

- `DllUnregisterServer`

- `RasCustomDeleteEntryNotify`

- `RasCustomDial`

- `RasCustomDialDlg`

- `RasCustomEntryDlg`

Bu uyarı, bir DLL için içeri aktarma kitaplığı oluştururken ve modül tanımı dosyasında özel olarak belirtmeden yukarıdaki işlevlerden birini dışarı aktardığınızda yayınlanır. Genel olarak, bu işlevler yalnızca OLE tarafından kullanılmak üzere verilir. Kitaplığa bağlı bir program bunlara çağrı yaptığında, bunları içeri aktarma kitaplığına koymak olağandışı davranışa yol açabilir. PRIVATE anahtar sözcüğü hakkında daha fazla bilgi için bkz. [dışarı aktarmalar](../../build/reference/exports.md).
