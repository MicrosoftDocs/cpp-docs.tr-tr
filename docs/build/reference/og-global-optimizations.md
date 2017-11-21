---
title: "-Og (Global iyileştirmeler) | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.GlobalOptimizations
- /og
dev_langs: C++
helpviewer_keywords:
- -Og compiler option [C++]
- global optimizations compiler option [C++]
- automatic register allocation
- /Og compiler option [C++]
- loop structures, optimizing
- common subexpression elimination
- Og compiler option [C++]
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a48d01437ad72bcc239de0465b62732efb805dd1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="og-global-optimizations"></a>/Og (Global İyileştirmeler)

Kullanım dışı. Yerel ve genel iyileştirmeler sağlar Otomatik yazmaç ayırma ve en iyi duruma getirme döngü. Ya da kullanmanızı öneririz [/O1 (boyutu en aza)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) veya [O2 (en üst düzeye hız)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) yerine.

## <a name="syntax"></a>Sözdizimi

> /Og

## <a name="remarks"></a>Açıklamalar

**/Og** kullanım dışı bırakılmıştır. Bu iyileştirmeler şimdi genellikle varsayılan olarak etkinleştirilir. En iyi duruma getirme hakkında daha fazla bilgi için bkz: [/O1, O2 (boyutu en aza indirmek, hızı en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) veya [/Ox (etkinleştirmek en hızlı iyileştirmeler)](../../build/reference/ox-full-optimization.md).

Aşağıdaki en iyi duruma getirme altında kullanılabilir **/Og**:

- Yerel ve genel Genel alt ifade ortadan kaldırma

     Bu iyileştirme, ortak bir alt değeri bir kez hesaplanır. Aşağıdaki örnekte, değerlerini `b` ve `c` arasında üç ifade değiştirmeyin, derleyici hesaplanması atayabilirsiniz `b + c` geçici bir değişken için ve değişken için yerine `b + c`:

    ```C
    a = b + c;
    d = b + c;
    e = b + c;
    ```

     Yerel ortak alt iyileştirme için derleyici kısa bölümlerini ortak alt ifadelerin kodunu inceler. Genel sık kullanılan alt iyileştirmek için tüm işlevleri için ortak alt ifadelerin derleyici arar.

- Otomatik yazmaç ayırma

     Bu en iyi duruma getirme deposu sık kullanılan değişkenleri ve alt ifadelerin derleyiciye Yazmaçları sağlar; `register` anahtar sözcüğü göz ardı edilir.

- Döngü iyileştirme

     Bu iyileştirme değişmez alt ifadelerin bir döngü gövdesinden kaldırır. En iyi bir döngü yalnızca her döngü yürütme değerleri değiştirmek ifade içeriyor. Aşağıdaki örnekte, ifade `x + y` döngü gövdesine değiştirmez:

    ```C
    i = -100;
    while( i < 0 ) {
        i += x + y;
    }
    ```

     En iyi duruma getirme sonra `x + y` döngü yürütüldüğünde kez her zaman yerine hesaplanır:

    ```C
    i = -100;
    t = x + y;
    while( i < 0 ) {
        i += t;
    }
    ```

     Döngü en iyi duruma getirme olduğunda çok daha etkili derleyici ile ayarladığınız hiçbir diğer ad oynayabilir [__restrict](../../cpp/extension-restrict.md), [noalias](../../cpp/noalias.md), veya [kısıtlamak](../../cpp/restrict.md).

    > [!NOTE]
    > Etkinleştirmek veya kullanma işlevi tarafından işlevi temel genel iyileştirme devre dışı `optimize` ile birlikte pragma `g` seçeneği.

 İlgili bilgi için bkz: [/Oi (iç işlevler Oluştur)](../../build/reference/oi-generate-intrinsic-functions.md) ve [/Ox (etkinleştirmek en hızlı iyileştirmeler)](../../build/reference/ox-full-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Tıklatın **C/C++** klasör.

1. Tıklatın **komut satırı** özellik sayfası.

1. Derleyici seçeneği girin **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)

[Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)