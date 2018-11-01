---
title: embedded_idl
ms.date: 10/18/2018
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: 202d5b23a5e2e8e673e3c220b9618cfe6cd4f0d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525612"
---
# <a name="embeddedidl"></a>embedded_idl

**C++ özgü**

Tür kitaplığı .tlh dosyasına, öznitelik tarafından oluşturulan kod korunarak yazıldığını belirtir.

## <a name="syntax"></a>Sözdizimi

```
embedded_idl[("param")]
```

### <a name="parameters"></a>Parametreler

*param*<br/>
İki değerden biri olabilir:

- **emitidl**: Tür Kitaplığı ' alınan tür bilgileri öznitelikli proje için üretilen IDL mevcut olacaktır.  Bu varsayılan ve geçerli bir parametre belirtmezseniz `embedded_idl`.

- **no_emitidl**: Tür Kitaplığı ' alınan tür bilgileri öznitelikli proje için üretilen IDL mevcut olmayacaktır.

## <a name="example"></a>Örnek

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

## <a name="remarks"></a>Açıklamalar

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)