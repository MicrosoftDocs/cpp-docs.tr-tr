---
title: spectre
ms.date: 01/23/2018
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
ms.openlocfilehash: 40eee25dec867ae3fce7a6b2d4715f0be81bfe76
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926361"
---
# <a name="spectre"></a>spectre

**Microsoft 'a özgü**

Derleyiciye bir işlev için Spectre VARIANT 1 kurgusal yürütme engeli ekleme yönergeleri eklememe konusunda bilgi söyler.

## <a name="syntax"></a>Sözdizimi

> **__declspec (Spectre (noazaltma))**

## <a name="remarks"></a>Açıklamalar

[/Qspectre](../build/reference/qspectre.md) derleyici seçeneği derleyicinin kurgusal yürütme engeli ekleme yönergeleri eklemesine neden olur. Bunlar, çözümlemenin bir Spectre varyant 1 güvenlik açığının bulunduğunu gösterdiği yerde eklenirler. Oluşturulan belirli yönergeler, işlemciye göre değişir. Bu yönergelerin kod boyutu veya performans üzerinde en az etkisi olması gerekir, ancak kodunuzun güvenlik açığından etkilenmemesi ve en yüksek performans gerektiren durumlar olabilir.

Uzman Analizi bir işlevin Spectre VARIANT 1 sınırları tarafından güvenli olduğunu belirleyebilir ve atlama hatasını kontrol edebilir. Bu durumda, işlev bildirimine uygulayarak `__declspec(spectre(nomitigation))` bir işlev içinde azaltma kodu oluşturmayı gizleyebilirsiniz.

> [!CAUTION]
> **/Qspectre** speculatıcı yürütme engeli, önemli güvenlik koruması sağlar ve performans üzerinde göz ardı edilebilir bir etkileri vardır. Bu nedenle, işlev performansının kritik bir önem arz ettiği ve işlevin güvenli olduğunun bilindiği nadir durumlar haricinde bunları engellememenizi öneririz.

## <a name="example"></a>Örnek

Aşağıdaki kod, nasıl `__declspec(spectre(nomitigation))`kullanılacağını göstermektedir.

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[/Qspectre](../build/reference/qspectre.md)
