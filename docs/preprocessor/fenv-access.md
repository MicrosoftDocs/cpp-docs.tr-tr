---
title: fenv_access pragma
description: Fenv_access yönergesinin kullanımını ve etkilerini açıklar pragma . Fenv_access yönergesi, çalışma zamanında kayan nokta ortamına erişimi denetler.
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragma, fenv_access
- fenv_access pragma
no-loc:
- pragma
ms.openlocfilehash: be33bbf9de381850ec78ece204d117ebc537152b
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713668"
---
# <a name="fenv_access-no-locpragma"></a>`fenv_access` pragma

**`on`** **`off`** Kayan nokta ortam bayrağı testlerini ve mod değişikliklerini değiştirecek () veya () iyileştirmelerini devre dışı bırakır.

## <a name="syntax"></a>Syntax

> **`#pragma fenv_access (`** { **`on`** | **`off`** } **`)`**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **`fenv_access`** **`off`** . Derleyici, kodunuzun kayan nokta ortamına erişmediğini veya onu işlemediğini varsayar. Ortam erişimi gerekmiyorsa, derleyici, kayan nokta kodunuzu iyileştirmek için daha fazlasını yapabilir.

**`fenv_access`** Kodunuz kayan nokta durum bayraklarını, özel durumları veya Denetim modu bayraklarını test ettikten sonra etkinleştirin. Derleyici kayan nokta iyileştirmelerini devre dışı bırakır, böylece kodunuzun kayan nokta ortamına tutarlı bir şekilde erişebilmesini sağlayabilirsiniz.

[/FP: Strict] komut satırı seçeneği otomatik olarak etkinleştirilir **`fenv_access`** . Bu ve diğer kayan nokta davranışı hakkında daha fazla bilgi için bkz. [/FP (Floating-Point davranışını belirt)](../build/reference/fp-specify-floating-point-behavior.md).

**`fenv_access`** pragma Diğer kayan nokta ayarları ile birlikte kullanmanın yolları konusunda kısıtlamalar vardır:

- **`fenv_access`** Kesin anlambilim etkinleştirilmediği takdirde etkinleştiremezsiniz. Kesin anlambilim, ya da [`float_control`](float-control.md) pragma [`/fp:precise`](../build/reference/fp-specify-floating-point-behavior.md) veya [`/fp:strict`](../build/reference/fp-specify-floating-point-behavior.md) derleyici seçenekleri kullanılarak etkinleştirilebilir. **`/fp:precise`** Diğer bir kayan nokta komut satırı seçeneği belirtilmemişse, derleyici varsayılan olarak ayarlanır.

- **`float_control`** Ayarlandığında kesin semantiğini devre dışı bırakmak için kullanamazsınız **`fenv_access(on)`** .

Uygulamasına tabi olan iyileştirmelerin türleri **`fenv_access`** şunlardır:

- Küresel genel alt ifade eleme

- Kod hareketi

- Sabit katlama

Diğer kayan nokta pragma yönergeleri şunlardır:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Örnekler

Bu örnek **`fenv_access`** **`on`** , 24 bit duyarlık için kayan nokta denetim kaydını ayarlamak üzere olarak ayarlanır:

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

Önceki örnekten yorum yaparsanız `#pragma fenv_access (on)` , çıktı farklıdır. Bunun nedeni, derleyicinin, Denetim modunu kullanmayan derleme zamanı değerlendirmesi gerçekleştirmesinden kaynaklanır.

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

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
