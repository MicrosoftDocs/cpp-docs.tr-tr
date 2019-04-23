---
title: ıncludelıb (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 57f039eeae527dd03884b12e7d9eb424d87f597f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030006"
---
# <a name="includelib-c"></a>includelib (C++)

Oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası neden olur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ includelib(name.idl) ];
```

### <a name="parameters"></a>Parametreler

*Name.idl*<br/>
Oluşturulan .idl dosyasının bir parçası olarak dahil istediğiniz .idl dosyasının adı.

## <a name="remarks"></a>Açıklamalar

**İncludelib** C++ öznitelik neden olur, sonra oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası `importlib` deyimi.

## <a name="example"></a>Örnek

Aşağıdaki kodu, .cpp dosyasında gösterilir:

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
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Evet|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[importlib](importlib.md)