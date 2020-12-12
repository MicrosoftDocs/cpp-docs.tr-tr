---
description: Şu konuda daha fazla bilgi edinin:/bigobj (içindeki bölüm sayısını artırın. Obj dosyası)
title: /bigobj (.Obj Dosyasında Bölüm Sayısını Arttırma)
ms.date: 03/26/2019
f1_keywords:
- /bigobj
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
ms.openlocfilehash: 4e820211ec46ad2a2d125552f95fb8a82c6f57ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182703"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (.Obj Dosyasında Bölüm Sayısını Arttırma)

**/bigobj** bir nesne dosyasının içerebileceği bölüm sayısını artırır.

## <a name="syntax"></a>Syntax

> **/bigobj**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir nesne dosyası en fazla 65.279 (neredeyse 2 ^ 16) adreslenebilir bölüm tutabilir. Bu sınır, hangi hedef platformun belirtildiğine bakılmaksızın geçerlidir. **/bigobj** bu adres kapasitesini 4.294.967.296 (2 ^ 32) olarak artırır.

Çoğu modül, 65.279 'den fazla bölüm içeren bir. obj dosyası oluşturmaz. Ancak, makine tarafından oluşturulan kod veya şablon kitaplıklarının ağır kullanımını sağlayan kod, daha fazla bölüm tutan. obj dosyaları gerektirebilir. makine tarafından oluşturulan XAML kodu çok sayıda üst bilgi içerdiğinden, **/bigobj** varsayılan olarak evrensel WINDOWS platformu (UWP) projelerinde etkindir. UWP uygulama projesinde bu seçeneği devre dışı bırakırsanız, kodunuz derleyici hatası C1128 oluşturabilir.

PE COFF nesne dosyası biçimi hakkında bilgi için, Windows belgelerindeki [PE biçimi](/windows/win32/debug/pe-format) bölümüne bakın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusuna **/bigobj** derleyici seçeneğini girin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
