---
title: spectre
ms.date: 1/23/2018
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
ms.openlocfilehash: 2377a3c23be1e27bfe4f2df23eb00823635fa05d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592016"
---
# <a name="spectre"></a>spectre

**Microsoft'a özgü**

Spectre değişkeni 1 kurgusal yürütmeyi barrier yönergelerini bir işlev için değil derleyiciye bildirir.

## <a name="syntax"></a>Sözdizimi

> **__declspec (spectre(nomitigation))**

## <a name="remarks"></a>Açıklamalar

[/Qspectre](../build/reference/qspectre.md) derleyici seçeneği, derleyiciye analiz burada gösterir Spectre değişkeni 1 güvenlik açığı var olduğundan kurgusal yürütmeyi barrier yönergelerini neden olur. Yayılan özel yönergeler işlemci üzerinde bağlıdır. Bu yönergeleri kod boyutu veya performans üzerinde en az bir etkiye sahip olmalıdır ancak burada kodunuzu açığından etkilenmez ve en yüksek performans gerektiren durumlar olabilir.

Uzman analiz, bir işlev bir Spectre değişkeni 1 sınırları onay atlama hatası güvenli olduğuna karar. Bu durumda, uygulayarak bir işlev içinde azaltma kod oluşturulmasını gözardı edebileceğini `__declspec(spectre(nomitigation))` işlev bildirimi için.

> [!CAUTION]
> **/Qspectre** kurgusal yürütmeyi barrier yönergelerini önemli bir güvenlik koruması sağlar ve ardı edilebilir bir performans sahip. Bu nedenle, işlev performansının kritik bir önem arz ettiği ve işlevin güvenli olduğunun bilindiği nadir durumlar haricinde bunları engellememenizi öneririz.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanılacağını gösterir `__declspec(spectre(nomitigation))`.

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[/Qspectre](../build/reference/qspectre.md)
