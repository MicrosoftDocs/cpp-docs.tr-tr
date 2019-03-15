---
title: /GX (Özel Durum İşlemeyi Etkinleştir)
ms.date: 11/04/2016
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
ms.openlocfilehash: 43be8f6d0f080f0d85568ce5b089751fc68f0e8e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815469"
---
# <a name="gx-enable-exception-handling"></a>/GX (Özel Durum İşlemeyi Etkinleştir)

Kullanım dışı. Zaman uyumlu özel durum işleme işlevleri varsayımına kullanarak bildirilen kullanarak etkinleştirir `extern "C"` hiçbir zaman bir özel durum.

## <a name="syntax"></a>Sözdizimi

```
/GX
```

## <a name="remarks"></a>Açıklamalar

**/GX** kullanım dışı bırakılmıştır. Eşdeğer kullanın [/ehsc](eh-exception-handling-model.md) bunun yerine seçeneği. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** konusundaki [kategoriye göre listelenmiş derleyici seçenekleri](compiler-options-listed-by-category.md).

Varsayılan olarak, **/ehsc**, denk olan **/GX**, Visual Studio geliştirme ortamını kullanarak derleme yaptığınızda yürürlükte olur. Komut satırı araçlarını kullanarak, hiçbir özel durum işleme belirtilir. Bu eşdeğerdir **/GX-**.

Daha fazla bilgi için [C++ özel durum işleme](../../cpp/cpp-exception-handling.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Gezinti bölmesinde **yapılandırma özellikleri**, **C/C++**, **komut satırı**.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[/EH (Özel Durum İşleme Modeli)](eh-exception-handling-model.md)
