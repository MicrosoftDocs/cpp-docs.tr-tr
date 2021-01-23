---
description: pragmaMicrosoft C/C++ ile uyumlu yönerge hakkında daha fazla bilgi edinin
title: uygundur pragma
ms.date: 01/22/2021
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragma, conform
no-loc:
- pragma
ms.openlocfilehash: baaeb41e2364daac8de91ca15251226bf3dd1e2a
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713707"
---
# <a name="conform-no-locpragma"></a>`conform` pragma

**C++ özel**

Derleyici seçeneğinin çalışma zamanı davranışını belirtir [`/Zc:forScope`](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) .

## <a name="syntax"></a>Syntax

> **`#pragma conform(`***Name* [ **`, show`** ] [ **`,`** { **`on`**  |  **`off`** }] [[ **`,`** { **`push`**  |  **`pop`** }] [ **`,`** *tanımlayıcı* [ **`,`** { **`on`**  |  **`off`** }]]]**`)`**

### <a name="parameters"></a>Parametreler

*ada*\
Değiştirilecek derleyici seçeneğinin adını belirtir. Geçerli tek *ad* `forScope` .

**`show`**\
Seçim Geçerli *adın* (true veya false) derleme sırasında bir uyarı mesajı aracılığıyla görüntülenmesine neden olur. Örneğin, `#pragma conform(forScope, show)`.

**`on`**, **`off`**\
Seçim *Name* ayarı **`on`** [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneğini sağlar. Varsayılan değer **`off`** .

**`push`**\
Seçim *Adın* geçerli değerini iç derleyici yığınına iter. *Tanımlayıcıyı* belirtirseniz, bir **`on`** **`off`** *adın* yığına itilmesi için veya değerini belirtebilirsiniz. Örneğin, `#pragma conform(forScope, push, myname, on)`.

**`pop`**\
Seçim *Ad* değerini, iç derleyici yığınının en üstünde bulunan değere ayarlar ve sonra yığını açılır. Tanımlayıcı ile belirtilirse **`pop`** , yığın, *tanımlayıcı* içeren kayıt bulunana kadar geri alınır ve bu da, yığındaki bir sonraki kayıttaki *adın* geçerli değeri, *ad* için yeni bir değer haline gelir. **`pop`** Yığındaki bir kayıtta olmayan bir *tanımlayıcı* ile belirtirseniz, **`pop`** yok sayılır.

*Tanımlayıcısını*\
Seçim Bir **`push`** veya **`pop`** komutuna eklenebilir. *Tanımlayıcı* kullanılıyorsa, **`on`** veya **`off`** belirleyicisi de kullanılabilir.

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

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
