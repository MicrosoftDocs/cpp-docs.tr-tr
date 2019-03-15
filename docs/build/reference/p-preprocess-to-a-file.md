---
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
ms.openlocfilehash: 5e6302d90647bce7e37c47a619e814cab300aaee
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813766"
---
# <a name="p-preprocess-to-a-file"></a>/P (Dosyaya Önişle)

C ve C++ kaynak dosyalarını önceden işler ve önceden işlenen çıkışı bir dosyaya yazar.

## <a name="syntax"></a>Sözdizimi

```
/P
```

## <a name="remarks"></a>Açıklamalar

Dosya kaynak dosyasını ve .i uzantı aynı temel ada sahip. İşleminde, tüm önişlemci yönergeleri gerçekleştirilir, makro genişletmeleri gerçekleştirilir ve açıklamaları kaldırılır. Önceden işlenmiş çıktı açıklamalarda korumak için kullanın [/C (korumak açıklamaları sırasındaki)](c-preserve-comments-during-preprocessing.md) seçeneği ile birlikte **/P**.

**/P** ekler `#line` başlangıcına ve son eklenen her dosyanın ve koşullu derleme için ön işlemci yönergeleri tarafından kaldırılan satırları etrafında çıkış yönergeleri. Bu yönergeler, önceden işlenmiş dosyayı satırlarını numaralandırmak. Sonuç olarak, işleme sonraki aşamaları sırasında oluşturulan hatalar satır numaralarını önceden işlenmiş dosyayı satırlar yerine orijinal kaynak dosyasına bakın. Oluşturulmasını engellemek için `#line` yönergeleri kullanan [/EP (#line yönergeleri olmadan stdout'ta önişle ön işleme)](ep-preprocess-to-stdout-without-hash-line-directives.md) yanı **/P**.

**/P** seçeneği derleme bastırır. Kullansanız bile bir .obj dosyası oluşturmaz [/Fo (nesne dosya adı)](fo-object-file-name.md). Derleme için önceden işlenmiş dosyayı yeniden göndermeniz gerekir. **/P** çıktı dosyalarından da bastırır **/FA**, **/Fa**, ve **/Fm** seçenekleri. Daha fazla bilgi için [/FA, /Fa (listeleme dosyası)](fa-fa-listing-file.md) ve [/Fm (eşlem dosyasını Adlandır)](fm-name-mapfile.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **önişlemci** özellik sayfası.

1. Değiştirme **önceden işlenmiş dosya oluştur** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırını önceden işler `ADD.C`, yorumları korur, ekler `#line` yönergeleri ve sonucu bir dosyaya yazar `ADD.I`:

```
CL /P /C ADD.C
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[/Fi (Çıktı Dosyası Adını Önişle)](fi-preprocess-output-file-name.md)
