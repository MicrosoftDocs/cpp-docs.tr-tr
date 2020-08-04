---
title: özel (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 7a1d9bd64a28fa7c08477c6011dc0e8236b7bcf6
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87521258"
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

- **Uygulama hedefi**: com dışı `interface` , `idl_module` Yöntemler, arabirim üyeleri, arabirim parametreleri,,,, **`typedef`** **`class`** **`enum`** **`union`** ve **`struct`** türleri.
- **Yinelenebilir**: Evet.
- **Gerekli öznitelikler**: **coclass** (sınıfta kullanıldığında).
- **Geçersiz öznitelikler**: yok.

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)
