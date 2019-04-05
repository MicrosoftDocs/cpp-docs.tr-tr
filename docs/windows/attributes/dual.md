---
title: çift (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dual
helpviewer_keywords:
- dual attribute
ms.assetid: 5d4a9069-d819-42cd-ba56-bbcda17157d9
ms.openlocfilehash: 8f02f6b69b31f10b41d5c920cfc2ad62dfa1cef2
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023964"
---
# <a name="dual"></a>çift

Bir arabirim çift arabirim .idl dosyasına yerleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
[dual]
```

## <a name="remarks"></a>Açıklamalar

Zaman **çift** C++ özniteliği önündeki bir arabirim, oluşturulan .idl dosyasındaki kitaplığı bloğunun yerleştirilecek arabirimi neden olur.

## <a name="example"></a>Örnek

Aşağıdaki kodu kullanan bir öznitelik bloğudur **çift** arabirimi tanımından önce:

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**arabirim**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|`dispinterface`|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Kullanıma Göre Öznitelikler](attributes-by-usage.md)<br/>
[özel](custom-cpp.md)<br/>
[dispinterface](dispinterface.md)<br/>
[nesne](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)