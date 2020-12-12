---
description: Şu konularda daha fazla bilgi edinin:/Wp64 (64-bit taşınabilirlik sorunlarını Algıla)
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
ms.openlocfilehash: d1ee441089531c4ebe222c73f6cec16b59fa7583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261092"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (64 Bit Taşınabilirlik Sorunlarını Algıla)

Bu derleyici seçeneği artık kullanılmıyor. Visual Studio 2013 önce Visual Studio sürümlerinde, bu, [__w64](../../cpp/w64.md) anahtar sözcüğüyle işaretlenmiş türler üzerinde 64 bitlik taşınabilirlik sorunlarını algılar.

## <a name="syntax"></a>Syntax

```
/Wp64
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, Visual Studio 2013 önce Visual Studio sürümlerinde **/Wp64** derleyici seçeneği 32 bitlik x86 kodu oluşturan MSVC derleyicisinde ve 64 bit, x64 kodu oluşturan MSVC derleyicisinde kapalıdır.

> [!IMPORTANT]
> [/Wp64](wp64-detect-64-bit-portability-issues.md) derleyici seçeneği ve [__W64](../../cpp/w64.md) anahtar sözcüğü Visual Studio 2010 ve Visual Studio 2012 ' de kullanımdan kaldırılmıştır ve Visual Studio 2013 itibaren desteklenmez. Bu anahtarı kullanan bir projeyi dönüştürürseniz, anahtar dönüştürme sırasında geçirilmez. Visual Studio 2010 veya Visual Studio 2012 ' de bu seçeneği kullanmak için, proje özelliklerinin **komut satırı** bölümünde **ek seçenekler** altında derleyici anahtarını yazmanız gerekir. Komut satırında **/Wp64** derleyici seçeneğini kullanırsanız, derleyici Command-Line uyarı D9002 ' ı yayınlar. 64-bit taşınabilirlik sorunlarını algılamak için bu seçeneği ve anahtar sözcüğü kullanmak yerine, 64 bit platformu hedefleyen bir MSVC derleyicisi kullanın ve [/W4](compiler-option-warning-level.md) seçeneğini belirtin. Daha fazla bilgi için bkz. [64 bit, x64 hedefleri Için C++ projelerini yapılandırma](../configuring-programs-for-64-bit-visual-cpp.md).

Aşağıdaki türlerin değişkenleri, 64 bit işletim sisteminde kullanılmakta olduğu gibi 32 bitlik bir işletim sisteminde test edilmiştir:

- int

- long

- pointer

Uygulamanızı düzenli olarak 64 bit, x64 kodu oluşturan bir derleyici kullanarak derlerseniz, 64-bit derleyicisi tüm sorunları algılayacağından, 32 bit derlemelerinizi **/Wp64** olarak devre dışı bırakabilirsiniz. Windows 64 bit işletim sistemini hedefleme hakkında daha fazla bilgi için bkz. [64 bit, x64 hedefleri Için C++ projelerini yapılandırma](../configuring-programs-for-64-bit-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın.

   Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusunu **/Wp64** içerecek şekilde değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[64 bit, x64 hedefleri için C++ projelerini yapılandırma](../configuring-programs-for-64-bit-visual-cpp.md)
