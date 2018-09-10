---
title: float_control | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
dev_langs:
- C++
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 958aef828d857b0e8d4043be0e2417cd8a349512
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109779"
---
# <a name="floatcontrol"></a>float_control

Bir işlev için kayan nokta davranışını belirtir.

## <a name="syntax"></a>Sözdizimi

> **#pragma float_control** [ **(** [ *değer* **,** *ayarı* [ **, anında iletme** ]] | [ **anında iletme** | **pop** ] **)** ]

## <a name="options"></a>Seçenekler

*değer*, *ayarı* [, **anında iletme**]<br/>
Kayan nokta davranışını belirtir. *değer* olabilir **kesin**, **katı**, veya **dışında**. Daha fazla bilgi için [FP (Floating-Point davranışını belirtin)](../build/reference/fp-specify-floating-point-behavior.md). *Ayarı* olabilir **üzerinde** veya **kapalı**.

Varsa *değer* olduğu **katı**, her ikisi de ayarlarını **katı** ve **dışında** tarafından belirtilen *ayarı* . **dışında** yalnızca ayarlanabilir **üzerinde** olduğunda **kesin** veya **katı** ayrıca kümesine **üzerinde**.

İsteğe bağlı **anında iletme** belirteci eklenir, geçerli ayarını *değer* iç derleyici yığınına gönderilir.

**push**<br/>
Geçerli anında iletme **float_control** açın iç derleyici yığınındaki ayarlama

**POP**<br/>
Kaldırır **float_control** derleyici iç yığının en üstünden ayarlama ve ilgili yeni **float_control** ayarı.

## <a name="remarks"></a>Açıklamalar

Kullanamazsınız **float_control** kapatmayı **kesin** kapalı olduğunda **dışında** açıktır. Benzer şekilde, **kesin** kapalı olduğunda açılamaz [fenv_access](../preprocessor/fenv-access.md) açıktır. Kullanarak hızlı bir modele katı modelden Git **float_control** pragması, aşağıdaki kodu kullanın:

```cpp
#pragma float_control(except, off)
#pragma fenv_access(off)
#pragma float_control(precise, off)
```

Katı bir modeli hızlı modelden gitmek **float_control** pragması, aşağıdaki kodu kullanın:

```cpp
#pragma float_control(precise, on)
#pragma fenv_access(on)
#pragma float_control(except, on)
```

Hiçbir seçenek belirtilmezse, **float_control** hiçbir etkisi olmaz.

Diğer kayan nokta pragmaları şunlardır:

- [fenv_access](../preprocessor/fenv-access.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, pragması kullanılarak taşma kayan nokta özel durumu yakalamak gösterilmektedir **float_control**.

```cpp
// pragma_directive_float_control.cpp
// compile with: /EHa
#include <stdio.h>
#include <float.h>

double func( ) {
   return 1.1e75;
}

#pragma float_control (except, on)

int main( ) {
   float u[1];
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);
   if (err != 0)
      printf_s("_controlfp_s failed!\n");

   try  {
      u[0] = func();
      printf_s ("Fail");
      return(1);
   }

   catch (...)  {
      printf_s ("Pass");
      return(0);
   }
}
```

```Output
Pass
```

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
