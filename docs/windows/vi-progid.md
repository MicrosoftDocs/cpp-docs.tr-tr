---
title: vi_progid | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.vi_progid
dev_langs:
- C++
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4798cf5c283fc4a663da0e1af7110df63496a6c9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408251"
---
# <a name="viprogid"></a>vi_progid

ProgID sürümden bağımsız biçimi belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ vi_progid(
   name
) ];
```

### <a name="parameters"></a>Parametreler

*Adı*<br/>
Sürüm bağımsız ProgID temsil eden nesne.

Progid'ler COM/ActiveX nesneleri tanımlamak için kullanılan sınıf tanımlayıcısı (CLSID) kullanıcı tarafından okunabilen bir sürümü var.

## <a name="remarks"></a>Açıklamalar

**Vi_progid** C++ özniteliği sürümden bağımsız bir COM nesnesi için bir ProgID belirtmenize olanak sağlar. Bir ProgID formundadır *name1.name2.version*. Sürümden bağımsız bir ProgID bulunmayan bir *sürüm*. Her ikisini de belirtmek mümkündür `progid` ve **vi_progid** üzerinde öznitelikleri bir `coclass`. Siz belirtmezseniz **vi_progid**, sürüm bağımsız ProgID tarafından belirtilen değerdir [ProgID](../windows/progid.md) özniteliği.

**vi_progid** gelir `coclass` belirtirseniz, diğer bir deyişle, öznitelik **vi_progid**, belirtmekle aynı şeydir `coclass` ve **vi_progid** öznitelikleri.

**Vi_progid** özniteliği bir sınıf belirtilen adla otomatik olarak kaydedilecek neden olur. Oluşturulan .idl dosyasının ProgID değeri görüntülemez.

ATL projelerinde, [coclass'ı](../windows/coclass.md) öznitelik varsa Ayrıca, belirtilen ProgID tarafından kullanılan `GetVersionIndependentProgID` işlevi (tarafından eklenen `coclass` özniteliği).

## <a name="example"></a>Örnek

Bkz: [coclass'ı](../windows/coclass.md) örnek kullanımını örneğin **vi_progid**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf Öznitelikleri](../windows/class-attributes.md)<br/>
[ProgID anahtarı](/windows/desktop/com/-progid--key)  
