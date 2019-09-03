---
title: float_control pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: aa8cdc07953405175c1753791ab53214d73ba516
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218573"
---
# <a name="float_control-pragma"></a>float_control pragması

Bir işlev için kayan nokta davranışını belirtir.

## <a name="syntax"></a>Sözdizimi

> **#pragma float_control**\
> **#pragma float_control (** { **kesin** | **kesin** | **hariç** } **,** { **on** | **off** } [ **, push** ] **)** \
> **#pragma float_control (** { **Push** | **pop** } **)**

## <a name="options"></a>Seçenekler

**kesin**katı, kapalıveGönderdışında |  |  | \
**Kesin**, **katı**veya **hariç**olabilen kayan nokta davranışını belirtir. Daha fazla bilgi için bkz. [/FP (kayan nokta davranışını belirt)](../build/reference/fp-specify-floating-point-behavior.md). Ayar **Açık** ya da **kapalı**olabilir.

**Katı**olduğunda hem **kesin** hem de **hariç** ayarları, **Açık** veya **kapalı** ayarıyla belirtilir. **except** , yalnızca **kesin** veya **kesin** olduğunda **Açık** olarak ayarlanabilir.

İsteğe bağlı **gönderim** belirteci eklenirse, **float_control** için geçerli ayar iç derleyici yığınına gönderilir.

**hareketle**\
Geçerli **float_control** ayarını iç derleyici yığınına gönder

**cağımız**\
**Float_control** ayarını iç derleyici yığınının üst öğesinden kaldırır ve yeni **float_control** ayarını yapar.

## <a name="remarks"></a>Açıklamalar

**Float_control** **hariç** olmak üzere **kesin** kapatma özelliğini kullanamazsınız. Benzer şekilde, [fenv_access](../preprocessor/fenv-access.md) açık olduğunda **kesin** bir şekilde kapatılamaz. **Float_control** pragmasını kullanarak katı modelden hızlı bir modele gitmek için aşağıdaki kodu kullanın:

```cpp
#pragma float_control(except, off)
#pragma fenv_access(off)
#pragma float_control(precise, off)
```

Hızlı modelden **float_control** pragma ile katı bir modele gitmek için aşağıdaki kodu kullanın:

```cpp
#pragma float_control(precise, on)
#pragma fenv_access(on)
#pragma float_control(except, on)
```

Hiçbir seçenek belirtilmemişse, **float_control** etkisizdir.

Diğer kayan nokta pragmaları şunlardır:

- [fenv_access](../preprocessor/fenv-access.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, pragma **float_control**kullanarak taşan kayan nokta özel durumunun nasıl yakalanarak gösterir.

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

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
