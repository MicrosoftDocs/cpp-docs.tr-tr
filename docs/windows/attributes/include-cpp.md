---
description: 'Şunlar hakkında daha fazla bilgi edinin: include (C++)'
title: dahil et (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: c6d12b9d8826ce84de0c01aaf055f5a4176fea10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321369"
---
# <a name="include-c"></a>include (C++)

Oluşturulan. IDL dosyasına dahil edilecek bir veya daha fazla üst bilgi dosyasını belirtir.

## <a name="syntax"></a>Sözdizimi

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

Aşağıdaki kod, **Include** öğesinin kullanımına ilişkin bir örnek gösterir. Bu örnekte, INCLUDE. h dosyası yalnızca bir `#include` ifade içerir.

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
|**Yinelenebilir**|Hayır|
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
