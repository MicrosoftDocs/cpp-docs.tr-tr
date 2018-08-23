---
title: defaultcollelem | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultcollelem
dev_langs:
- C++
helpviewer_keywords:
- defaultcollelem attribute
ms.assetid: 3dbbd293-8b83-4f70-a36b-64cc1d0b6713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3cf41a5d827bd3834cffdd7d229d01d4a4889c9b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610008"
---
# <a name="defaultcollelem"></a>defaultcollelem

Visual Basic kod iyileştirme için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
[defaultcollelem]
```

## <a name="remarks"></a>Açıklamalar

**Defaultcollelem** C++ özniteliği ile aynı işlevlere sahip [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir arabirim yöntemini kullanarak göstermektedir **defaultcollelem** özniteliği:

```cpp
// cpp_attr_ref_defaultcollelem.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyForm
{
   [propget, id(1), bindable, defaultcollelem, displaybind,
   defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);
   [propput, id(1), bindable, defaultcollelem, displaybind,
   defaultbind, requestedit] HRESULT P1([in] long nSize);
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Yöntem Öznitelikleri](../windows/method-attributes.md)  