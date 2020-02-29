---
title: float_control pragması
description: Float_control pragma yönergesinin kullanımını ve etkilerini açıklar. Float_control yönergesi, çalışma zamanında kayan nokta kesin semantiğinin ve özel durum semantiğinin durumunu denetler.
ms.date: 11/18/2019
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: 5f907bfeb3f92f788fe951854ddc32accc83ae03
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78166790"
---
# <a name="float_control-pragma"></a>float_control pragması

Bir işlev için kayan nokta davranışını belirtir.

## <a name="syntax"></a>Sözdizimi

> **#pragma float_control**\
> **#pragma float_control (kesin,** { **on** | **kapalı** } [ **, push** ] **)** \
> **#pragma float_control (hariç,** { **on** | **off** } [ **, push** ] **)** \
> **#pragma float_control (** { **Push** | **pop** } **)**

## <a name="options"></a>Seçenekler

**kesin**, ** | ** **kapalı**, **Gönder**\
Kesin kayan nokta semantiğinin etkinleştirilip etkinleştirilmeyeceğini (**Açık**) veya devre dışı bırakmayı (**kapalı**) belirtir. **/FP: kesin** derleyici seçeneğiyle ilgili farklılıklar hakkında daha fazla bilgi Için, açıklamalar bölümüne bakın. İsteğe bağlı **gönderme** belirteci, iç derleyici yığınında **float_control** için geçerli ayarı gönderir.

**dışında**, ** | ** **off**,\ **Gönder**
Kayan nokta özel durum semantiğini etkinleştirip etkinleştirmeyeceğinizi (**Açık**) veya devre dışı bırakmayı (**kapalı**) belirtir. İsteğe bağlı **gönderme** belirteci, iç derleyici yığınında **float_control** için geçerli ayarı gönderir.

**except** yalnızca, **kesin** olarak **Açık**olarak ayarlandığı zaman **Açık** olarak ayarlanabilir.

**gönderim**\
Geçerli **float_control** ayarını iç derleyici yığınına iter.

**pop**\
**Float_control** ayarını iç derleyici yığınının üst öğesinden kaldırır ve yeni **float_control** ayarını yapar.

## <a name="remarks"></a>Açıklamalar

**Float_control** pragma, [/FP](../build/reference/fp-specify-floating-point-behavior.md) derleyici seçeneği ile aynı davranışa sahip değil. **Float_control** pragma yalnızca kayan nokta davranışının bir parçasını yönetir. **/FP** derleyici seçeneklerini yeniden oluşturmak için [fp_contract](../preprocessor/fp-contract.md) ve pragmalar [fenv_access](../preprocessor/fenv-access.md) ile birleştirilmelidir. Aşağıdaki tabloda her derleyici seçeneği için eşdeğer pragma ayarları gösterilmektedir:

| | float_control (kesin, \*) | float_control (\*hariç) | fp_contract (\*) | fenv_access (\*) |
|-|-|-|-|-|
| /FP: Strict             | on  | on  | kapalı | on  |
| /FP: kesin            | on  | kapalı | on  | kapalı |
| /FP: Fast               | kapalı | kapalı | on  | kapalı |

Diğer bir deyişle, **/FP: Fast**, **/FP: kesinlikli**ve **/FP: Strict** komut satırı seçeneklerine benzemek için çeşitli pragmalar kullanmanız gerekebilir.

**Float_control** ve kayan nokta pragmalarını **fenv_access** birlikte kullanma gibi kısıtlamalar vardır:

- Kesin semantikler etkinse, yalnızca **Açık** **olarak ayarlamak için** **float_control** kullanabilirsiniz. Kesin anlambilim **float_control** pragma tarafından ya da **/FP: kesin** veya **/FP: Strict** derleyici seçenekleri kullanılarak etkinleştirilebilir.

- Özel durum semantiği etkin olduğunda float_control, bir **float_control** pragma veya **/FP: except** derleyici seçeneği tarafından açık **olarak devre dışı bırakmak için** kullanamazsınız.

- Kesin semantik bir **float_control** pragma veya bir derleyici seçeneği tarafından etkinleştirilmediği takdirde **fenv_access** etkinleştiremezsiniz.

- **Fenv_access** etkinleştirildiğinde **kesin** devre dışı bırakmak için **float_control** kullanamazsınız.

Bu kısıtlamalar, bazı kayan nokta pragmaların sırasının önemli olduğu anlamına gelir. Pragmaları kullanarak hızlı bir modelden katı bir modele gitmek için aşağıdaki kodu kullanın:

```cpp
#pragma float_control(precise, on)  // enable precise semantics
#pragma fenv_access(on)             // enable environment sensitivity
#pragma float_control(except, on)   // enable exception semantics
#pragma fp_contract(off)            // disable contractions
```

**Float_control** pragma kullanarak katı bir modelden hızlı bir modele gitmek için aşağıdaki kodu kullanın:

```cpp
#pragma float_control(except, off)  // disable exception semantics
#pragma fenv_access(off)            // disable environment sensitivity
#pragma float_control(precise, off) // disable precise semantics
#pragma fp_contract(on)             // enable contractions
```

Hiçbir seçenek belirtilmediyse **float_control** hiçbir etkisi olmaz.

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

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[fenv_access](../preprocessor/fenv-access.md)\
[fp_contract](../preprocessor/fp-contract.md)
