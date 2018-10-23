---
title: embedded_idl | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- embedded_idl
dev_langs:
- C++
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7337595111b01ceeec53cc97f11ec2f35a081c5
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808348"
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