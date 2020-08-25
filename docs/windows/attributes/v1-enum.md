---
title: v1_enum (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.v1_enum
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
ms.openlocfilehash: 6529a32b0bfe2de09191e9cced8f6bd98e7ffdcc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832990"
---
# <a name="v1_enum"></a>v1_enum

Belirtilen numaralandırılmış türün 16 bit varsayılan yerine 32 bitlik bir varlık olarak aktarılacağını yönlendirir.

## <a name="syntax"></a>Syntax

```cpp
[v1_enum]
```

## <a name="remarks"></a>Açıklamalar

**V1_enum** C++ özniteliği, [v1_enum](/windows/win32/Midl/v1-enum) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod **v1_enum**kullanımını gösterir:

```cpp
// cpp_attr_ref_v1_enum.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export, v1_enum]
enum eList {
   e1 = 1, e2 = 2
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Numaralandırılmış tür|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)
