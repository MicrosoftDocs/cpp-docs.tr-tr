---
title: embedded_idl içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: 01948b171b20ad0a3bf3e7a41047f1fe3df185b0
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216331"
---
# <a name="embedded_idl-import-attribute"></a>embedded_idl içeri aktarma özniteliği

**C++Belirli**

Tür kitaplığının, öznitelik tarafından oluşturulan kodla korunan `.tlh` dosyaya yazılıp yazılmadığını belirtir.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **embedded_idl** [ **(** { **"emitidl"**  |  **"no_emitidl"** } **)** ]

### <a name="parameters"></a>Parametreler

**emitidl**\
*Türden* içeri aktarılan tür bilgileri, öznitelikli proje IÇIN oluşturulan IDL 'de mevcut. Bu davranış varsayılandır ve için `embedded_idl`bir parametre belirtmezseniz geçerli olur.

**"no_emitidl"** \
*Türden* içeri aktarılan tür bilgileri, öznitelikli proje IÇIN oluşturulan IDL 'de yok.

## <a name="example"></a>Örnek

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
