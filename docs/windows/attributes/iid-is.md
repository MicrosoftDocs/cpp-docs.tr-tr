---
title: iid_is (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.iid_is
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
ms.openlocfilehash: 6a8fe8c7481cd251baff65293607733573f46ea6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832223"
---
# <a name="iid_is"></a>iid_is

Bir arabirim işaretçisi tarafından işaret edilen COM arabiriminin IID 'sini belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ iid_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*ifadesini*<br/>
Bir arabirim işaretçisi tarafından işaret edilen bir COM arabiriminin IID öğesini belirten bir C dili ifadesi.

## <a name="remarks"></a>Açıklamalar

**İid_is** C++ özniteliği, [iid_is](/windows/win32/Midl/iid-is) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod **iid_is**kullanımını gösterir:

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
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)
