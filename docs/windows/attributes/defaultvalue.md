---
description: 'Daha fazla bilgi edinin: DefaultValue'
title: DefaultValue (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultvalue
helpviewer_keywords:
- defaultvalue attribute
ms.assetid: efa5d050-b2cc-4d9e-9b8e-79954f218d3a
ms.openlocfilehash: 907c736861d39064103af28917f35a97c0c7b1e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122167"
---
# <a name="defaultvalue"></a>defaultvalue

Türü belirtilmiş bir isteğe bağlı parametre için varsayılan değer belirtimine izin verir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ defaultvalue= value ]
```

### <a name="parameters"></a>Parametreler

*değer*<br/>
Parametresi için varsayılan değer.

## <a name="remarks"></a>Açıklamalar

**DefaultValue** C++ özniteliği, [DefaultValue](/windows/win32/Midl/defaultvalue) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, **DefaultValue** özniteliğini kullanarak bir arabirim yöntemi gösterir:

```cpp
// cpp_attr_ref_defaultvalue.cpp
// compile with: /LD
#include <windows.h>

[export] typedef long HRESULT;
[export, ptr, string] typedef unsigned char * MY_STRING_TYPE;

[  uuid("479B29EE-9A2C-11D0-B696-00A0C903487A"), dual, oleautomation, helpstring("IFireTabCtrl Interface"), helpcontext(122), pointer_default(unique) ]

__interface IFireTabCtrl : IDispatch {
   [bindable, propget] HRESULT get_Size([out, retval, defaultvalue("33")] long *nSize);
   [bindable, propput] HRESULT put_Size([in] int nSize);
};

[ module(name="ATLFIRELib", uuid="479B29E1-9A2C-11D0-B696-00A0C903487A",    version="1.0", helpstring="ATLFire 1.0 Type Library") ];
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Arabirim parametresi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)<br/>
[dışı](out-cpp.md)<br/>
[retval](retval.md)<br/>
['ndaki](in-cpp.md)<br/>
[pointer_default](pointer-default.md)<br/>
[eşi](unique-cpp.md)
