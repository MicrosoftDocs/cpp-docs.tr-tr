---
description: pragmaMicrosoft C/C++ ' da fp_contract yönergesi hakkında daha fazla bilgi edinin
title: fp_contract pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
helpviewer_keywords:
- pragma, fp_contract
- fp_contract pragma
no-loc:
- pragma
ms.openlocfilehash: 3263d1ec9675e0f8a9402ac7da78751b988e7bdf
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713655"
---
# <a name="fp_contract-no-locpragma"></a>`fp_contract` pragma

Kayan nokta dalgalanıp gerçekleşmeyeceğini belirler. Kayan nokta karşıtı, iki ayrı kayan nokta işlemini tek bir yönergede birleştiren FMA (Fkullandınız-çarp-Add) gibi bir yönergedir. Bu yönergelerin kullanılması kayan nokta duyarlığını etkileyebilir, çünkü her işlemden sonra yuvarlama yerine, işlemci her iki işlemden sonra yalnızca bir kez yer alabilir.

## <a name="syntax"></a>Syntax

> **`#pragma fp_contract (`** { **`on`** | **`off`** } **`)`**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **`fp_contract`** **`on`** . Bu, derleyiciye mümkün olan yerlerde kayan nokta karşıtı yönergeler kullanmasını söyler. **`fp_contract`** **`off`** Bağımsız kayan nokta talimatlarını korumak için olarak ayarlayın.

Kayan nokta davranışı hakkında daha fazla bilgi için bkz. [ `/fp` (kayan nokta davranışını belirt)](../build/reference/fp-specify-floating-point-behavior.md).

Diğer kayan nokta pragma yönergeleri şunlardır:

- [`fenv_access`](../preprocessor/fenv-access.md)

- [`float_control`](../preprocessor/float-control.md)

## <a name="example"></a>Örnek

Bu örnekten oluşturulan kod, hedef işlemcide kullanılabilir olduğunda bile, Fuse-çarp-Add yönergesini kullanmaz. Dışarı yorum yaptıysanız `#pragma fp_contract (off)` oluşturulan kod, varsa, bir Fuse-çarp-Add yönergesi kullanabilir.

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

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
