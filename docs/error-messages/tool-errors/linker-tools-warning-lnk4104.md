---
title: Bağlayıcı Araçları Uyarısı LNK4104
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: 604dccf01b3dffc0060546bebf19d64c16ebf965
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193972"
---
# <a name="linker-tools-warning-lnk4104"></a>Bağlayıcı Araçları Uyarısı LNK4104

' symbol ' sembolünün dışarı aktarılması özel olmalıdır

`symbol` aşağıdakilerden biri olabilir:

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
