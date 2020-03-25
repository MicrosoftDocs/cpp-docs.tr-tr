---
title: bağlanabilir (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.bindable
helpviewer_keywords:
- bindable attribute
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
ms.openlocfilehash: 9e476183374ad2a70864fd46aaa19c616cd3ce91
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167361"
---
# <a name="bindable"></a>bağlanabilir

Özelliğin veri bağlamayı desteklediğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[bindable]
```

## <a name="remarks"></a>Açıklamalar

**Bağlanabilir** C++ öznitelik, [bağlanabilir](/windows/win32/Midl/bindable) MIDL özniteliğiyle aynı işlevselliğe sahiptir. Bunu [propget](propget.md), [propput](propput.md)veya [propputref](propputref.md) öznitelikleriyle tanımlanan özelliklerde kullanabilir ya da bağlanabilir bir yöntemi el ile tanımlayabilirsiniz.

Aşağıdaki MFC örnekleri, **bağlanabilir**kullanımını gösterir:

- [Denetimler örnekleri: MFC tabanlı ActiveX denetimleri](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/controls)

- [CIRC örneği: ActiveX denetimi](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/controls)

- [TESTHELP örneği: araç Ipuçları ve yardım ile ActiveX denetimi](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/controls)

## <a name="example"></a>Örnek

Aşağıdaki kod, bir özellikte **bağlanabilir** özelliği nasıl kullanabileceğinizi gösterir:

```cpp
// cpp_attr_ref_bindable.cpp
// compile with: /LD
#include <windows.h>
[
   uuid("479B29E3-9A2C-11D0-B696-00A0C903487A"), dispinterface, helpstring("property demo Interface")
]
__interface IPropDemo : IDispatch {

   [propget, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);
   [propput, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);
   [id(3), bindable, propget] HRESULT Object([out, retval] IDispatch **ppObj);
   [id(3), bindable, propputref] HRESULT Object([in] IDispatch* pObj);
   [id(-552), helpstring("method AboutBox")] HRESULT AboutBox();
};

[ module(name="PropDemoLib", uuid="479B29E2-9A2C-11D0-B696-00A0C903487A", version="1.0", helpstring="property demo") ];
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Interface yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)
