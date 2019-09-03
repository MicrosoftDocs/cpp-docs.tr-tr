---
title: conform pragması
ms.date: 08/29/2019
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
ms.openlocfilehash: 816ff85bb19f549c6ea072073bd89fcd503545f2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220506"
---
# <a name="conform-pragma"></a>conform pragması

**C++Belirli**

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneğinin çalışma zamanı davranışını belirtir.

## <a name="syntax"></a>Sözdizimi

> **#pragma uyumlu (** *ad* [ **, show** ] [ **,** { **on** | **off** }] [[ **,** { **Push** | **pop** }] [ **,** *tanımlayıcı* [ **,** { **on** **kapalı}** ]  |  ] ] **)**

### <a name="parameters"></a>Parametreler

*ada*\
Değiştirilecek derleyici seçeneğinin adını belirtir. Geçerli tek *ad* `forScope`.

**göster**\
Seçim Geçerli *adın* (true veya false) derleme sırasında bir uyarı mesajı aracılığıyla görüntülenmesine neden olur. Örneğin: `#pragma conform(forScope, show)`.

**Açık**, **kapalı**\
Seçim *Name* ayarının **on** olarak ayarlanması [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneğini sağlar. Varsayılan değer **kapalıdır**.

**hareketle**\
Seçim *Adın* geçerli değerini iç derleyici yığınına iter. *Tanımlayıcıyı*belirtirseniz, bir *adın* yığına itilmesi için **Açık** veya **kapalı** değerini belirtebilirsiniz. Örneğin: `#pragma conform(forScope, push, myname, on)`.

**cağımız**\
Seçim *Ad* değerini, iç derleyici yığınının en üstünde bulunan değere ayarlar ve sonra yığını açılır. Tanımlayıcı, **pop**ile belirtilirse, *tanımlayıcı*içeren kayıt bulunana kadar yığın geri alınır; bu da silinecek. yığındaki bir sonraki kayıttaki *ad* için geçerli değer, *ad*için yeni bir değer haline gelir. Yığın üzerinde bir kayıtta olmayan bir *tanımlayıcı* içeren **pop** belirtirseniz, **pop** yok sayılır.

*Tanımlayıcısını*\
Seçim **Push** veya **pop** komutuna eklenebilir. *Tanımlayıcı* kullanılıyorsa, bir **Açık** veya **kapalı** belirticisi de kullanılabilir.

## <a name="example"></a>Örnek

```cpp
// pragma_directive_conform.cpp
// compile with: /W1
// C4811 expected
#pragma conform(forScope, show)
#pragma conform(forScope, push, x, on)
#pragma conform(forScope, push, x1, off)
#pragma conform(forScope, push, x2, off)
#pragma conform(forScope, push, x3, off)
#pragma conform(forScope, show)
#pragma conform(forScope, pop, x1)
#pragma conform(forScope, show)

int main() {}
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
