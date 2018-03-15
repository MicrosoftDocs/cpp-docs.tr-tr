---
title: fenv_access | Microsoft Docs
ms.custom: 
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e19b4b3f1fd71d61609648f587dee9aac31e6f6
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="fenvaccess"></a>fenv_access

Devre dışı bırakır (**üzerinde**) veya sağlar (**kapalı*) kayan nokta ortamı değişebilir iyileştirmeler bayrak testleri ve mod değişiklikleri.

## <a name="syntax"></a>Sözdizimi

> **#pragma fenv_access (** { **üzerinde** | **kapalı** } **)**  

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **fenv_access** olan **devre dışı**. Derleyici varsayımında kodunuzu erişemedi veya kayan nokta ortamı işlemek, sonra birçok kayan nokta kodu en iyi duruma getirme işlemi gerçekleştirebilirsiniz. Ayarlama **fenv_access** için **üzerinde** kodunuzu durumu bayrakları, özel durumlar, test veya Denetim modu bayrakları ayarlamak için kayan nokta ortamı erişen derleyici bilgilendirmek için. Kodunuzu kayan nokta ortamı tutarlı bir şekilde erişebilmesi için bu iyileştirmeler derleyici devre dışı bırakır. 

Kayan nokta davranışını hakkında daha fazla bilgi için bkz: [/fp (Floating-Point davranış belirtin)](../build/reference/fp-specify-floating-point-behavior.md).

Tabi olan en iyi duruma getirme türlerini **fenv_access** şunlardır:

- Genel Genel alt ifade ortadan kaldırma

- Kod hareket

- Sabit Katlama

Diğer kayan nokta pragmaları şunlardır:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Örnekler

Bu örnek ayarlar **fenv_access** için **üzerinde** 24 bit duyarlık kayan nokta denetim kaydolun ayarlamak için:

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

Çıkarırsanız `#pragma fenv_access (on)` önceki örnekten derleyici denetim modunu kullanmaz derleme zamanı değerlendirme yaptığından çıkış farklı olduğuna dikkat edin.

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
