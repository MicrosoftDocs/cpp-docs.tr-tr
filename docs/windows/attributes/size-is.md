---
title: size_is (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.size_is
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
ms.openlocfilehash: dd0ec8622dfffdf9a0578c86d75d313042cc3c01
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841772"
---
# <a name="size_is"></a>size_is

Boyutlandırılmış işaretçiler için ayrılan bellek boyutunu, boyutlandırılmış işaretçilere boyutlandırılmış boyutları ve tek veya çok boyutlu dizileri belirtin.

## <a name="syntax"></a>Söz dizimi

```cpp
[ size_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*ifadesini*<br/>
Boyutlandırılmış işaretçiler için ayrılan bellek boyutu.

## <a name="remarks"></a>Açıklamalar

**Size_is** C++ özniteliği, [size_is](/windows/win32/Midl/size-is) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Dizinin bir bölümünü belirtme örneği için [first_is](first-is.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`struct`** Or **`union`** , Interface parametresi, Interface yöntemi içindeki alan|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|`max_is`|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)
