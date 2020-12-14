---
description: Daha fazla bilgi edinin:/F (yığın boyutunu ayarla)
title: /F (Yığın Boyutunu Ayarla)
ms.date: 11/04/2016
f1_keywords:
- /f
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
ms.openlocfilehash: 5bf8b0855c65fc39caf8935b06a877c62a4e0df0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200786"
---
# <a name="f-set-stack-size"></a>/F (Yığın Boyutunu Ayarla)

Program yığın boyutunu bayt cinsinden ayarlar.

## <a name="syntax"></a>Syntax

> **/F** *numarası*

## <a name="arguments"></a>Arguments

*sayısından*<br/>
Yığın boyutu bayt cinsinden.

## <a name="remarks"></a>Açıklamalar

Bu seçenek olmadan, yığın boyutu varsayılan olarak 1 MB 'tır. *Sayı* bağımsız değişkeni Decimal veya C dili gösteriminde olabilir. Bağımsız değişken, 1 ile bağlayıcı tarafından kabul edilen en büyük yığın boyutu arasında değişebilir. Bağlayıcı belirtilen değeri en yakın 4 bayta yuvarlar. **/F** ve *sayı* arasındaki alan isteğe bağlıdır.

Programınız yığın taşması iletileri alırsa yığın boyutunu artırmanız gerekebilir.

Yığın boyutunu Ayrıca şu şekilde ayarlayabilirsiniz:

- **/Stack** bağlayıcı seçeneğini kullanma. Daha fazla bilgi için bkz. [/Stack](stack.md).

- . Exe dosyasında EDITBIN kullanma. Daha fazla bilgi için bkz. [editbin başvurusu](editbin-reference.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
