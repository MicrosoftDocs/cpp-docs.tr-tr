---
title: /Og (Global İyileştirmeler)
ms.date: 09/22/2017
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
ms.openlocfilehash: 5e45273b6b609f1bf78504a519c1fb98e2147f76
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818537"
---
# <a name="og-global-optimizations"></a>/Og (Global İyileştirmeler)

Kullanım dışı. Yerel ve genel iyileştirmelerini sağlayıp otomatik kaydını ayırma ve döngü en iyi duruma getirme. Ya da kullanmanızı öneririz [/O1 (boyutu en aza)](o1-o2-minimize-size-maximize-speed.md) veya [/O2 (hız en üst düzeye)](o1-o2-minimize-size-maximize-speed.md) yerine.

## <a name="syntax"></a>Sözdizimi

> /Og

## <a name="remarks"></a>Açıklamalar

**/Og** kullanım dışı bırakılmıştır. Bu iyileştirmeleri artık genel olarak varsayılan olarak etkindir. En iyi duruma getirme hakkında daha fazla bilgi için bkz. [/O1, / O2 (boyutu en aza indirmek, hızı en üst düzeye)](o1-o2-minimize-size-maximize-speed.md) veya [/Ox (etkinleştirme en hız iyileştirmelerini)](ox-full-optimization.md).

Aşağıdaki en iyi duruma getirme altında kullanılabilir **/Og**:

- Yerel ve genel Genel alt ifade ortadan kaldırma

   Bu iyileştirme, ortak bir alt ifade değerini kere hesaplanır. Aşağıdaki örnekte, değerlerini `b` ve `c` arasında üç ifadesinden değiştirmeyin, derleyici hesaplanması atayabilirsiniz `b + c` geçici bir değişkene ve değişken için yerine `b + c`:

    ```C
    a = b + c;
    d = b + c;
    e = b + c;
    ```

   Yerel Genel alt ifade iyileştirme için derleyici kısa bölümlerini ortak alt ifadeler için kodu inceler. Genel Genel alt ifade iyileştirmek için tüm işlevler için ortak bir alt ifadeler derleyici arar.

- Otomatik yazmaç ayırma

   Bu en iyi duruma getirme deposu sık kullanılan değişkenlerin ve alt ifadeler derleyicinin kayıtlara izin verir; `register` anahtar sözcüğünü sayılır.

- Döngü en iyi duruma getirme

   Bu iyileştirme, bir döngü gövdesinden sabit alt ifadeler kaldırır. En iyi bir döngü yalnızca döngünün her yürütülmesi değerleri değiştirme ifadeleri içerir. Aşağıdaki örnekte, ifade `x + y` döngü gövdesinde değiştirmez:

    ```C
    i = -100;
    while( i < 0 ) {
        i += x + y;
    }
    ```

   En iyi duruma getirme sonra `x + y` döngü yürütüldüğünde bir kez her zaman yerine hesaplanır:

    ```C
    i = -100;
    t = x + y;
    while( i < 0 ) {
        i += t;
    }
    ```

   Döngü iyileştirmesi olduğunda çok daha etkili bir derleyici ile ayarladığınız hiçbir diğer ad varsayabilirsiniz [__restrict](../../cpp/extension-restrict.md), [noalias](../../cpp/noalias.md), veya [kısıtlama](../../cpp/restrict.md).

   > [!NOTE]
   > Etkinleştirebilir veya bir işlev tarafından işlevi olarak kullanarak genel iyileştirmeyi devre dışı `optimize` pragma ile birlikte `g` seçeneği.

İlgili bilgiler için bkz. [(iç işlevler Oluştur) /Oi](oi-generate-intrinsic-functions.md) ve [/Ox (etkinleştirme en hız iyileştirmelerini)](ox-full-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini girin **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
