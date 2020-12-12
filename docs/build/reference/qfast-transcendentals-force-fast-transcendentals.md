---
description: Şu konuda daha fazla bilgi edinin:/Qfast_transcendentals (hızlı bir şekilde bu salları zorla)
title: /Qfast_transcendentals (Hızlı Soyutları Zorla)
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: 7701925aa7df33107b0829ade1c0c711eda14c08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225667"
---
# <a name="qfast_transcendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (Hızlı Soyutları Zorla)

Döküm işlevleri için satır içi kod üretir.

## <a name="syntax"></a>Syntax

```
/Qfast_transcendentals
```

## <a name="remarks"></a>Açıklamalar

Bu derleyici seçeneği, yürütme hızını artırmak için, geçiş işlevlerini satır içi koda dönüştürmek üzere zorlar. Bu seçenek yalnızca **/FP: except** veya **/FP: kesin** ile eşleştirildiği zaman etkilidir. Diğer işlevler için satır içi kod oluşturma, **/FP: Fast** altında varsayılan davranıştır.

Bu seçenek **/FP: Strict** ile uyumsuzdur. Kayan nokta derleyicisi seçenekleri hakkında daha fazla bilgi için bkz. [/FP (Floating-Point davranışını belirt)](fp-specify-floating-point-behavior.md) .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q seçenekler (düşük düzey Işlemler)](q-options-low-level-operations.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
