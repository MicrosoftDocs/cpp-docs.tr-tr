---
title: özel (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 19f28963a18abf42c6f629ac0f6491628387aa6d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491007"
---
# <a name="custom-c"></a>özel (C++)

Tür kitaplığındaki bir nesne için meta verileri tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ custom(
   uuid,
   value
) ];
```

### <a name="parameters"></a>Parametreler

*uuid*<br/>
Benzersiz bir KIMLIK.

*value*<br/>
Bir varyanta koyabileceğiniz bir değer.

## <a name="remarks"></a>Açıklamalar

**Özel** C++ öznitelik, bilgilerin tür kitaplığına yerleştirilmesine neden olur. Tür kitaplığından özel değeri okuyan bir araca ihtiyacınız olacak.

**Özel** öznitelik [özel](/windows/win32/Midl/custom) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|COM dışı **arabirim**, **sınıf**, **enum** `idl_module` s, Yöntemler, arabirim üyeleri, arabirim parametreleri, **typedef**, **birleşim**s, **Yapı**s|
|**Tekrarlanabilir**|Evet|
|**Gerekli öznitelikler**|**coclass** (sınıfında kullanıldığında)|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)