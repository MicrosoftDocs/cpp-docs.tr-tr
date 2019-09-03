---
title: fp_contract pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
ms.openlocfilehash: 833d8e7f4b8c9da18901610e52afed619468c5c3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218568"
---
# <a name="fp_contract-pragma"></a>fp_contract pragması

Kayan nokta dalgalanıp gerçekleşmeyeceğini belirler. Kayan nokta karşıtı, iki ayrı kayan nokta işlemini tek bir yönergede birleştiren FMA (Fkullandınız-çarp-Add) gibi bir yönergedir. Bu yönergelerin kullanılması kayan nokta duyarlığını etkileyebilir, çünkü her işlemden sonra yuvarlama yerine, işlemci her iki işlemden sonra yalnızca bir kez yer alabilir.

## <a name="syntax"></a>Sözdizimi

> **#pragma fp_contract (** { **on** | **off** } **)**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **fp_contract** 'dir. Bu, derleyiciye mümkün olan yerlerde kayan nokta karşıtı yönergeler kullanmasını söyler. Tek kayan nokta talimatlarını korumak için **fp_contract** ayarlayın.

Kayan nokta davranışı hakkında daha fazla bilgi için bkz. [/FP (kayan nokta davranışını belirt)](../build/reference/fp-specify-floating-point-behavior.md).

Diğer kayan nokta pragmaları şunlardır:

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>Örnek

Bu örnekten oluşturulan kod, hedef işlemcide kullanılabilir olduğunda bile, Fuse-çarp-Add yönergesini kullanmaz. Dışarı `#pragma fp_contract (off)`yorum yaptıysanız oluşturulan kod, varsa, bir Fuse-çarp-Add yönergesi kullanabilir.

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

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
