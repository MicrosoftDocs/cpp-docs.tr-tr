---
title: defaultvtable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultvtable
dev_langs:
- C++
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4cec0e02a6a61638f8aed1b4015fea065cbfd343
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207694"
---
# <a name="defaultvtable"></a>defaultvtable

Varsayılan vtable arabirim bir COM nesnesi için bir arabirim tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ defaultvtable(
   interface
) ]
```

### <a name="parameters"></a>Parametreler

*interface*  
COM nesnesi için varsayılan vtable olmasını istediğiniz belirtilen arabirim.

## <a name="remarks"></a>Açıklamalar

**Defaultvtable** C++ özniteliği ile aynı işlevlere sahip [defaultvtable](/windows/desktop/Midl/defaultvtable) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod öznitelikleri kullanan bir sınıf üzerinde gösterir. **defaultvtable** bir varsayılan arabirim belirtmek için:

```cpp
// cpp_attr_ref_defaultvtable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI1 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface IMyI2 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000003")]
__interface IMyI3 {
   HRESULT x();
};

[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),
uuid("00000000-0000-0000-0000-000000000004")]
class CMyC3 : public IMyI3 {};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass**|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Sınıf Öznitelikleri](../windows/class-attributes.md)  