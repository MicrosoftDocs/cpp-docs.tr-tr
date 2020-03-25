---
title: ıncludelib (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 4022a3f1f2d4ccaabe65c24065be8e1c846d604d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214856"
---
# <a name="includelib-c"></a>includelib (C++)

Oluşturulan. IDL dosyasına bir. IDL veya. h dosyasının eklenmesine neden olur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ includelib(name.idl) ];
```

### <a name="parameters"></a>Parametreler

*Name. IDL*<br/>
Üretilen. IDL dosyasının bir parçası olarak dahil etmek istediğiniz. IDL dosyasının adı.

## <a name="remarks"></a>Açıklamalar

**Includelib** C++ özniteliği, `importlib` deyimden sonra oluşturulan. IDL dosyasına bir. IDL veya. h dosyasının eklenmesine neden olur.

## <a name="example"></a>Örnek

Aşağıdaki kod bir. cpp dosyasında gösterilmiştir:

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Yes|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[importlib](importlib.md)
