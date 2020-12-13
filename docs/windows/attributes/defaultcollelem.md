---
description: 'Daha fazla bilgi edinin: defaultcollelem'
title: defaultcollelem
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultcollelem
helpviewer_keywords:
- defaultcollelem attribute
ms.assetid: 3dbbd293-8b83-4f70-a36b-64cc1d0b6713
ms.openlocfilehash: 6d1d3bb77a9951fc82cd19a3dc9d6f42ee54b6c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333020"
---
# <a name="defaultcollelem"></a>defaultcollelem

Visual Basic kodu iyileştirmesi için kullanılır.

## <a name="syntax"></a>Syntax

```cpp
[defaultcollelem]
```

## <a name="remarks"></a>Açıklamalar

**Defaultcollelem** C++ özniteliği, [defaultcollelem](/windows/win32/Midl/defaultcollelem) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, **defaultcollelem** özniteliğini kullanarak bir arabirim yöntemi gösterir:

```cpp
// cpp_attr_ref_defaultcollelem.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyForm
{
   [propget, id(1), bindable, defaultcollelem, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);
   [propput, id(1), bindable, defaultcollelem, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Interface yöntemi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)
