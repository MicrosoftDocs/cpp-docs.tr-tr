---
description: 'Daha fazla bilgi edinin: ıncludelib (C++)'
title: ıncludelib (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 9a7565a931a865b69f0da95da9e92481b27de3b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321356"
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

**Includelib** C++ özniteliği, ' den sonra oluşturulan. IDL dosyasına bir. IDL veya. h dosyasının eklenmesini sağlar `importlib` .

## <a name="example"></a>Örnek

Aşağıdaki kod bir. cpp dosyasında gösterilmiştir:

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Yinelenebilir**|Evet|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)<br/>
[aktarmaya](import.md)<br/>
[importidl](importidl.md)<br/>
[içeriyor](include-cpp.md)<br/>
[importlib](importlib.md)
