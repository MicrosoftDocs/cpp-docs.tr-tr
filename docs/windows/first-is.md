---
title: first_is | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.first_is
dev_langs:
- C++
helpviewer_keywords:
- first_is attribute
ms.assetid: 89acbf56-3b38-4d44-83e8-1ce2f6f74ffd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ef8cfc2a8485a45ac3156a277617c3eacdd8a5b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612800"
---
# <a name="firstis"></a>first_is

Aktarılacak ilk dizi öğesinin dizinini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ first_is(
   "expression"
) ]
```

### <a name="parameters"></a>Parametreler

*İfade*  
Bir veya daha fazla C dili ifadeleri. Boş bağımsız değişken yuvaları izin verilir.

## <a name="remarks"></a>Açıklamalar

**First_is** C++ özniteliği ile aynı işlevlere sahip [first_is](http://msdn.microsoft.com/library/windows/desktop/aa366831) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir dizi içinde bir bölümde belirtmek için çeşitli yollar gösterir:

```cpp
// cpp_attr_ref_first_is.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"

[module(name="MyLib")];

[object, uuid(11111111-1111-1111-1111-111111111111)]
__interface b
{
   [id(0), propget, bindable, displaybind, defaultbind,
requestedit] HRESULT get_I([out, retval]long *i);
   HRESULT Proc1([in] short First, [in] short Last,
[first_is(First), last_is(Last), size_is(Last-First)] char Arr1[]);
   HRESULT Proc2([in] short First, [in] short Last,
[last_is(First), size_is(Last)] char Arr2[]);
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|İçinde alan **yapı** veya **birleşim**, parametre arabirim, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)  
[Parametre Öznitelikleri](../windows/parameter-attributes.md)  
[last_is](../windows/last-is.md)  
[max_is](../windows/max-is.md)  
[length_is](../windows/length-is.md)  
[size_is](../windows/size-is.md)  