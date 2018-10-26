---
title: ProgID (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.progid
dev_langs:
- C++
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 239f50011c91320c2b5e0a96449139e8eeab10ff
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072870"
---
# <a name="progid"></a>progid

Bir COM nesnesi için ProgID belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>Parametreler

*Adı*<br/>
ProgID temsil eden nesne.

Progid'ler COM/ActiveX nesneleri tanımlamak için kullanılan sınıf tanımlayıcısı (CLSID) kullanıcı tarafından okunabilen bir sürümü var.

## <a name="remarks"></a>Açıklamalar

**ProgID** C++ özniteliği için bir COM nesnesi ProgID belirtmenize olanak sağlar. Bir ProgID formundadır *name1.name2.version*. Belirtmezseniz, bir *sürüm* bir program kimliği için varsayılan sürüm 1'dir. Siz belirtmezseniz *name1.name2*, varsayılan ad *classname.classname*. Siz belirtmezseniz **ProgID** ve belirttiğiniz `vi_progid`, *name1.name2* alınmıştır `vi_progid` ve (bir sonraki sıralı numara) sürüm eklenir.

Kullanan bir öznitelik bloğuna, **ProgID** ayrıca kullanmaz **UUID**, derleyici olmadığını görmek için kayıt defteri denetleyecek bir **UUID** belirtilen mevcut **program kimliği** . Varsa **ProgID** belirtilmezse, oluşturulacak sürümü (ve coclass'ı oluşturuyorsanız coclass'ı adı) kullanılacak bir **ProgID**.

**progid** gelir `coclass` belirtirseniz, diğer bir deyişle, öznitelik **ProgID**, belirtmekle aynı şeydir `coclass` ve **ProgID** öznitelikleri.

**ProgID** özniteliği bir sınıf belirtilen adla otomatik olarak kaydedilecek neden olur. Oluşturulan .idl dosyasının görüntülenmez **ProgID** değeri.

Bu öznitelik ATL kullanan bir proje içinde kullanıldığında, öznitelik davranışını değiştirir. Yukarıdaki davranışa ek olarak, bu öznitelik ile belirtilen bilgileri kullanılan `GetProgID` işlevi tarafından eklenen `coclass` özniteliği. Daha fazla bilgi için [coclass'ı](coclass.md) özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [coclass'ı](coclass.md) örnek kullanımı için **ProgID**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[ProgID anahtarı](/windows/desktop/com/-progid--key)
