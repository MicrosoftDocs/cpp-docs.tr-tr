---
title: nesne (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: c0c0ff552d8a33ebe70f56b9b186e963cc8e9b3d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843111"
---
# <a name="object-c"></a>nesne (C++)

Özel bir arabirim tanımlar.

## <a name="syntax"></a>Syntax

```cpp
[object]
```

## <a name="remarks"></a>Açıklamalar

Bir arabirim tanımından önce, **nesne** C++ özniteliği arabirimin. IDL dosyasına özel bir arabirim olarak yerleştirilmesine neden olur.

Nesne ile işaretlenen herhangi bir arabirim öğesinden devralması gerekir `IUnknown` . Taban arabirimlerinden herhangi biri öğesinden devraldığı takdirde bu durum karşılanır `IUnknown` . Öğesinden hiçbir temel arabirim devralmadıysanız `IUnknown` , derleyici **nesne** ile işaretlenmiş arabirimin türetmesine neden olur `IUnknown` .

## <a name="example"></a>Örnek

**Nesnenin**nasıl kullanılacağına ilişkin bir örnek için bkz. [gözatılabilir](nonbrowsable.md) .

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**arayüz**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)<br/>
[çift](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[özel](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)
