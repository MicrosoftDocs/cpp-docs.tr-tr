---
title: bağlanabilir (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.bindable
helpviewer_keywords:
- bindable attribute
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
ms.openlocfilehash: 07f446b946d6703c4a8b9ae59ae0edd8172c6879
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037243"
---
# <a name="bindable"></a>bağlanabilir

Özelliğin veri bağlamayı desteklediğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[bindable]
```

## <a name="remarks"></a>Açıklamalar

**Bağlanabilir** C++ özniteliği ile aynı işlevlere sahip [bağlanabilir](/windows/desktop/Midl/bindable) MIDL özniteliği. Özellikleri ile tanımlanmış kullanabilirsiniz [propget](propget.md), [propput](propput.md), veya [propputref](propputref.md) öznitelikleri veya el ile tanımlayabilir bağlanabilir bir yöntem.

Aşağıdaki MFC örnekleri kullanımı Göster **bağlanabilir**:

- [Denetim örnekleri: MFC tabanlı ActiveX denetimleri](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/controls)

- [DAİ örneği: ActiveX denetimi](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/controls)

- [TESTHELP örneği: Araç ipuçları ve Yardım ActiveX denetimi](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/controls)

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanabileceğinizi gösterir **bağlanabilir** özellikte:

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
|**Uygulandığı öğe:**|Arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)