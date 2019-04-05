---
title: public (C++ öznitelikleri) (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.public
helpviewer_keywords:
- public attribute
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
ms.openlocfilehash: a12ab0905064a72057dffac03340b667f07b3ae5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022833"
---
# <a name="public-c-attributes"></a>genel (C++ Öznitelikleri)

Bu gelen .idl dosyasında başvurulmuyor olsa bile bir typedef tür kitaplığına geçer sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[public]
```

## <a name="remarks"></a>Açıklamalar

**Genel** C++ özniteliği ile aynı işlevlere sahip [genel](/windows/desktop/Midl/public) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanılacağını gösterir **genel** özniteliği:

```cpp
// cpp_attr_ref_public.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, public] typedef long MEMBERID;

[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]
__interface IFireTabCtrl : IDispatch
{
   [id(2)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**typedef**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)