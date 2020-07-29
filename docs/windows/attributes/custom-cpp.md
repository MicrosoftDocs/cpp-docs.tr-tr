---
title: özel (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 185517720af7e61f6a04068e8868d258a51f262f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215328"
---
# <a name="custom-c"></a>özel (C++)

Tür kitaplığındaki bir nesne için meta verileri tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
[ custom(
   uuid,
   value
) ];
```

### <a name="parameters"></a>Parametreler

*uuid*<br/>
Benzersiz bir KIMLIK.

*deeri*<br/>
Bir varyanta koyabileceğiniz bir değer.

## <a name="remarks"></a>Açıklamalar

**Özel** C++ özniteliği, bilgilerin tür kitaplığına yerleştirilmesine neden olur. Tür kitaplığından özel değeri okuyan bir araca ihtiyacınız olacak.

**Özel** öznitelik [özel](/windows/win32/Midl/custom) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Şunlara uygulanır**|COM olmayan **arabirim**, **`class`** , **`enum`** s, `idl_module` Yöntemler, arabirim üyeleri, arabirim parametreleri, **`typedef`** **`union`** **`struct`** s, s, s|
|**Tekrarlanabilir**|Yes|
|**Gerekli öznitelikler**|**coclass** (sınıfında kullanıldığında)|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)
