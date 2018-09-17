---
title: -E (Stdout'a önişle) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /e
dev_langs:
- C++
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48517f4469f203f5e29fbaa4ec105a3e36aafb44
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720277"
---
# <a name="e-preprocess-to-stdout"></a>/E (stdout'a Önişle)

C ve C++ kaynak dosyalarını önceden işler ve standart çıktı cihazına önceden işlenmiş dosya kopyalar.

## <a name="syntax"></a>Sözdizimi

```
/E
```

## <a name="remarks"></a>Açıklamalar

Bu işlem, tüm önişlemci yönergeleri gerçekleştirilir, makro genişletmeleri gerçekleştirilir ve açıklamaları kaldırılır. Önceden işlenmiş çıktı açıklamalarda korumak için kullanın [/C (korumak açıklamaları sırasındaki)](../../build/reference/c-preserve-comments-during-preprocessing.md) derleyici seçeneği.

**/E** ekler `#line` başlangıcını ve bitişini eklenen her dosyanın ve koşullu derleme için ön işlemci yönergeleri tarafından kaldırılan satırları etrafında çıktısına yönergeleri. Bu yönergeler, önceden işlenmiş dosyayı satırlarını numaralandırmak. Sonuç olarak, işleme sonraki aşamaları sırasında oluşturulan hatalar satır numaralarını önceden işlenmiş dosyayı satırlar yerine orijinal kaynak dosyasına bakın.

**/E** seçeneği derleme bastırır. Derleme için önceden işlenmiş dosyayı yeniden göndermeniz gerekir. **/E** çıktı dosyalarından da bastırır **/FA**, **/Fa**, ve **/Fm** seçenekleri. Daha fazla bilgi için [/FA, /Fa (listeleme dosyası)](../../build/reference/fa-fa-listing-file.md) ve [/Fm (eşlem dosyasını Adlandır)](../../build/reference/fm-name-mapfile.md).

Bastırmak için `#line` yönergeleri kullanan [/EP (#line yönergeleri olmadan stdout'ta önişle ön işleme)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) bunun yerine seçeneği.

Önceden işlenmiş çıkış için bir dosya göndermek için `stdout`, kullanın [/P (dosyaya ön işleme)](../../build/reference/p-preprocess-to-a-file.md) bunun yerine seçeneği.

Bastırmak için `#line` yönergeleri ve önceden işlenen çıkışı bir dosyaya gönderme **/P** ve **/EP** birlikte.

Önceden derlenmiş üst bilgiler ile kullanamazsınız **/E** seçeneği.

Ayrı bir dosya için ön işleme sırasında alanları belirteçleri sonra gösterilen değil olduğunu unutmayın. Bu neden geçersiz bir programda veya sahip istenmeyen yan etkiler. Aşağıdaki program başarıyla derler:

```
#define m(x) x
m(int)main( )
{
   return 0;
}
```

Ancak, derleme yaparsanız:

```
cl -E test.cpp > test2.cpp
```

`int main` içinde Test2.cpp yanlış olacaktır `intmain`.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler**kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırını önceden işler `ADD.C`, yorumları korur, ekler `#line` yönergeleri ve sonucu standart çıktı cihazında gösterir:

```
CL /E /C ADD.C
```

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)