---
title: ıncludelıb (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 96d4ecff09cf00b5221fd0c9c80b4584b203a781
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059658"
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

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[importlib](importlib.md)