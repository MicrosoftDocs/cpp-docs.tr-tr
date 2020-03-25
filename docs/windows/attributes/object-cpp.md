---
title: nesne (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: 4545d899c13a1eabf8ea5fb6fe3918fb5f05b626
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214715"
---
# <a name="object-c"></a>nesne (C++)

Özel bir arabirim tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[object]
```

## <a name="remarks"></a>Açıklamalar

Bir arabirim tanımından önce, **nesne** C++ özniteliği arabirimin. IDL dosyasına özel bir arabirim olarak yerleştirilmesine neden olur.

Nesne ile işaretlenen herhangi bir arabirim `IUnknown`devralması gerekir. Temel arabirimlerin herhangi biri `IUnknown`devraldığı takdirde bu durum karşılanır. `IUnknown`hiçbir temel arabirim devralmadıysanız, derleyici **nesne** ile işaretlenen arabirimin `IUnknown`türetmesine neden olur.

## <a name="example"></a>Örnek

**Nesnenin**nasıl kullanılacağına ilişkin bir örnek için bkz. [gözatılabilir](nonbrowsable.md) .

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[custom](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)
