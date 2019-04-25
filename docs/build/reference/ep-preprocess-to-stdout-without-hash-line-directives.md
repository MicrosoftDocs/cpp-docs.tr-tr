---
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
ms.openlocfilehash: 49745b644234c0e5ce92661f14304531aaca5c69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293257"
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP (#line Yönergeleri Olmadan stdout'ta Önişle)

C ve C++ kaynak dosyalarını önceden işler ve standart çıktı cihazına önceden işlenmiş dosya kopyalar.

## <a name="syntax"></a>Sözdizimi

```
/EP
```

## <a name="remarks"></a>Açıklamalar

İşleminde, tüm önişlemci yönergeleri gerçekleştirilir, makro genişletmeleri gerçekleştirilir ve açıklamaları kaldırılır. Önceden işlenmiş çıktı açıklamalarda korumak için kullanın [/C (korumak açıklamaları sırasındaki)](c-preserve-comments-during-preprocessing.md) seçeneğini **/EP**.

**/EP** seçeneği derleme bastırır. Derleme için önceden işlenmiş dosyayı yeniden göndermeniz gerekir. **/EP** çıktı dosyalarından da bastırır **/FA**, **/Fa**, ve **/Fm** seçenekleri. Daha fazla bilgi için [/FA, /Fa (listeleme dosyası)](fa-fa-listing-file.md) ve [/Fm (eşlem dosyasını Adlandır)](fm-name-mapfile.md).

İşleme sonraki aşamaları sırasında oluşturulan hatalar için satır numaralarını önceden işlenmiş dosyayı yerine orijinal kaynak dosyasına bakın. Özgün kaynak dosyasına başvurmak için satır numaralarını istiyorsanız kullanın [/E (Stdout'a önişle)](e-preprocess-to-stdout.md) yerine. **/E** seçeneği ekler `#line` yönergeleri bu amaç için çıktı.

İle önceden işlenmiş çıkış göndermek için `#line` yönergelerini, bir dosyaya, kullanmak [/P (dosyaya ön işleme)](p-preprocess-to-a-file.md) bunun yerine seçeneği.

İle stdout için önceden işlenmiş çıkış göndermek için `#line` yönergeleri kullanan **/P** ve **/EP** birlikte.

Önceden derlenmiş üst bilgiler ile kullanamazsınız **/EP** seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **önişlemci** özellik sayfası.

1. Değiştirme **önceden işlenmiş dosya oluştur** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırını dosyasını ön işlemden geçirir `ADD.C`yorumları korur ve sonucu standart çıktı cihazında gösterir:

```
CL /EP /C ADD.C
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
