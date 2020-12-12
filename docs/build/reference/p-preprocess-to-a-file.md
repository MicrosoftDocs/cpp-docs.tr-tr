---
description: Daha fazla bilgi edinin:/P (bir dosyaya ön Işlem)
title: /P (Dosyaya Önişle)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
ms.openlocfilehash: 20bca03694c866baa0575445271fc4f587268096
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226200"
---
# <a name="p-preprocess-to-a-file"></a>/P (Dosyaya Önişle)

C ve C++ kaynak dosyalarını önceden işler ve önceden işlenmiş çıktıyı bir dosyaya yazar.

## <a name="syntax"></a>Syntax

```
/P
```

## <a name="remarks"></a>Açıklamalar

Dosya, kaynak dosya ve bir. ı uzantısıyla aynı temel ada sahip. İşlemde, tüm Önişlemci yönergeleri uygulanır, makro genişletmeleri gerçekleştirilir ve açıklamalar kaldırılır. Önceden işlenmiş çıktıda açıklamaları korumak için [/c (ön Işleme sırasında açıklamaları koru)](c-preserve-comments-during-preprocessing.md) seçeneğini **/p** ile birlikte kullanın.

**/P** `#line` , eklenen her dosyanın başlangıcında ve sonunda ve koşullu derleme için Önişlemci yönergeleri tarafından kaldırılan satırların çevresine yönergeler ekler. Bu yönergeler, önceden işlenmiş dosyanın satırlarını yeniden numaralandırın. Sonuç olarak, sonraki işlem aşamaları sırasında oluşturulan hatalar, ön işlenmiş dosyadaki satırlar yerine orijinal kaynak dosyanın satır numaralarına başvurur. Yönergelerin oluşturulmasını engellemek için `#line` [/EP 'yi (#line yönergeleri olmadan stdout Için önceden işleme)](ep-preprocess-to-stdout-without-hash-line-directives.md) ve **/p**'yi kullanın.

**/P** seçeneği derlemeyi gizler. [/Fo (nesne dosya adı)](fo-object-file-name.md)kullanıyor olsanız bile bir. obj dosyası oluşturmaz. Derleme için önceden işlenmiş dosyayı yeniden göndermeniz gerekir. **/P** Ayrıca **/FA**, **/FA** ve **/FM** seçeneklerindeki çıkış dosyalarını da engeller. Daha fazla bilgi için bkz. [/FA,/FA (listeleme dosyası)](fa-fa-listing-file.md) ve [/FM (ad Mapfile)](fm-name-mapfile.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Önişlemci** Özellik sayfasına tıklayın.

1. **Önceden Işlenmiş dosya oluştur** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırı önceden işlenir `ADD.C` , Yorumları korur, yönergeleri ekler `#line` ve sonucu bir dosyaya yazar `ADD.I` :

```
CL /P /C ADD.C
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[/Fi (çıktı dosyası adını Önişle)](fi-preprocess-output-file-name.md)
