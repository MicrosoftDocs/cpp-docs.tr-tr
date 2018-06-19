---
title: fp_contract | Microsoft Docs
ms.custom: ''
ms.date: 03/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 514b4708129d625ea7880e4c61be22c4b1ac2db5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912894"
---
# <a name="fpcontract"></a>fp_contract

Kayan nokta daraltmaya gerçekleşir olup olmadığını belirler. Kayan nokta daraltmaya iki ayrı kayan nokta işlemleri tek bir yönerge içine birleştiren FMA (Fused-Çarp-ekleyin) gibi bir yönerge ' dir. Her işlemden sonra yuvarlama yerine işlemci yalnızca bir kez hem işlemlerinden sonra yuvarlamak çünkü bu yönergeleri kullanımını kayan nokta duyarlık etkileyebilir.

## <a name="syntax"></a>Sözdizimi

> **#pragma fp_contract (** { **üzerinde** | **kapalı** } **)**  

## <a name="remarks"></a>Açıklamalar  

Varsayılan olarak, **fp_contract** olan **üzerinde**. Derleyicinin mümkün olduğunda kayan nokta daraltmaya yönergeleri kullanmasını söyler. Ayarlama **fp_contract** için **kapalı** tek tek kayan nokta yönergeleri korumak için.

Kayan nokta davranışını hakkında daha fazla bilgi için bkz: [/fp (Floating-Point davranış belirtin)](../build/reference/fp-specify-floating-point-behavior.md).

Diğer kayan nokta pragmaları şunlardır:

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>Örnek

Hedef işlemci kullanılabilir olduğunda bile bu örnekten oluşturulan kodu Sigortalı Çarp-ekleme yönerge kullanmaz. Çıkarırsanız `#pragma fp_contract (off)`, kullanılabilir durumdaysa oluşturulan kod Sigortalı Çarp-ekleme yönerge kullanabilir.  
  
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
