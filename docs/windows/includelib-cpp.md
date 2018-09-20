---
title: ıncludelıb (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.includelib
dev_langs:
- C++
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5f15fcefe1a18156e4cbe8180138d7b6c1d944e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398592"
---
# <a name="includelib-c"></a>includelib (C++)

Oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası neden olur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ includelib(
   name.idl
) ];
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

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)<br/>
[Tek Başına Öznitelikler](../windows/stand-alone-attributes.md)<br/>
[import](../windows/import.md)<br/>
[importidl](../windows/importidl.md)<br/>
[İçerir](../windows/include-cpp.md)<br/>
[importlib](../windows/importlib.md)  