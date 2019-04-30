---
title: Kimliği (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 5faf08418771deda3086a434cff6b1900a37e36e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409505"
---
# <a name="id"></a>kimlik

Belirtir bir *DISPID* (bir özellik veya bir arabirim veya dispinterface bir yöntem), bir üye işlev için parametre.

## <a name="syntax"></a>Sözdizimi

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
Arabirim yöntemi için gönderme kimliği.

## <a name="remarks"></a>Açıklamalar

**Kimliği** C++ özniteliği ile aynı işlevlere sahip [kimliği](/windows/desktop/Midl/id) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [bağlanabilir](bindable.md) nasıl kullanılacağına ilişkin bir örnek **kimliği**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|None|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Veri Üyesi Öznitelikleri](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)