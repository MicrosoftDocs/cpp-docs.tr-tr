---
description: Daha fazla bilgi edinin:/EP (#line yönergeler olmadan stdout için önceden Işlem)
title: /EP (#line Yönergeleri Olmadan stdout'ta Önişle)
ms.date: 11/04/2016
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
ms.openlocfilehash: cbd36cd6bdafe315a7a6ef01b46857725033bd69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201007"
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP (#line Yönergeleri Olmadan stdout'ta Önişle)

C ve C++ kaynak dosyalarını önceden işler ve önceden işlenen dosyaları standart çıkış cihazına kopyalar.

## <a name="syntax"></a>Syntax

```
/EP
```

## <a name="remarks"></a>Açıklamalar

İşlemde, tüm Önişlemci yönergeleri uygulanır, makro genişletmeleri gerçekleştirilir ve açıklamalar kaldırılır. Önceden işlenmiş çıktıda açıklamaları korumak için, **/EP** ile [/C (ön işleme sırasında açıklamaları koru)](c-preserve-comments-during-preprocessing.md) seçeneğini kullanın.

**/EP** seçeneği derlemeyi gizler. Derleme için önceden işlenmiş dosyayı yeniden göndermeniz gerekir. **/EP** Ayrıca **/FA**, **/FA** ve **/FM** seçeneklerindeki çıkış dosyalarını da engeller. Daha fazla bilgi için bkz. [/FA,/FA (listeleme dosyası)](fa-fa-listing-file.md) ve [/FM (ad Mapfile)](fm-name-mapfile.md).

Sonraki işlem aşamaları sırasında oluşturulan hatalar, orijinal kaynak dosya yerine, önceden işlenmiş dosyanın satır numaralarına başvurur. Satır numaralarının özgün kaynak dosyasına başvurmasını istiyorsanız, bunun yerine [/e (stdout Için preprocess)](e-preprocess-to-stdout.md) kullanın. **/E** seçeneği, `#line` Bu amaçla çıktıya yönergeler ekler.

Önceden işlenmiş çıktıyı `#line` yönergeler ile bir dosyaya göndermek için, bunun yerine [/p (bir dosyaya ön işlem)](p-preprocess-to-a-file.md) seçeneğini kullanın.

Önceden işlenmiş çıktıyı stdout 'a göndermek için `#line` yönergeleriyle birlikte **/P** ve **/EP** kullanın.

Önceden derlenmiş üst bilgileri **/EP** seçeneğiyle kullanamazsınız.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Önişlemci** Özellik sayfasına tıklayın.

1. **Önceden Işlenmiş dosya oluştur** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırı, dosyayı önceden işler `ADD.C` , Yorumları korur ve standart çıkış cihazında sonucu görüntüler:

```
CL /EP /C ADD.C
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
