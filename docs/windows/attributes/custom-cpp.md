---
title: özel (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: f51b0210fff4db5be359fa94237f4d7c77b4fef2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214896"
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
|**Uygulama hedefi**|COM dışı **arabirim**, **sınıf**, **enum**s, `idl_module` yöntemleri, arabirim üyeleri, arabirim parametreleri, **typedef**, **birleşim**s, **Yapı**s|
|**Tekrarlanabilir**|Yes|
|**Gerekli öznitelikler**|**coclass** (sınıfında kullanıldığında)|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)
