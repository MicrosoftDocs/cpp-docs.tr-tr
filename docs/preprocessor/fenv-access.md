---
title: fenv_access | Microsoft Docs
ms.custom: ''
ms.date: 03/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c06556d47bf0c471aa7e4fab610971e2b7ad11e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081475"
---
# <a name="fenvaccess"></a>fenv_access
Devre dışı bırakır (**üzerinde**) ya da etkinleştirir (**kapalı**) kayan nokta ortam değişebilir iyileştirmeleri, testleri ve modu değişiklikleri bayrak.

## <a name="syntax"></a>Sözdizimi

> **#pragma fenv_access (** { **üzerinde** | **kapalı** } **)**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **fenv_access** olduğu **kapalı**. Derleyici, kabul edilebilir değilse kodunuzu erişemeyebilir veya kayan nokta ortamını işleyin ve ardından birçok kayan nokta kodu en iyi duruma getirme gerçekleştirebilirsiniz. Ayarlama **fenv_access** için **üzerinde** derleyici kodunuzu kayan nokta ortamın durumu bayrakları, özel durumlar, test etmek için ya da Denetim modu bayrakları ayarlamanızı erişimi olduğunu bildirmek için. Böylece kodunuzu kayan nokta ortam tutarlı bir şekilde erişebilir, derleyici bu iyileştirmeler devre dışı bırakır.

Kayan nokta davranışı hakkında daha fazla bilgi için bkz. [FP (Floating-Point davranışını belirtin)](../build/reference/fp-specify-floating-point-behavior.md).

Tabi olan en iyi duruma getirme türlerini **fenv_access** şunlardır:

- Genel Genel alt ifade ortadan kaldırma

- Kod Ara

- Sabit bir Katlama

Diğer kayan nokta pragmaları şunlardır:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Örnekler

Bu örnekte ayarlar **fenv_access** için **üzerinde** 24 bit duyarlık kayan nokta denetim kaydı ayarlamak için:

```cpp
// pragma_directive_fenv_access_x86.cpp
// compile with: /O2
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
out=9.999999776482582e-003
```

Çıkarırsanız `#pragma fenv_access (on)` önceki örnekten derleyici denetim modunu kullanmaz derleme zamanı değerlendirmesi, çünkü çıkış farklı olduğunu unutmayın.

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2
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
out=1.000000000000000e-002
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
