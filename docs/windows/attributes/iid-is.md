---
title: iid_is (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.iid_is
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
ms.openlocfilehash: b91fb7937bb0e20f2500eace9695bc0ddba21b26
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038563"
---
# <a name="iidis"></a>iid_is

Bir arabirim işaretçisi tarafından işaret edilen COM arabirimi Laboratuvardaki belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ iid_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*İfade*<br/>
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
|**Geçersiz öznitelikler**|None|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)