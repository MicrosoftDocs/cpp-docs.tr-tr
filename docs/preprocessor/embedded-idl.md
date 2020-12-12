---
description: 'Hakkında daha fazla bilgi edinin: embedded_idl Import özniteliği'
title: embedded_idl içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: a56c6e664c082db4b6eac078b7133a1ead947d3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300599"
---
# <a name="embedded_idl-import-attribute"></a>embedded_idl içeri aktarma özniteliği

**C++ özel**

Tür kitaplığının, `.tlh` öznitelik tarafından oluşturulan kodla korunan dosyaya yazılıp yazılmadığını belirtir.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **embedded_idl** [ **(** { **"emitidl"**  |  **"no_emitidl"** } **)** ]

### <a name="parameters"></a>Parametreler

**emitidl**\
*Türden* içeri aktarılan tür bilgileri, öznitelikli proje IÇIN oluşturulan IDL 'de mevcut. Bu davranış varsayılandır ve için bir parametre belirtmezseniz geçerli olur `embedded_idl` .

**"no_emitidl"**\
*Türden* içeri aktarılan tür bilgileri, öznitelikli proje IÇIN oluşturulan IDL 'de yok.

## <a name="example"></a>Örnek

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
