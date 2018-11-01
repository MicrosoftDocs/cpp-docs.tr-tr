---
title: (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: 6fb385877285602c1eb6649d11e16558d7fb07ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544761"
---
# <a name="include-c"></a>include (C++)

Oluşturulan .idl dosyasına eklenecek bir veya daha fazla üst bilgi dosyaları belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>Parametreler

*header_fıle*<br/>
Oluşturulan .idl dosyasına dahil istediğiniz bir dosya adı.

## <a name="remarks"></a>Açıklamalar

**Dahil** C++ öznitelik neden olan bir `#include` altına yerleştirilecek deyimi `import "docobj.idl"` oluşturulan .idl dosyasındaki deyimi.

**Dahil** C++ özniteliği ile aynı işlevlere sahip [dahil](/windows/desktop/Midl/include) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği nasıl kullanılacağını gösterir **dahil**. Bu örnekte, yalnızca dosya include.h içeren bir `#include` deyimi.

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)