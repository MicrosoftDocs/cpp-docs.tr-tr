---
description: 'Daha fazla bilgi edinin: Çift'
title: Dual (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dual
helpviewer_keywords:
- dual attribute
ms.assetid: 5d4a9069-d819-42cd-ba56-bbcda17157d9
ms.openlocfilehash: d1e72bd787bc73042b4f4a180ea119712021edaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112030"
---
# <a name="dual"></a>çift

. IDL dosyasına bir arabirimi çift arabirim olarak koyar.

## <a name="syntax"></a>Syntax

```cpp
[dual]
```

## <a name="remarks"></a>Açıklamalar

**Dual** C++ özniteliği bir arabirimden önceyse, arabirimin oluşturulan. IDL dosyasındaki kitaplık bloğunun içine yerleştirilmesine neden olur.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir arabirim tanımından önce **çift** kullanan bir öznitelik bloğuna sahiptir:

```cpp
// cpp_attr_ref_dual.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLibrary")];

[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), dual]

__interface IStatic : IDispatch
{
   HRESULT Func1(int i);
   [   propget,    id(1),    bindable,    displaybind,    defaultbind,    requestedit
   ]
   HRESULT P1([out, retval] long *nSize);
   [   propput,    id(1),    bindable,    displaybind,    defaultbind,    requestedit
   ]
   HRESULT P1([in] long nSize);
};

[cpp_quote("#include file.h")];
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**arayüz**|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|`dispinterface`|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Kullanıma göre öznitelikler](attributes-by-usage.md)<br/>
[Özel](custom-cpp.md)<br/>
[dispinterface](dispinterface.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)
