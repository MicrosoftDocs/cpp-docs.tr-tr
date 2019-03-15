---
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
ms.openlocfilehash: 9db595daa7de7820b594a8515ece7481b4382c98
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820422"
---
# <a name="f-set-stack-size"></a>/F (Yığın Boyutunu Ayarla)

Program yığın boyutu bayt cinsinden ayarlar.

## <a name="syntax"></a>Sözdizimi

> **/F** *numarası*

## <a name="arguments"></a>Arguments

*Sayı*<br/>
Yığın boyutunu bayt cinsinden.

## <a name="remarks"></a>Açıklamalar

Bu seçenek olmadan, yığın boyutu 1 MB ile varsayılan olarak. *Numarası* bağımsız değişkeni, ondalık ya da C dili gösterimi olabilir. Bağımsız değişkeni 1'den bağlayıcı tarafından kabul edilen maksimum yığın boyutu değişebilir. Bağlayıcı, belirtilen değeri en yakın 4 bayt yuvarlar. Arasındaki boşluk **/F** ve *numarası* isteğe bağlıdır.

Programınızı yığın taşması iletileri alırsa yığın boyutunu artırabilir gerekebilir.

Ayrıca yığın boyutu ayarlayabileceğiniz:

- Kullanarak **/STACK** bağlayıcı seçeneği. Daha fazla bilgi için [/STACK](stack.md).

- EDITBIN .exe dosyası kullanma. Daha fazla bilgi için [EDITBIN başvurusu](editbin-reference.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
