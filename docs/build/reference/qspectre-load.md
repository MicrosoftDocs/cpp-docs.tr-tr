---
title: /Qspectre-Load
description: Microsoft C/C++ DERLEYICISI (MSVC)/Qspectre-Load seçeneğini açıklar.
ms.date: 01/28/2020
helpviewer_keywords:
- /Qspectre-load
ms.openlocfilehash: a766cf9b7eef11b7c5819cbdaa7706ab5b80c608
ms.sourcegitcommit: 0f4ee9056d65043fa5a715f0ad1031c0ed30e2b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2020
ms.locfileid: "77035531"
---
# <a name="qspectre-load"></a>/Qspectre-Load

Her yük yönergesiyle ilgili serileştirme yönergelerinin derleyici oluşturma sayısını belirtir. Bu seçenek **/Qspectre** bayrağını genişleterek, yükleri temel alan herhangi bir olası öngörülebilir **yürütme tarafı kanal saldırılarına** karşı azaltıcı değildir.

## <a name="syntax"></a>Sözdizimi

> **/Qspectre-Load**

## <a name="remarks"></a>Açıklamalar

**/Qspectre-Load** derleyicinin bellekten gelen yükleri algılamasına ve bundan sonra serileştirme yönergeleri eklemesine neden olur. `RET` ve `CALL`dahil olmak üzere belleği yükleyen denetim akışı yönergeleri, bir yük ve denetim akışı aktarımına bölünür. Yükün korunduğundan emin olmak için yük bir `LFENCE` gelir. Derleyicinin `jmp` yönergesi gibi denetim akışı yönergelerine bölünemeyeceği durumlar vardır. bu nedenle, alternatif bir azaltma tekniği kullanır. Örneğin, derleyici, burada gösterildiği gibi, bir LÇIT eklemeden önce, hedefi tekrar tekrar yükleme yönergelerini ekleyerek `jmp [rax]` azaltır:

```asm
    xor rbx, [rax]
    xor rbx, [rax]  ; force a load of [rax]
    lfence          ; followed by an LFENCE
    jmp [rax]
```

**/Qspectre-Load** tüm yüklerin bir şekilde durmasını durdurduğundan, performans etkisi yüksektir. Risk azaltma her yerde uygun değildir. Koruma gerektirmeyen performans açısından kritik kod blokları varsa, `__declspec(spectre(nomitigation))`kullanarak bu azaltmaları devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [__declspec Spectre](../../cpp/spectre.md).

**/Qspectre-Load** seçeneği varsayılan olarak kapalıdır ve tüm iyileştirme düzeylerini destekler.

**/Qspectre-Load** seçeneği, Visual Studio 2019 sürüm 16,5 ve sonraki sürümlerinde kullanılabilir. Bu seçenek yalnızca x86 ve x64 işlemcileri hedefleyen derleyicilerde kullanılabilir. ARM İşlemcileri hedefleyen derleyicilerde kullanılamaz.

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
