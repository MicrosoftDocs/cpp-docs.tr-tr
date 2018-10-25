---
title: v1_enum (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: c1deb68164cdcbd93b6c4992f1c2a19b01095d57
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50058421"
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
   e1 = 1, e2 = 2
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

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)