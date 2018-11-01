---
title: fp_contract
ms.date: 03/12/2018
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
ms.openlocfilehash: 14c3ac60d4fc0f45fcf0ece6c3f73153e5de4271
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476511"
---
# <a name="fpcontract"></a>fp_contract

Kayan nokta kısaltmanın gerçekleşmeden olup olmadığını belirler. Kayan nokta kısaltmanın iki ayrı kayan nokta işlemleri tek bir yönerge halinde birleştiren FMA (Fused-Çarp-Ekle) gibi bir yönergedir. Bu yönergelerin kullanımını, her işlemden sonra yuvarlama yerine işlemci yalnızca bir kez hem işlemlerinden sonra yuvarlak çünkü kayan nokta duyarlığını etkileyebilir.

## <a name="syntax"></a>Sözdizimi

> **#pragma fp_contract (** { **üzerinde** | **kapalı** } **)**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **fp_contract** olduğu **üzerinde**. Bu, derleyicinin kayan nokta kısaltmanın yönergeleri mümkün olan yerlerde kullanın bildirir. Ayarlama **fp_contract** için **kapalı** tek kayan nokta yönergeleri korumak için.

Kayan nokta davranışı hakkında daha fazla bilgi için bkz. [FP (Floating-Point davranışını belirtin)](../build/reference/fp-specify-floating-point-behavior.md).

Diğer kayan nokta pragmaları şunlardır:

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>Örnek

Hedef işlemci üzerinde mevcut olsa bile bu örnekten oluşturulan kod çarpım-Çarp-Ekle bir yönerge kullanmaz. Çıkarırsanız `#pragma fp_contract (off)`, varsa, oluşturulan kod çarpım-Çarp-Ekle bir yönerge kullanabilir.

```cpp
// pragma_directive_fp_contract.cpp
// on x86 and x64 compile with: /O2 /fp:fast /arch:AVX2
// other platforms compile with: /O2

#include <stdio.h>

// remove the following line to enable FP contractions
#pragma fp_contract (off)

int main() {
   double z, b, t;

   for (int i = 0; i < 10; i++) {
      b = i * 5.5;
      t = i * 56.025;

      z = t * i + b;
      printf("out = %.15e\n", z);
   }
}
```

```Output
out = 0.000000000000000e+00
out = 6.152500000000000e+01
out = 2.351000000000000e+02
out = 5.207249999999999e+02
out = 9.184000000000000e+02
out = 1.428125000000000e+03
out = 2.049900000000000e+03
out = 2.783725000000000e+03
out = 3.629600000000000e+03
out = 4.587525000000000e+03
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
