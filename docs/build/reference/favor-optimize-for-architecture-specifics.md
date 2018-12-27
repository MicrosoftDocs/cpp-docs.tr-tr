---
title: /favor (Mimari Özellikleri için İyileştirme)
ms.date: 11/04/2016
f1_keywords:
- /favor
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
ms.openlocfilehash: 63affcced5dfc5bb56b0226021e1c32d93ec5d4f
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53626753"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (Mimari Özellikleri için İyileştirme)

**/ favor:** `option` belirli bir mimari için ya da AMD ve Intel mimarileri mikro mimariler için iyileştirilmiş kod üretir.

## <a name="syntax"></a>Sözdizimi

> **/ favor:**{**blend** | **ATOM** | **AMD64** | **ıntel64**}

## <a name="remarks"></a>Açıklamalar

**/favor:Blend**<br/>
(x86 ve x64) özellikleri mikro mimariler AMD ve Intel mimarileri için iyileştirilmiş kod üretir. Sırada **/favor:blend** en iyi performans verebilir, çok çeşitli x86 ve x64 işlemciler arasında en iyi performans sunmak üzere tasarlanmıştır belirli bir işlemci üzerinde mümkün. Varsayılan olarak, **/favor:blend** etkindir.

**/favor:Atom**<br/>
(x86 ve x64) Intel Centrino Atom işlemci teknolojisi ve Intel Atom işlemci özellikleri için en iyi duruma getirilmiş kodu üretir. Kullanılarak oluşturulan kodu **/favor:ATOM** Intel işlemcileri için Intel SSSE3, SSE3, SSE2 ve SSE yönergeleri oluşturulmasına neden olabilir.

**/favor:AMD64**<br/>
(yalnızca x64) AMD Opteron ve 64-bit uzantıları destekleyen Athlon işlemcileri için oluşturulan kodu en iyi duruma getirir. En iyi duruma getirilmiş kod, uyumlu bir platform tüm x64 çalıştırabilirsiniz. Kullanılarak oluşturulan kodu **/favor:AMD64** daha zayıf performans ıntel64 destekleyen Intel işlemci üzerinde neden olabilir.

**/favor:INTEL64**<br/>
(yalnızca x64) desteği genellikle, platform için daha iyi performans verir ıntel64, Intel işlemcileri için oluşturulan kodu en iyi duruma getirir. Sonuçta elde edilen kod üzerinde herhangi bir x64 çalıştırabilirsiniz platform. İle oluşturulan kodu **/favor:INTEL64** daha zayıf performans AMD Opteron ve 64-bit uzantıları destekleyen Athlon işlemciler üzerinde neden olabilir.

> [!NOTE]
> Intel64 mimarisi daha önce Extended Memory 64 Technology biliniyordu ve karşılık gelen derleyici seçeneği olan **/favor:EM64T**.

X64 programı hakkında bilgi için Mimari bkz [x64 yazılım kuralları](../../build/x64-software-conventions.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **C/C++** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. Derleyici seçeneğini girin **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)