---
title: /Wp64 (64 Bit Taşınabilirlik Sorunlarını Algıla)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
ms.openlocfilehash: 5a3cdaf85fa4dc05ece54fc630cb69fc93650e6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316554"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (64 Bit Taşınabilirlik Sorunlarını Algıla)

Bu derleyici seçeneğini kullanımdan kalkmıştır. Visual Studio 2013 önce Visual Studio sürümlerinde, 64-bit taşınabilirlik sorunlarını ile işaretlenmiş türlerinde bunu algılar [__w64](../../cpp/w64.md) anahtar sözcüğü.

## <a name="syntax"></a>Sözdizimi

```
/Wp64
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, önce Visual Studio 2013, Visual Studio sürümlerinde **/Wp64** derleyici seçeneği 32-bit x86 oluşturan MSVC derleyici kapalıdır kod üzerinde MSVC derleyicisi, 64-bit, x64 yapılara ve kod.

> [!IMPORTANT]
>  [/Wp64](wp64-detect-64-bit-portability-issues.md) derleyici seçeneği ve [__w64](../../cpp/w64.md) anahtar sözcüğü, Visual Studio 2010 ve Visual Studio 2012'de kullanım dışı ve Visual Studio 2013 itibariyle desteklenmiyor. Bu anahtar kullanan bir proje dönüştürürseniz, anahtar dönüştürme sırasında geçirilmez. Visual Studio 2010 veya Visual Studio 2012'de bu seçeneği kullanmak için derleyici anahtarı altındaki yazın **ek seçenekler** içinde **komut satırı** Proje Özellikleri bölümünde. Kullanırsanız **/Wp64** derleyici seçeneği komut satırında derleyici komut satırı uyarısı D9002 verir. Bu seçenek ve anahtar sözcüğü 64-bit taşınabilirlik sorunlarını algılamak için kullanmak yerine 64-bit platformu hedefleyen bir MSVC derleyici kullanın ve belirtin [/W4](compiler-option-warning-level.md) seçeneği. Daha fazla bilgi için [yapılandırma C++ projeleri 64-bit için x64 hedefleri](../configuring-programs-for-64-bit-visual-cpp.md).

Bunlar bir 64-bit işletim sisteminde olarak kullanılıyorsa şu türlerinin değişkenleri bir 32-bit işletim sisteminde test edilmez:

- int

- long

- pointer

Düzenli olarak 64-bit, x64 oluşturan bir derleyici kullanarak uygulamanızı derlemek, kod, yalnızca devre dışı bırakabilirsiniz **/Wp64** , 32-bit derlemelerde çünkü 64 bit derleyici tüm sorunları algılar. Hedef bir Windows 64-bit işletim sistemi hakkında daha fazla bilgi için bkz. [yapılandırma C++ projeleri 64-bit için x64 hedefleri](../configuring-programs-for-64-bit-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu.

   Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** kutusuna **/Wp64**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[C++ projeleri için 64 bit x64 yapılandırma hedefleri](../configuring-programs-for-64-bit-visual-cpp.md)
