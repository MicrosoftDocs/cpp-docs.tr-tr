---
title: switch_type | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.switch_type
dev_langs:
- C++
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: faa2a3be7260eecb16599db967336bcb7b774c99
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200132"
---
# <a name="switchtype"></a>switch_type

Birleşim discriminant kullanılan değişkenin türünü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[switch_type(
type
}]
```

### <a name="parameters"></a>Parametreler

*Türü*  
Anahtar türü, bir tamsayı, karakter, Boole veya numaralandırma türü olabilir.

## <a name="remarks"></a>Açıklamalar

**Switch_type** C++ özniteliği ile aynı işlevlere sahip [switch_type](/windows/desktop/Midl/switch-type) MIDL özniteliği.

C++ öznitelikleri desteklemiyor [birleşimler kapsüllenmiş](/windows/desktop/Midl/encapsulated-unions). [Nonencapsulated birleşimler](/windows/desktop/Midl/nonencapsulated-unions) yalnızca şu biçimde desteklenir:

```cpp
// cpp_attr_ref_switch_type.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLibrary")];
[ export ]
struct SizedValue2 {
   [switch_type("char"), switch_is(kind)] union {
      [case(1), string]
         wchar_t* wval;
      [default, string]
         char* val;
   };
   char kind;
};
```

## <a name="example"></a>Örnek

Bkz: [çalışması](../windows/case-cpp.md) örnek kullanımını örneğin **switch_type**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**tür tanımı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)  
[export](../windows/export.md)  