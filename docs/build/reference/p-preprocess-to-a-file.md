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
ms.openlocfilehash: 9b3d84d94ed75acd68011b895afbc4f190019673
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622254"
---
# <a name="p-preprocess-to-a-file"></a>/P (Dosyaya Önişle)

C ve C++ kaynak dosyalarını önceden işler ve önceden işlenen çıkışı bir dosyaya yazar.

## <a name="syntax"></a>Sözdizimi

```
/P
```

## <a name="remarks"></a>Açıklamalar

Dosya kaynak dosyasını ve .i uzantı aynı temel ada sahip. İşleminde, tüm önişlemci yönergeleri gerçekleştirilir, makro genişletmeleri gerçekleştirilir ve açıklamaları kaldırılır. Önceden işlenmiş çıktı açıklamalarda korumak için kullanın [/C (korumak açıklamaları sırasındaki)](../../build/reference/c-preserve-comments-during-preprocessing.md) seçeneği ile birlikte **/P**.

**/P** ekler `#line` başlangıcına ve son eklenen her dosyanın ve koşullu derleme için ön işlemci yönergeleri tarafından kaldırılan satırları etrafında çıkış yönergeleri. Bu yönergeler, önceden işlenmiş dosyayı satırlarını numaralandırmak. Sonuç olarak, işleme sonraki aşamaları sırasında oluşturulan hatalar satır numaralarını önceden işlenmiş dosyayı satırlar yerine orijinal kaynak dosyasına bakın. Oluşturulmasını engellemek için `#line` yönergeleri kullanan [/EP (#line yönergeleri olmadan stdout'ta önişle ön işleme)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) yanı **/P**.

**/P** seçeneği derleme bastırır. Kullansanız bile bir .obj dosyası oluşturmaz [/Fo (nesne dosya adı)](../../build/reference/fo-object-file-name.md). Derleme için önceden işlenmiş dosyayı yeniden göndermeniz gerekir. **/P** çıktı dosyalarından da bastırır **/FA**, **/Fa**, ve **/Fm** seçenekleri. Daha fazla bilgi için [/FA, /Fa (listeleme dosyası)](../../build/reference/fa-fa-listing-file.md) ve [/Fm (eşlem dosyasını Adlandır)](../../build/reference/fm-name-mapfile.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

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

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/Fi (Çıktı Dosyası Adını Önişle)](../../build/reference/fi-preprocess-output-file-name.md)