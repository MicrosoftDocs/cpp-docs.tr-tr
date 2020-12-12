---
description: Daha fazla bilgi edinin:/E (stdout için ön Işlem)
title: /E (stdout'a Önişle)
ms.date: 11/04/2016
f1_keywords:
- /e
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
ms.openlocfilehash: 9d6c9ea3a5fcf8e7ba06ede6e7e70d933b5c921a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192621"
---
# <a name="e-preprocess-to-stdout"></a>/E (stdout'a Önişle)

C ve C++ kaynak dosyalarını önceden işler ve önceden işlenen dosyaları standart çıkış cihazına kopyalar.

## <a name="syntax"></a>Syntax

```
/E
```

## <a name="remarks"></a>Açıklamalar

Bu işlemde, tüm Önişlemci yönergeleri uygulanır, makro genişletmeleri gerçekleştirilir ve açıklamalar kaldırılır. Önceden işlenmiş çıktıda açıklamaları korumak için [/c (ön Işleme sırasında açıklamaları koru)](c-preserve-comments-during-preprocessing.md) derleyici seçeneğini kullanın.

**/E** `#line` eklenen her dosyanın başındaki ve sonundaki ve koşullu derleme için Önişlemci yönergeleri tarafından kaldırılan satırların çevresine yönergeler ekler. Bu yönergeler, önceden işlenmiş dosyanın satırlarını yeniden numaralandırın. Sonuç olarak, sonraki işlem aşamaları sırasında oluşturulan hatalar, ön işlenmiş dosyadaki satırlar yerine orijinal kaynak dosyanın satır numaralarına başvurur.

**/E** seçeneği derlemeyi gizler. Derleme için önceden işlenmiş dosyayı yeniden göndermeniz gerekir. **/E** Ayrıca **/FA**, **/FA** ve **/FM** seçeneklerindeki çıkış dosyalarını da engeller. Daha fazla bilgi için bkz. [/FA,/FA (listeleme dosyası)](fa-fa-listing-file.md) ve [/FM (ad Mapfile)](fm-name-mapfile.md).

Yönergeleri gizlemek için `#line` , [/EP (#line yönergeleri olmadan stdout Için önceden işleme)](ep-preprocess-to-stdout-without-hash-line-directives.md) seçeneğini kullanın.

Önceden işlenmiş çıktıyı yerine bir dosyaya göndermek için `stdout` , bunun yerine [/p (bir dosyaya ön işlem)](p-preprocess-to-a-file.md) seçeneğini kullanın.

Yönergeleri gizlemek `#line` ve önceden işlenmiş çıktıyı bir dosyaya göndermek için **/P** ve **/EP** birlikte kullanın.

Önceden derlenmiş üst bilgileri **/e** seçeneğiyle kullanamazsınız.

Ayrı bir dosyaya ön işleme yapıldığında, belirteçlerin ardından boşlukların yayınlanmadığını unutmayın. Bu, geçersiz bir programın oluşmasına veya istenmeyen yan etkilere neden olabilir. Aşağıdaki program başarıyla derlenir:

```
#define m(x) x
m(int)main( )
{
   return 0;
}
```

Ancak, ile derlerseniz:

```
cl -E test.cpp > test2.cpp
```

`int main` Test2. cpp içinde yanlış olur `intmain` .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırı ön işler `ADD.C` , açıklamaları korur, yönergeler ekler `#line` ve sonucu standart çıkış cihazında görüntüler:

```
CL /E /C ADD.C
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
