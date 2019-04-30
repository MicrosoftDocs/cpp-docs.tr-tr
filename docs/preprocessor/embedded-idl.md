---
title: embedded_idl
ms.date: 10/18/2018
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: c46924d2757d01a934c21a70f23e6556f6a10fd3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389352"
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

- **emitidl**: Typelib'den içeri aktarılan tür bilgilerini öznitelikli proje için üretilen IDL de mevcut olacaktır.  Bu varsayılan ve geçerli bir parametre belirtmezseniz `embedded_idl`.

- **no_emitidl**: Typelib'den içeri aktarılan tür bilgilerini öznitelikli proje için üretilen IDL içinde mevcut olmaz.

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

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)