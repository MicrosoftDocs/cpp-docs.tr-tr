---
title: /Og (Global İyileştirmeler)
description: Önceden genel iyileştirmeleri etkinleştirmek için kullanılan/OG kullanım dışı MSVC derleyici seçeneğini tanımlar.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.GlobalOptimizations
- /og
helpviewer_keywords:
- -Og compiler option [C++]
- global optimizations compiler option [C++]
- automatic register allocation
- /Og compiler option [C++]
- loop structures, optimizing
- common subexpression elimination
- Og compiler option [C++]
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
ms.openlocfilehash: c1cab53ccb391bd7d6ca7660e2750f53aa7c72e4
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180857"
---
# <a name="og-global-optimizations"></a>`/Og`(Global Iyileştirmeler)

Kullanım dışı. Yerel ve genel iyileştirmeler, otomatik kayıt ayırma ve döngü iyileştirmesi sağlar. Bunun yerine [ `/O1` (boyutu en aza indir)](o1-o2-minimize-size-maximize-speed.md) ya da [ `/O2` (hızı en üst düzeye çıkarın)](o1-o2-minimize-size-maximize-speed.md) kullanmanızı öneririz.

## <a name="syntax"></a>Sözdizimi

> **`/Og`**

## <a name="remarks"></a>Açıklamalar

**`/Og`** kullanım dışıdır. Bu iyileştirmeler, artık herhangi bir iyileştirme etkinleştirildiğinde varsayılan olarak etkindir. İyileştirmeler hakkında daha fazla bilgi için bkz. [ `/O1` , `/O2` (boyutu en aza indir, hızı Büyüt)](o1-o2-minimize-size-maximize-speed.md)veya [ `/Ox` (çoğu hız iyileştirmelerini etkinleştir)](ox-full-optimization.md).

Aşağıdaki iyileştirmeler aşağıda verilmiştir **`/Og`** :

- Yerel ve genel sık kullanılan alt ifade eleme

   Bu iyileştirmede, ortak bir alt ifadenin değeri bir kez hesaplanır. Aşağıdaki örnekte, değerleri, `b` ve `c` üç ifade arasında değişmezseniz, derleyici hesaplamasını `b + c` geçici bir değişkene atayabilir ve bu değişkeni için kullanabilirsiniz `b + c` :

    ```C
    a = b + c;
    d = b + c;
    e = b + c;
    ```

   Yerel ortak alt ifade iyileştirmesi için, derleyici ortak alt ifadeler için kodun kısa kısımlarını inceler. Genel sık kullanılan alt ifade iyileştirmesi için, derleyici tüm işlevleri ortak alt ifadeler için arar.

- Otomatik kayıt ayırma

   Bu iyileştirme, derleyicinin kayıtlarda sık kullanılan değişkenleri ve alt ifadeleri depolamasına olanak sağlar; `register`anahtar sözcüğü yoksayıldı.

- Döngü iyileştirmesi

   Bu iyileştirme, bir döngü gövdesinin sabit alt ifadelerini kaldırır. En iyi döngü, yalnızca değerleri döngünün her yürütülmesinde değişen ifadeleri içerir. Aşağıdaki örnekte, ifadesi `x + y` döngü gövdesinde değişmez:

    ```C
    i = -100;
    while( i < 0 ) {
        i += x + y;
    }
    ```

   İyileştirmeden sonra, `x + y` döngü her yürütüldüğünde değil bir kez hesaplanır:

    ```C
    i = -100;
    t = x + y;
    while( i < 0 ) {
        i += t;
    }
    ```

   Derleyici bir diğer ad belirtmede, veya ile ayarladığınız zaman döngü iyileştirmesi çok daha etkilidir [`__restrict`](../../cpp/extension-restrict.md) [`noalias`](../../cpp/noalias.md) [`restrict`](../../cpp/restrict.md) .

   > [!NOTE]
   > Seçeneğini seçeneğiyle birlikte kullanarak bir işlev işlevi temelinde, genel iyileştirmeyi etkinleştirebilir veya devre dışı bırakabilirsiniz `optimize` `g` .

İlgili bilgiler için bkz. [ `/Oi` (iç işlevler oluşturma)](oi-generate-intrinsic-functions.md) ve [ `/Ox ` (çoğu hız iyileştirmelerini etkinleştir)](ox-full-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusunda derleyici seçeneğini girin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
