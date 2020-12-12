---
description: 'Hakkında daha fazla bilgi edinin: gözatılabilir'
title: gözatılabilir (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonbrowsable
helpviewer_keywords:
- nonbrowsable attribute
ms.assetid: e71a98e7-4b65-454a-9829-342b9f2a84be
ms.openlocfilehash: 943458ff989a3f00d2ce33a4f5681a8bd29a76ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329771"
---
# <a name="nonbrowsable"></a>nonbrowsable

Bir arabirim üyesinin bir özellik tarayıcısında görüntülenmemesi gerektiğini belirtir.

## <a name="syntax"></a>Syntax

```cpp
[nonbrowsable]
```

## <a name="remarks"></a>Açıklamalar

**Gözatılabilir** C++ özniteliği, [gözatılabilir](/windows/win32/Midl/nonbrowsable) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_nonbrowsable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, helpstring("help string"), helpstringcontext(1),
uuid="11111111-1111-1111-1111-111111111111"]
__interface IMyI
{
   [nonbrowsable] HRESULT xx();
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Interface yöntemi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)
