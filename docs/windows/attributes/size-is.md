---
description: 'Hakkında daha fazla bilgi edinin: size_is'
title: size_is (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.size_is
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
ms.openlocfilehash: f61124dc286de1c8893f093454c921b4d6e46037
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329606"
---
# <a name="size_is"></a>size_is

Boyutlandırılmış işaretçiler için ayrılan bellek boyutunu, boyutlandırılmış işaretçilere boyutlandırılmış boyutları ve tek veya çok boyutlu dizileri belirtin.

## <a name="syntax"></a>Sözdizimi

```cpp
[ size_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*expression*<br/>
Boyutlandırılmış işaretçiler için ayrılan bellek boyutu.

## <a name="remarks"></a>Açıklamalar

**Size_is** C++ özniteliği, [size_is](/windows/win32/Midl/size-is) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Dizinin bir bölümünü belirtme örneği için [first_is](first-is.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`struct`** Or **`union`** , Interface parametresi, Interface yöntemi içindeki alan|
|**Yinelenebilir**|Hayır|
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
