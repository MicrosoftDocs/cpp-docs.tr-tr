---
description: Şu konuda daha fazla bilgi edinin:/GE (Yığın Yoklamalarını Etkinleştir)
title: /Ge (Yığın Yoklamalarını Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- /ge
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
ms.openlocfilehash: db996deb1c5b964661e5465fe72cfb0fab93df56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192024"
---
# <a name="ge-enable-stack-probes"></a>/Ge (Yığın Yoklamalarını Etkinleştir)

Yerel değişkenler için depolama gerektiren her işlev çağrısı için yığın araştırmalarını etkinleştirir.

## <a name="syntax"></a>Syntax

```
/Ge
```

## <a name="remarks"></a>Açıklamalar

Bu mekanizma, yığın araştırmasının işlevselliğini yeniden yazmak için yararlıdır. Yığın araştırmasını yeniden yazmak yerine [/GH (_Penter kanca Işlevini etkinleştir)](gh-enable-penter-hook-function.md) kullanmanız önerilir.

[/GS (denetim yığını denetim çağrıları)](gs-control-stack-checking-calls.md) aynı etkiye sahiptir.

**/Ge** kullanım dışıdır; Visual Studio 2005 ' den başlayarak, derleyici otomatik olarak yığın denetimi oluşturur. Kullanım dışı bırakılan derleyici seçeneklerinin bir listesi için, bkz. [kategoriye göre listelenen derleyici seçeneklerinde](compiler-options-listed-by-category.md) **kullanım dışı ve kaldırılmış derleyici seçenekleri** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
