---
title: iid_is | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.iid_is
dev_langs:
- C++
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 597d4c2e6fa9904906c2971c3c442a9f26779834
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215084"
---
# <a name="iidis"></a>iid_is

Bir arabirim işaretçisi tarafından işaret edilen COM arabirimi Laboratuvardaki belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ iid_is(
   "expression"
) ]
```

### <a name="parameters"></a>Parametreler

*İfade*  
Bir COM arabirimi Laboratuvardaki belirten C dil ifadesi için bir arabirim işaretçisi tarafından işaret.

## <a name="remarks"></a>Açıklamalar

**İid_is** C++ özniteliği ile aynı işlevlere sahip [iid_is](/windows/desktop/Midl/iid-is) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod kullanımını gösterir **iid_is**:

```cpp
// cpp_attr_ref_iid_is.cpp
// compile with: /LD
#include "wtypes.h"
#include "unknwn.h"
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl : IDispatch
{
   [id(1)] HRESULT CreateInstance([in] REFIID riid,[out, iid_is("riid")]
   IUnknown ** ppvObject);
};

[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Arabirimi parametresi, veri üyesi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Parametre Öznitelikleri](../windows/parameter-attributes.md)  