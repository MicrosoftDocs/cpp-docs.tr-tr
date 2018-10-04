---
title: Özel (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.custom
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5a491c120dff7f8f505878d6887498eb5f05fb22
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789893"
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