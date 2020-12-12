---
description: 'Daha fazla bilgi edinin: kimlik'
title: kimlik (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 04f7144e1c6f8b6655b0b6be23e0ffa4f22dc27c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180207"
---
# <a name="id"></a>kimlik

Bir üye işlev için bir *DISPID* parametresi belirtir (bir özellik veya bir yöntem, bir arabirim veya dispınterface).

## <a name="syntax"></a>Sözdizimi

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Arabirim yöntemi için dağıtım KIMLIĞI.

## <a name="remarks"></a>Açıklamalar

**İd** C++ özniteliği, [ID](/windows/win32/Midl/id) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Kimliği** nasıl kullanacağınızı gösteren bir [örnek için bkz](bindable.md) ..

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Interface yöntemi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[Veri üyesi öznitelikleri](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
['ndaki](in-cpp.md)<br/>
[dışı](out-cpp.md)
