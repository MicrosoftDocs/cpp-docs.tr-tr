---
description: Şu konuda daha fazla bilgi edinin:/et (mimari özellikleri için Iyileştirme)
title: /favor (Mimari Özellikleri için İyileştirme)
ms.date: 11/04/2016
f1_keywords:
- /favor
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
ms.openlocfilehash: 184e81e1007214a09088601b6c579692a0dd20a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192310"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (Mimari Özellikleri için İyileştirme)

**/iyilik:** `option` AMD ve Intel mimarilerinde mikro mimarilerin özellikleri için en iyi duruma getirilmiş kodu üretir.

## <a name="syntax"></a>Syntax

> **/iyilik:**{**Blend**  |  **atom**  |    |  **Intel64**}

## <a name="remarks"></a>Açıklamalar

**/iyilik: Blend**<br/>
(x86 ve x64), AMD ve Intel mimarilerinde mikro mimarilerin özellikleri için en iyi duruma getirilmiş kodu üretir. **/Et: Blend** belirli bir işlemcide mümkün olan en iyi performansı veremeyebilir, çok sayıda x86 ve x64 işlemci genelinde en iyi performansı sağlamak üzere tasarlanmıştır. Varsayılan olarak, **/iyileştir: Blend** etkindir.

**/iyilik: ATOM**<br/>
(x86 ve x64), Intel Atom işlemcisi ve Intel Centrino Atom Işlemci teknolojisinin özellikleri için en iyi duruma getirilmiş kodu üretir. **/İyı: Atom** kullanılarak oluşturulan kod, Intel Işlemcileri IÇIN Intel SSSE3, SSE3, SSE2 ve SSE yönergeleri de üretebilir.

**/iyilik: AMD64**<br/>
(yalnızca x64), AMD Opteron ve 64 bitlik uzantıları destekleyen Athlon işlemciler için üretilen kodu iyileştirir. İyileştirilmiş kod, tüm x64 uyumlu platformlarda çalıştırılabilir. **/Et: AMD64** kullanılarak oluşturulan kod, Intel64 destekleyen Intel işlemcilerinde kötü performansa neden olabilir.

**/iyilik: ıNTEL64**<br/>
(yalnızca x64), bu platform için genellikle daha iyi performans veren Intel64 destekleyen Intel işlemcileri için üretilen kodu iyileştirir. Elde edilen kod herhangi bir x64 platformunda çalıştırılabilir. **/Et: Intel64** ile oluşturulan kod, AMD Opteron ve 64 bitlik uzantıları destekleyen Athlon işlemcilerde performansı kötüleşmesine neden olabilir.

> [!NOTE]
> Intel64 mimarisi daha önce genişletilmiş bellek 64 teknolojisi olarak bilinmişti ve karşılık gelen derleyici seçeneği/iyisti **: EM64T** idi.

X64 mimarisine yönelik programlama hakkında daha fazla bilgi için bkz. [x64 yazılım kuralları](../x64-software-conventions.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü seçin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusunda derleyici seçeneğini girin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
