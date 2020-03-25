---
title: dahil etC++ (com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: 39f991bb036dce1c50a9d2ee800d3fec65af7c55
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166789"
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

**Include** C++ özniteliği, bir `#include` deyimin, oluşturulan. IDL dosyasındaki `import "docobj.idl"` deyimin altına yerleştirilmesine neden olur.

**Include** C++ özniteliği [Include](/windows/win32/Midl/include) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, **Include**öğesinin kullanımına ilişkin bir örnek gösterir. Bu örnekte, INCLUDE. h dosyası yalnızca bir `#include` ifadesini içerir.

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
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)
