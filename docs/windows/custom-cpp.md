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
ms.openlocfilehash: cb5a3ebbf3ecf1454745d507fc2f2b6f792768ac
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600427"
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

*uuid*  
Benzersiz kimliği

*value*  
Bir değişken koyabilirsiniz bir değer.

## <a name="remarks"></a>Açıklamalar

**Özel** C++ özniteliği tür kitaplığına yerleştirilecek bilgi neden olur. Tür kitaplığından özel değeri okuyan bir aracı gerekir.

**Özel** özniteliği ile aynı işlevlere sahip [özel](http://msdn.microsoft.com/library/windows/desktop/aa366766) MIDL özniteliği.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|COM olmayan **arabirimi**, **sınıfı**, **enum**s, `idl_module` yöntemleri, arabirim üyeleri, arabirim parametrelerini **typedef**s, **birleşim**s, **yapı**s|
|**Tekrarlanabilir**|Evet|
|**Gerekli öznitelikleri**|**coclass'ı** (sınıfı kullanıldığında)|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Tek Başına Öznitelikler](../windows/stand-alone-attributes.md)  
[Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)  
[Parametre Öznitelikleri](../windows/parameter-attributes.md)  
[Yöntem Öznitelikleri](../windows/method-attributes.md)  
[Sınıf Öznitelikleri](../windows/class-attributes.md)  
[Arabirim Öznitelikleri](../windows/interface-attributes.md)  