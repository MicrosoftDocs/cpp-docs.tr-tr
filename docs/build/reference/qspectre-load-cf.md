---
title: /Qspectre-load-cf
description: Microsoft C/C++ DERLEYICISI (MSVC)/Qspectre-load-cf seçeneğini açıklar.
ms.date: 01/28/2020
helpviewer_keywords:
- /Qspectre-load-cf
no-loc:
- Qspectre-load-cf
ms.openlocfilehash: c32b843df517cb6fbe662fba0b592cbf745f1764
ms.sourcegitcommit: 0f4ee9056d65043fa5a715f0ad1031c0ed30e2b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2020
ms.locfileid: "77035524"
---
# /Qspectre-load-cf

Yük içeren her denetim akışı yönergesine ilişkin serileştirme yönergelerinin derleme üretilmesini belirtir. Bu seçenek, [/Qspectre-Load](qspectre-load.md) seçeneğinde gerçekleştirilen azaltmanın bir alt kümesini gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

> **/Qspectre-load-cf**

## <a name="remarks"></a>Açıklamalar

**/Qspectre-load-cf** derleyicinin bellekten yüklenen `JMP`, `RET`ve `CALL` denetim akışı talimatlarını algılamasına ve yüklemeden sonra serileştirme yönergeleri eklemesine neden olur. Mümkün olduğunda, bu yönergeler bir yükleme ve bir denetim akışı aktarımına ayrılır. Yükün korunduğundan emin olmak için yük bir `LFENCE` gelir. Derleyicinin `JMP` yönergesi gibi yönergeleri bölünemeyeceği durumlar vardır. bu nedenle, alternatif bir azaltma tekniği kullanır. Örneğin, derleyici, burada gösterildiği gibi, bir LÇIT eklemeden önce, hedefi tekrar tekrar yükleme yönergelerini ekleyerek `jmp [rax]` azaltır:

```asm
    xor rbx, [rax]
    xor rbx, [rax]  ; force a load of [rax]
    lfence          ; followed by an LFENCE
    jmp [rax]
```

**/Qspectre-load-cf** tüm yüklerin denetim akışı yönergelerindeki bir şekilde durmasını durdurduğundan, performans etkisi yüksektir. Risk azaltma her yerde uygun değildir. Koruma gerektirmeyen performans açısından kritik kod blokları varsa, `__declspec(spectre(nomitigation))`kullanarak bu azaltmaları devre dışı bırakabilirsiniz.

**/Qspectre-load-cf** seçeneği varsayılan olarak kapalıdır ve tüm iyileştirme düzeylerini destekler.

**/Qspectre-load-cf** seçeneği Visual Studio 2019 sürüm 16,5 ve sonraki sürümlerde kullanılabilir. Bu seçenek yalnızca x86 ve x64 işlemcileri hedefleyen derleyicilerde kullanılabilir. ARM İşlemcileri hedefleyen derleyicilerde kullanılamaz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

2. **Yapılandırma özellikleri** > **CC++ /**  > **kod oluşturma** Özellik sayfası ' nı seçin.

3. **Spectre hafifletme** özelliği için yeni bir değer seçin. Değişikliği uygulamak için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q seçenekler (düşük düzey işlemler)](q-options-low-level-operations.md)\
[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
