---
title: -Wp64 (64-Bit taşınabilirlik sorunlarını Algıla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
dev_langs:
- C++
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac86fb6372db5aa88b4416dba07fd183f5f1df20
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700745"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (64 Bit Taşınabilirlik Sorunlarını Algıla)

Bu derleyici seçeneğini kullanımdan kalkmıştır. Visual Studio 2013 önce Visual Studio sürümlerinde, 64-bit taşınabilirlik sorunlarını ile işaretlenmiş türlerinde bunu algılar [__w64](../../cpp/w64.md) anahtar sözcüğü.

## <a name="syntax"></a>Sözdizimi

```
/Wp64
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, önce Visual Studio 2013, Visual Studio sürümlerinde **/Wp64** derleyici seçeneği 32-bit x86 oluşturan Visual C++ derleyicisi kapalıdır kod üzerinde Visual C++ derleyicinin 64-bit, x64 yapılara ve kod.

> [!IMPORTANT]
>  [/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) derleyici seçeneği ve [__w64](../../cpp/w64.md) anahtar sözcüğü, Visual Studio 2010 ve Visual Studio 2012'de kullanım dışı ve Visual Studio 2013 itibariyle desteklenmiyor. Bu anahtar kullanan bir proje dönüştürürseniz, anahtar dönüştürme sırasında geçirilmez. Visual Studio 2010 veya Visual Studio 2012'de bu seçeneği kullanmak için derleyici anahtarı altındaki yazın **ek seçenekler** içinde **komut satırı** Proje Özellikleri bölümünde. Kullanırsanız **/Wp64** derleyici seçeneği komut satırında derleyici komut satırı uyarısı D9002 verir. Bu seçenek ve anahtar sözcüğü 64-bit taşınabilirlik sorunlarını algılamak için kullanmak yerine 64-bit platformu hedefleyen bir Visual C++ Derleyici kullanın ve belirtin [/W4](../../build/reference/compiler-option-warning-level.md) seçeneği. Daha fazla bilgi için [yapılandırma Visual C++ 64 bit x64 için hedefleri](../../build/configuring-programs-for-64-bit-visual-cpp.md).

Bunlar bir 64-bit işletim sisteminde olarak kullanılıyorsa şu türlerinin değişkenleri bir 32-bit işletim sisteminde test edilmez:

- int

- long

- pointer

Düzenli olarak 64-bit, x64 oluşturan bir derleyici kullanarak uygulamanızı derlemek, kod, yalnızca devre dışı bırakabilirsiniz **/Wp64** , 32-bit derlemelerde çünkü 64 bit derleyici tüm sorunları algılar. Hedef bir Windows 64-bit işletim sistemi hakkında daha fazla bilgi için bkz. [yapılandırma Visual C++ 64 bit x64 için hedefleri](../../build/configuring-programs-for-64-bit-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu.

   Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** kutusuna **/Wp64**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Visual C++’ı 64 bit, x64 hedefler için yapılandırma](../../build/configuring-programs-for-64-bit-visual-cpp.md)