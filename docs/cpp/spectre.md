---
title: spectre | Microsoft Docs
ms.custom: 
ms.date: 1/23/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b515d25d4818cf8b6213a37f3fe78df4f3882a69
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="spectre"></a>spectre

**Microsoft Specific**

Spectre değişken 1 kurgusal yürütme engel yönergeler için bir işlev değil derleyicinin eklemesini söyler.

## <a name="syntax"></a>Sözdizimi

> **__declspec (spectre(nomitigation))**  

## <a name="remarks"></a>Açıklamalar

[/Qspectre](../build/reference/qspectre.md) derleyici seçeneği kurgusal yürütme engel yönergeleri burada analiz gösterir Spectre değişken 1 güvenlik açığı var olduğunu eklemek derleyicinin neden olur. Gösterilen özel yönergeler işlemci bağlıdır. Bu yönergeleri kod boyutu veya performans üzerinde en az bir etkiye sahip olsa da, burada kodunuzu güvenlik açığından etkilenmez ve en yüksek performans gerektiren durumlar olabilir.

Uzman analiz işlevi bir Spectre değişken 1 sınırları onay atlama hatası güvenli olduğunu belirleyebilirsiniz. Bu durumda, uygulayarak azaltma kodu bir işlev içinde nesil gözardı edebileceğini `__declspec(spectre(nomitigation))` işlev bildirimi için.

> [!CAUTION]
> **/Qspectre** kurgusal yürütme engel yönergeleri önemli güvenlik korumasını sağlar ve performans üzerinde düşünülerek etkileyen sahip. Bu nedenle, işlev performansının kritik bir önem arz ettiği ve işlevin güvenli olduğunun bilindiği nadir durumlar haricinde bunları engellememenizi öneririz.

## <a name="example"></a>Örnek

Aşağıdaki kodu nasıl kullanılacağını gösterir `__declspec(spectre(nomitigation))`.

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

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)  
[Anahtar Sözcükler](../cpp/keywords-cpp.md)  
[/Qspectre](../build/reference/qspectre.md)  
