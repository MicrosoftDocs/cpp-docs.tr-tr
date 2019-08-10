---
title: /Ob (Satır İçi İşlev Genişletmesi)
ms.date: 08/08/2019
f1_keywords:
- VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion
- VC.Project.VCCLCompilerTool.InlineFunctionExpansion
- /ob
helpviewer_keywords:
- inline functions, function expansion compiler option [C++]
- -Ob1 compiler option [C++]
- -Ob0 compiler option [C++]
- /Ob0 compiler option [C++]
- /Ob1 compiler option [C++]
- any suitable compiler option [C++]
- Ob2 compiler option [C++]
- Ob1 compiler option [C++]
- /Ob2 compiler option [C++]
- Ob compiler option [C++]
- -Ob2 compiler option [C++]
- disable compiler option [C++]
- -Ob compiler option [C++]
- /Ob compiler option [C++]
- only __inline compiler option [C++]
- Ob0 compiler option [C++]
- inline expansion, compiler option
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
ms.openlocfilehash: 7eb3db1e359349eaf5125a6c8a46a3ac7d847f2f
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915478"
---
# <a name="ob-inline-function-expansion"></a>/Ob (Satır İçi İşlev Genişletmesi)

İşlevlerin satır içi genişletmesini denetler. Varsayılan olarak, iyileştirildiğinde, genişletme derleyicinin tüm işlevlerde (genellikle *Otomatik*olarak ifade edilir) meydana gelir.

## <a name="syntax"></a>Sözdizimi

::: moniker range=">=vs-2019"

> **/Ob** {**0**|12|**3**}|

::: moniker-end

::: moniker range="<=vs-2017"

> **/Ob** {**0**|12|}

::: moniker-end

## <a name="arguments"></a>Arguments

**0**\
[/Od](od-disable-debug.md)altındaki varsayılan değer. Satır içi genişleimleri devre dışı bırakır.

**1**\
Yalnızca [satır içi](../../cpp/inline-functions-cpp.md), [__inline](../../cpp/inline-functions-cpp.md)veya [__forceinline](../../cpp/inline-functions-cpp.md)olarak işaretlenen işlevlerin genişlemesine veya sınıf bildiriminde tanımlanan C++ bir üye işleve izin verir.

**iki**\
[/O1](o1-o2-minimize-size-maximize-speed.md) ve [/O2](o1-o2-minimize-size-maximize-speed.md)altındaki varsayılan değer. Derleyicinin hiçbir satır için açıkça işaretlenmemiş herhangi bir işlevi genişletmesine izin verir.

::: moniker range=">=vs-2019"

**03**\
Bu seçenek **/Ob2**' den daha agresif bir giriş belirtir, ancak aynı kısıtlamalara sahiptir. **/Ob3** seçeneği, Visual Studio 2019 ' den itibaren kullanılabilir.

::: moniker-end

## <a name="remarks"></a>Açıklamalar

Derleyici, satır içi genişleme seçeneklerine ve anahtar sözcüklerine öneri olarak davranır. Herhangi bir işlevin satır içi olarak genişletilmeyeceği garantisi yoktur. Satır içi genişleimleri devre dışı bırakabilirsiniz ancak, `__forceinline` anahtar sözcüğü kullanılırken bile derleyiciyi belirli bir işlevi satır içi olarak zorlayamaz.

İşlevlerin satır içi genişletme için aday olarak dikkate alınması dışında, [__declspec (noinline)](../../cpp/noinline.md)veya [#pragma auto_inline (off)](../../preprocessor/auto-inline.md) ve [#pragma auto_inline (on)](../../preprocessor/auto-inline.md) yönergeleriyle işaretlenmiş bir bölgeyi kullanabilirsiniz. Derleyiciye iç ipuçları sağlamanın başka bir yolu hakkında daha fazla bilgi için, [#pragma iç](../../preprocessor/intrinsic.md) yönergesine bakın.

> [!NOTE]
> Profil oluşturma testi çalıştırmalarından toplanan bilgiler, **/ob**, **/OS**veya **/ot**belirttiğiniz için, aksi takdirde geçerli olacak iyileştirmeleri geçersiz kılar. Daha fazla bilgi için bkz. [Profil temelli iyileştirmeler](../profile-guided-optimizations.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++** optimizasyon > özellik sayfasını seçin.

1. **Satır Içi Işlev genişletme** özelliğini değiştirin.

::: moniker range=">=vs-2019"

**/Ob3** seçeneği, **satır içi işlev genişletme** özelliğinde kullanılamaz. **/Ob3**ayarlamak için:

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /** komut> **satırı** Özellik sayfası ' nı seçin.

1. **Ek seçeneklere** **/OB3** girin.

::: moniker-end

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O seçenekler (kodu Iyileştirme)](o-options-optimize-code.md)\
[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
