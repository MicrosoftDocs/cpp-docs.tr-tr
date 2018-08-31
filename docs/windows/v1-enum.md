---
title: v1_enum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.v1_enum
dev_langs:
- C++
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bbacec7644a05f0077c8d6ffbe3e7856c66dcc4f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222981"
---
# <a name="v1enum"></a>v1_enum

Belirtilen listeden seçimli türü 16-bit varsayılan yerine bir 32-bit varlık olarak iletilmesi yönlendirir.

## <a name="syntax"></a>Sözdizimi

```cpp
[v1_enum]
```

## <a name="remarks"></a>Açıklamalar

**V1_enum** C++ özniteliği ile aynı işlevlere sahip [v1_enum](/windows/desktop/Midl/v1-enum) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir kullanımını göstermektedir. **v1_enum**:

```cpp
// cpp_attr_ref_v1_enum.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export, v1_enum]
enum eList {
   e1 = 1,
   e2 = 2
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Numaralandırılmış tür|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)  