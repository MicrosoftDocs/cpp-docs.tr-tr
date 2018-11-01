---
title: Bağlayıcı Araçları Uyarısı LNK4104
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: 3d89b27c32b33b917abb7fc140eebf5924142423
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668136"
---
# <a name="linker-tools-warning-lnk4104"></a>Bağlayıcı Araçları Uyarısı LNK4104

'symbol' sembolünün dışarı aktarılması özel olmalıdır

`symbol` Aşağıdakilerden biri olabilir:

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

Bu uyarı, bir DLL için bir içeri aktarma kitaplığı derlerken yayılan ve yukarıdaki işlevlerden biri, özel olarak modül tanım dosyasında belirtmeden dışarı aktarın. Genel olarak, bu işlevler yalnızca OLE tarafından kullanılmak üzere dışarı aktarılır. Kitaplığa yanlış bağlı bir programı bunlara çağrı yaptığında bunları içeri aktarma kitaplığı'nda yerleştirme olağan dışı davranışlara neden olabilir. PRIVATE anahtar sözcüğü hakkında daha fazla bilgi için bkz: [dışarı AKTARMALARI](../../build/reference/exports.md).