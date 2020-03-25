---
title: iid_is (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.iid_is
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
ms.openlocfilehash: 627ecff4835386dc70a9f3dfac0500404a84eefe
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167998"
---
# <a name="iid_is"></a>iid_is

Bir arabirim işaretçisi tarafından işaret edilen COM arabiriminin IID 'sini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ iid_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*ifadesini*<br/>
Bir arabirim işaretçisi tarafından işaret edilen bir COM arabiriminin IID öğesini belirten bir C dili ifadesi.

## <a name="remarks"></a>Açıklamalar

**İid_is** C++ özniteliği [iid_is](/windows/win32/Midl/iid-is) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Arabirim parametresi, veri üyesi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)
