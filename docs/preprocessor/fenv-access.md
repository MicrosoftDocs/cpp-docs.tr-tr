---
title: fenv_access pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
ms.openlocfilehash: c8e66881bde12df28bf24e18230471cb4caca792
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218598"
---
# <a name="fenv_access-pragma"></a>fenv_access pragması

Kayan nokta ortam bayrağı testlerini ve moddeğişikliklerini değiştirecek (**Açık**) veya mümkün olan iyileştirmeleri devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> **#pragma fenv_access (** { **on** | **off** } **)**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **fenv_access** **kapalıdır**. Derleyici, kodunuzun kayan nokta ortamına erişeceğini veya onu işlemez olduğunu varsayabilir ve birçok kayan nokta kodu iyileştirmesi gerçekleştirebilir. Derleyiciye kodunuzun kayan nokta ortamına eriştiğini, test durum bayraklarını, özel durumları veya Denetim modu bayraklarını ayarlamak için **fenv_access** olarak **Açık** olarak ayarlayın. Derleyici bu iyileştirmeleri devre dışı bırakarak kodunuzun kayan nokta ortamına tutarlı bir şekilde erişmesini sağlayabilir.

Kayan nokta davranışı hakkında daha fazla bilgi için bkz. [/FP (kayan nokta davranışını belirt)](../build/reference/fp-specify-floating-point-behavior.md).

**Fenv_access** 'e tabi olan iyileştirme türleri şunlardır:

- Küresel genel alt ifade eleme

- Kod hareketi

- Sabit katlama

Diğer kayan nokta pragmaları şunlardır:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Örnekler

Bu örnek, 24 bit duyarlık için kayan nokta denetim kaydını ayarlamak üzere **fenv_access** öğesini **on** olarak ayarlar:

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

Önceki örnekten yorum `#pragma fenv_access (on)` yaptıysanız, derleyici, Denetim modunu kullanmayan derleme zamanı değerlendirmesi yaptığından, çıktının farklı olduğunu unutmayın.

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
