---
title: dahil et (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: 6b75df74ee69ee4f89eb7bf18fb6bcd77d8a6284
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842201"
---
# <a name="include-c"></a>include (C++)

Oluşturulan. IDL dosyasına dahil edilecek bir veya daha fazla üst bilgi dosyasını belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>Parametreler

*header_file*<br/>
Oluşturulan. IDL dosyasına dahil etmek istediğiniz dosyanın adı.

## <a name="remarks"></a>Açıklamalar

C++ **dahil etme** özniteliği, bir `#include` deyimin `import "docobj.idl"` oluşturulan. IDL dosyasındaki deyimin altına yerleştirilmesine neden olur.

C++ **dahil etme** özniteliği [Include](/windows/win32/Midl/include) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, **Include**öğesinin kullanımına ilişkin bir örnek gösterir. Bu örnekte, INCLUDE. h dosyası yalnızca bir `#include` ifade içerir.

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)<br/>
[aktarmaya](import.md)<br/>
[importidl](importidl.md)<br/>
[INCLUDELIB](includelib-cpp.md)<br/>
[importlib](importlib.md)
