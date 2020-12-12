---
description: Daha fazla bilgi edinin:/GX (özel durum Işlemeyi etkinleştir)
title: /GX (Özel Durum İşlemeyi Etkinleştir)
ms.date: 11/19/2019
f1_keywords:
- /gx
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
ms.openlocfilehash: e511407504129f94b615fb3ec05c9f8a04766b10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191712"
---
# <a name="gx-enable-exception-handling"></a>/GX (Özel Durum İşlemeyi Etkinleştir)

Kullanım dışı. Tarafından tanımlanan işlevlerin `extern "C"` hiçbir zaman özel durum oluşturmaz, zaman uyumlu özel durum işleme etkinleştirilir.

## <a name="syntax"></a>Syntax

```
/GX
```

## <a name="remarks"></a>Açıklamalar

**/GX** kullanım dışıdır. Bunun yerine denk [/EHsc](eh-exception-handling-model.md) seçeneğini kullanın. Kullanım dışı bırakılan derleyici seçeneklerinin bir listesi için, [kategoriye göre listelenen derleyici seçenekleri](compiler-options-listed-by-category.md)konusunun **kullanım dışı ve kaldırılmış derleyici seçenekleri** bölümüne bakın.

Varsayılan olarak, **/GX**'nin eşdeğeri olan **/EHsc**, Visual Studio geliştirme ortamını kullanarak derlerken geçerli olur. Komut satırı araçlarını kullanırken özel durum işleme belirtilmez. Bu, **/GX-**' nin eşdeğeridir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Gezinti bölmesinde, **yapılandırma özellikleri**, **C/C++**, **komut satırı**' nı seçin.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[/EH (özel durum Işleme modeli)](eh-exception-handling-model.md)
