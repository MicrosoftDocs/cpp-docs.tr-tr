---
description: 'Hakkında daha fazla bilgi edinin: Spectre'
title: spectre
ms.date: 01/23/2018
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
ms.openlocfilehash: fc1f56a59dea1eaa3596a6f7a7c0347ab822e302
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113824"
---
# <a name="spectre"></a>spectre

**Microsoft'a Özgü**

Derleyiciye bir işlev için Spectre VARIANT 1 kurgusal yürütme engeli ekleme yönergeleri eklememe konusunda bilgi söyler.

## <a name="syntax"></a>Syntax

> **__declspec (Spectre (noazaltma))**

## <a name="remarks"></a>Açıklamalar

[/Qspectre](../build/reference/qspectre.md) derleyici seçeneği derleyicinin kurgusal yürütme engeli ekleme yönergeleri eklemesine neden olur. Bunlar, çözümlemenin bir Spectre varyant 1 güvenlik açığının bulunduğunu gösterdiği yerde eklenirler. Oluşturulan belirli yönergeler, işlemciye göre değişir. Bu yönergelerin kod boyutu veya performans üzerinde en az etkisi olması gerekir, ancak kodunuzun güvenlik açığından etkilenmemesi ve en yüksek performans gerektiren durumlar olabilir.

Uzman Analizi bir işlevin Spectre VARIANT 1 sınırları tarafından güvenli olduğunu belirleyebilir ve atlama hatasını kontrol edebilir. Bu durumda, işlev bildirimine uygulayarak bir işlev içinde azaltma kodu oluşturmayı gizleyebilirsiniz `__declspec(spectre(nomitigation))` .

> [!CAUTION]
> **/Qspectre** speculatıcı yürütme engeli, önemli güvenlik koruması sağlar ve performans üzerinde göz ardı edilebilir bir etkileri vardır. Bu nedenle, işlev performansının kritik bir önem arz ettiği ve işlevin güvenli olduğunun bilindiği nadir durumlar haricinde bunları engellememenizi öneririz.

## <a name="example"></a>Örnek

Aşağıdaki kod, nasıl kullanılacağını göstermektedir `__declspec(spectre(nomitigation))` .

```cpp
// compile with: /c /Qspectre
static __declspec(spectre(nomitigation))
int noSpectreIssues() {
    // No Spectre variant 1 vulnerability here
    // ...
    return 0;
}

int main() {
    noSpectreIssues();
    return 0;
}
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[/Qspectre](../build/reference/qspectre.md)
