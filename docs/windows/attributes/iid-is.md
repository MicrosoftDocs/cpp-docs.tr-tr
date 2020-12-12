---
description: 'Hakkında daha fazla bilgi edinin: iid_is'
title: iid_is (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.iid_is
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
ms.openlocfilehash: 9de6d636fbb189ece9aedec95cb9460c2ccbb5a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183106"
---
# <a name="iid_is"></a>iid_is

Bir arabirim işaretçisi tarafından işaret edilen COM arabiriminin IID 'sini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ iid_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*expression*<br/>
Bir arabirim işaretçisi tarafından işaret edilen bir COM arabiriminin IID öğesini belirten bir C dili ifadesi.

## <a name="remarks"></a>Açıklamalar

**İid_is** C++ özniteliği, [iid_is](/windows/win32/Midl/iid-is) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod **iid_is** kullanımını gösterir:

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Arabirim parametresi, veri üyesi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)
