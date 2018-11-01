---
title: özel (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 7aca125879591f71fe2ba60f34b712918350940f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565704"
---
# <a name="custom-c"></a>özel (C++)

Bir nesne için meta verileri tür kitaplığındaki tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ custom(
   uuid,
   value
) ];
```

### <a name="parameters"></a>Parametreler

*uuid*<br/>
Benzersiz kimliği

*value*<br/>
Bir değişken koyabilirsiniz bir değer.

## <a name="remarks"></a>Açıklamalar

**Özel** C++ özniteliği tür kitaplığına yerleştirilecek bilgi neden olur. Tür kitaplığından özel değeri okuyan bir aracı gerekir.

**Özel** özniteliği ile aynı işlevlere sahip [özel](/windows/desktop/Midl/custom) MIDL özniteliği.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|COM olmayan **arabirimi**, **sınıfı**, **enum**s, `idl_module` yöntemleri, arabirim üyeleri, arabirim parametrelerini **typedef**s, **birleşim**s, **yapı**s|
|**Tekrarlanabilir**|Evet|
|**Gerekli öznitelikleri**|**coclass'ı** (sınıfı kullanıldığında)|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)