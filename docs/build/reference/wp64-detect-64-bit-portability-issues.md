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
ms.openlocfilehash: e5c30ac9096094948a83195f5b3990794c421685
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335881"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (64 Bit Taşınabilirlik Sorunlarını Algıla)

Bu derleyici seçeneği eskidir. Visual Studio 2013'ten önceki Visual Studio sürümlerinde, [__w64](../../cpp/w64.md) anahtar kelimeyle de işaretlenmiş türlerde 64 bit taşınabilirlik sorunları algılar.

## <a name="syntax"></a>Sözdizimi

```
/Wp64
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, Visual Studio 2013'ten önceki Visual Studio sürümlerinde **, /Wp64** derleyici seçeneği 32 bit x86 kodu oluşturan MSVC derleyicisinde ve 64 bit, x64 kodu oluşturan MSVC derleyicisinde kapalıdır.

> [!IMPORTANT]
> [/Wp64](wp64-detect-64-bit-portability-issues.md) derleyici seçeneği ve [__w64](../../cpp/w64.md) anahtar kelimesi Visual Studio 2010 ve Visual Studio 2012'de küçümsenmiş ve Visual Studio 2013'ten itibaren desteklenmez. Bu anahtarı kullanan bir projeyi dönüştürürseniz, geçiş dönüşüm sırasında geçirilmez. Visual Studio 2010 veya Visual Studio 2012'de bu seçeneği kullanmak için, proje özelliklerinin **Komut Satırı** bölümüne **Ek Seçenekler** altında derleyici anahtarı yazmanız gerekir. Komut satırında **/Wp64** derleyici seçeneğini kullanırsanız, derleyici Komut Satırı Uyarısı D9002'yi çalıştırUr. 64 bit taşınabilirlik sorunlarını algılamak için bu seçeneği ve anahtar kelimeyi kullanmak yerine, 64 bit platform hedefleyen ve [/W4](compiler-option-warning-level.md) seçeneğini belirten bir MSVC derleyicisi kullanın. Daha fazla bilgi için bkz: [64 bit, x64 hedefleri için C++ projelerini yapılandırın.](../configuring-programs-for-64-bit-visual-cpp.md)

Aşağıdaki türdeki değişkenler, 64 bit işletim sisteminde kullanılıyormuş gibi 32 bit işletim sistemi üzerinde test edilir:

- int

- long

- pointer

64 bit, x64 kodu oluşturan bir derleyici kullanarak uygulamanızı düzenli olarak derlerseniz, 64 bit derleyici tüm sorunları algıladığı için 32 bit derlemelerinizde **/Wp64'ü** devre dışı bırakabilirsiniz. Windows 64 bit işletim sisteminin nasıl hedefleneöğretilen hakkında daha fazla bilgi için [bkz.](../configuring-programs-for-64-bit-visual-cpp.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik Sayfaları** iletişim kutusunu açın.

   Daha fazla bilgi için [Bkz. C++ derleyicisi ayarlanın ve Visual Studio'da özellikler oluşturun.](../working-with-project-properties.md)

1. **C/C++** klasörünü tıklatın.

1. Komut **Satırı** özelliği sayfasını tıklatın.

1. Ek **Seçenekler** kutusunu **/Wp64'ü**içerecek şekilde değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[C++ projelerini 64 bit, x64 hedefleri için yapılandırma](../configuring-programs-for-64-bit-visual-cpp.md)
