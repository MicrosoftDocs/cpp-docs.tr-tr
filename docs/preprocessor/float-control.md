---
title: float_control pragma
description: Float_control yönergesinin kullanımını ve etkilerini açıklar pragma . Float_control yönergesi, çalışma zamanında kayan nokta kesin semantiğinin ve özel durum semantiğinin durumunu denetler.
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragma, float_control
no-loc:
- pragma
ms.openlocfilehash: 98695c15424395a9b4e008a5cb1133824e1e7054
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712771"
---
# <a name="float_control-no-locpragma"></a>`float_control` pragma

Bir işlev için kayan nokta davranışını belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma float_control`**\
> **`#pragma float_control( precise,`** { **`on`** | **`off`** } [ **`, push`** ] **`)`**\
> **`#pragma float_control( except,`** { **`on`** | **`off`** } [ **`, push`** ] **`)`**\
> **`#pragma float_control(`** { **`push`** | **`pop`** } **`)`**

## <a name="options"></a>Seçenekler

**`precise`**, **`on`** | **`off`**, **`push`**\
**`on`** Kesin kayan nokta semantiğinin etkinleştirilip etkinleştirilmeyeceğini () veya devre dışı bırakmayı ( **`off`** ) belirtir. Derleyici seçeneğiyle ilgili farklılıklar hakkında daha fazla bilgi için **`/fp:precise`** , açıklamalar bölümüne bakın. İsteğe bağlı **`push`** belirteç, iç derleyici yığınında için geçerli ayarı gönderir **`float_control`** .

**`except`**, **`on`** | **`off`**, **`push`**\
**`on`** **`off`** Kayan nokta özel durum semantiğinin etkinleştirilip etkinleştirilmeyeceğini () veya devre dışı bırakılacağını belirtir. İsteğe bağlı **`push`** belirteç, iç derleyici yığınında için geçerli ayarı gönderir **`float_control`** .

**`except`** yalnızca, olarak ayarlandığında olarak **`on`** ayarlanabilir **`precise`** **`on`** .

**`push`**\
Geçerli **`float_control`** ayarı iç derleyici yığınına iter.

**`pop`**\
Ayarı, **`float_control`** iç derleyici yığınının en üstünden kaldırır ve yeni **`float_control`** ayarı yapar.

## <a name="remarks"></a>Açıklamalar

, **`float_control`** pragma Derleyici seçeneğiyle aynı davranışa sahip değildir [`/fp`](../build/reference/fp-specify-floating-point-behavior.md) . **`float_control`** pragma Yalnızca kayan nokta davranışının bir parçasını yönetir. [`fp_contract`](../preprocessor/fp-contract.md) [`fenv_access`](../preprocessor/fenv-access.md) pragma Derleyici seçeneklerini yeniden oluşturmak için ve yönergeleri ile birleştirilmelidir **`/fp`** . Aşağıdaki tabloda pragma her bir derleyici seçeneğinin eşdeğer ayarları gösterilmektedir:

| Seçenek | `float_control(precise, *)` | `float_control(except, *)` | `fp_contract(*)` | `fenv_access(*)` |
|-|-|-|-|-|
| `/fp:strict`             | `on`  | `on`  | `off` | `on`  |
| `/fp:precise`            | `on`  | `off` | `on`  | `off` |
| `/fp:fast`               | `off` | `off` | `on`  | `off` |

Diğer bir deyişle,, pragma **`/fp:fast`** **`/fp:precise`** ve **`/fp:strict`** komut satırı seçeneklerine benzemek için birkaç yönergesi birlikte kullanmanız gerekebilir.

**`float_control`** Ve **`fenv_access`** kayan nokta yönergelerini birlikte kullanabileceğiniz yollarla ilgili kısıtlamalar vardır pragma :

- ' İ yalnızca **`float_control`** **`except`** **`on`** kesin semantikler etkinse öğesini kullanabilirsiniz. Kesin anlambilim, ya da **`float_control`** pragma **`/fp:precise`** veya **`/fp:strict`** derleyici seçenekleri kullanılarak etkinleştirilebilir.

- **`float_control`** **`precise`** Bir **`float_control`** pragma veya derleyici seçeneği tarafından özel durum semantiği etkinleştirildiğinde devre dışı bırakmak için kullanamazsınız **`/fp:except`** .

- Ya da bir **`fenv_access`** derleyici seçeneği tarafından kesin anlambilim etkinleştirilmediği takdirde etkinleştiremezsiniz **`float_control`** pragma .

- **`float_control`** **`precise`** Etkinleştirildiğinde devre dışı bırakmak için kullanamazsınız **`fenv_access`** .

Bu kısıtlamalar, bazı kayan nokta pragma yönergelerinin sırası önemli olduğu anlamına gelir. Yönergeleri kullanarak hızlı bir modelden katı bir modele gitmek için pragma aşağıdaki kodu kullanın:

```cpp
#pragma float_control(precise, on)  // enable precise semantics
#pragma fenv_access(on)             // enable environment sensitivity
#pragma float_control(except, on)   // enable exception semantics
#pragma fp_contract(off)            // disable contractions
```

Kullanarak katı bir modelden hızlı bir modele gitmek için **`float_control`** pragma aşağıdaki kodu kullanın:

```cpp
#pragma float_control(except, off)  // disable exception semantics
#pragma fenv_access(off)            // disable environment sensitivity
#pragma float_control(precise, off) // disable precise semantics
#pragma fp_contract(on)             // enable contractions
```

Hiçbir seçenek belirtilmemişse, hiçbir **`float_control`** etkisi olmaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek kullanılarak taşma noktası özel durumunun nasıl yakalanarak gösterilmektedir pragma **`float_control`** .

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

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)\
[`fenv_access` pragma](../preprocessor/fenv-access.md)\
[`fp_contract` pragma](../preprocessor/fp-contract.md)
