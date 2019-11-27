---
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
ms.openlocfilehash: 171ff0d0dfb1dec41bae5f6be63c941802c402a4
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245083"
---
# <a name="gx-enable-exception-handling"></a>/GX (Özel Durum İşlemeyi Etkinleştir)

Kullanım dışı. `extern "C"` kullanılarak belirtilen işlevlerin hiçbir zaman özel durum oluşturmayacağı varsayımını kullanarak zaman uyumlu özel durum işleme etkinleştirilir.

## <a name="syntax"></a>Sözdizimi

```
/GX
```

## <a name="remarks"></a>Açıklamalar

**/GX** kullanım dışıdır. Bunun yerine denk [/EHsc](eh-exception-handling-model.md) seçeneğini kullanın. Kullanım dışı bırakılan derleyici seçeneklerinin bir listesi için, [kategoriye göre listelenen derleyici seçenekleri](compiler-options-listed-by-category.md)konusunun **kullanım dışı ve kaldırılmış derleyici seçenekleri** bölümüne bakın.

Varsayılan olarak, **/GX**'nin eşdeğeri olan **/EHsc**, Visual Studio geliştirme ortamını kullanarak derlerken geçerli olur. Komut satırı araçlarını kullanırken özel durum işleme belirtilmez. Bu, **/GX-** ' nin eşdeğeridir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Gezinti bölmesinde, **yapılandırma özellikleri**, **CC++/** , **komut satırı**' nı seçin.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/EH (Özel Durum İşleme Modeli)](eh-exception-handling-model.md)
