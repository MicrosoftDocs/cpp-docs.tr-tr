---
title: Bağlayıcı araçları uyarısı LNK4104 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6304f3ea928c89f4756a4594270ebb7914324f85
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057268"
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