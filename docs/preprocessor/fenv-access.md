---
title: fenv_access pragması
description: Fenv_access pragma yönergesinin kullanımını ve etkilerini açıklar. Fenv_access yönergesi, çalışma zamanında kayan nokta ortamına erişimi denetler.
ms.date: 11/19/2019
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
ms.openlocfilehash: e03eb404f2805a4f7c96509600c063c1b1acf629
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305849"
---
# <a name="fenv_access-pragma"></a>fenv_access pragması

Kayan nokta ortam bayrağı testlerini ve mod değişikliklerini**değiştirecek (** **Açık**) veya mümkün olan iyileştirmeleri devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> **#pragma fenv_access (** { **on** | **off** } **)**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak **fenv_access** **kapalıdır**. Derleyici, kodunuzun kayan nokta ortamına erişmediğini veya onu işlemediğini varsayar. Ortam erişimi gerekmiyorsa, derleyici, kayan nokta kodunuzu iyileştirmek için daha fazlasını yapabilir.

Kodunuz kayan nokta durum bayraklarını, özel durumları veya Denetim modu bayraklarını test ettikten sonra **fenv_access** etkinleştirin. Derleyici kayan nokta iyileştirmelerini devre dışı bırakır, böylece kodunuzun kayan nokta ortamına tutarlı bir şekilde erişebilmesini sağlayabilirsiniz.

[/FP: Strict] komut satırı seçeneği **fenv_access**otomatik olarak etkinleştirilir. Bu ve diğer kayan nokta davranışı hakkında daha fazla bilgi için bkz. [/FP (kayan nokta davranışını belirt)](../build/reference/fp-specify-floating-point-behavior.md).

**Fenv_access** pragma 'ı diğer kayan nokta ayarları ile birlikte kullanmanın yolları hakkında kısıtlamalar vardır:

- Kesin anlambilim etkinleştirilmediği takdirde **fenv_access** etkinleştiremezsiniz. Kesin anlambilim [float_control](float-control.md) pragma tarafından ya da [/FP: kesin](../build/reference/fp-specify-floating-point-behavior.md) veya [/FP: Strict](../build/reference/fp-specify-floating-point-behavior.md) derleyici seçenekleri kullanılarak etkinleştirilebilir. Diğer bir kayan nokta komut satırı seçeneği belirtilmemişse, derleyici varsayılan olarak **/FP: kesin** olarak ayarlanır.

- **Fenv_access (açık)** ayarlandığında kesin semantiğini devre dışı bırakmak için **float_control** kullanamazsınız.

**Fenv_access** tabi olan iyileştirmelerin türleri şunlardır:

- Küresel genel alt ifade eleme

- Kod hareketi

- Sabit katlama

Diğer kayan nokta pragmaları şunlardır:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Örnekler

Bu örnek, 24 bit duyarlık için kayan nokta denetim kaydını ayarlamak üzere **fenv_access** **Açık** olarak ayarlar:

```cpp
// pragma_directive_fenv_access_x86.cpp
// compile with: /O2 /arch:IA32
// processor: x86
#include <stdio.h>
#include <float.h>
#include <errno.h>
#pragma fenv_access (on)

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=9.999999776482582e-03
```

Önceki örnekten `#pragma fenv_access (on)` yorum yaptığınızda çıktı farklıdır. Bunun nedeni, derleyicinin, Denetim modunu kullanmayan derleme zamanı değerlendirmesi gerçekleştirmesinden kaynaklanır.

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2 /arch:IA32
#include <stdio.h>
#include <float.h>

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=1.000000000000000e-02
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
