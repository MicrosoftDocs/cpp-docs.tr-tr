---
description: Daha fazla bilgi edinin:/GL (tüm program iyileştirmesi)
title: /GL (Bütün program iyileştirmesi)
ms.date: 03/05/2021
f1_keywords:
- /GL
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.openlocfilehash: 509deaae8881c4875a9ec2ddf4d5f1ee7744a2cf
ms.sourcegitcommit: c0c9cdae79f19655e809a4979227c51bb19cff63
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102236556"
---
# <a name="gl-whole-program-optimization"></a>`/GL` (Tüm program iyileştirmesi)

Tüm program iyileştirmesini mümkün hale getirme.

## <a name="syntax"></a>Syntax

> **`/GL`**[**`-`**]

## <a name="remarks"></a>Açıklamalar

Tüm program iyileştirmesi derleyicinin programdaki tüm modüller hakkındaki bilgilerle iyileştirmeler gerçekleştirmesine olanak sağlar. Tüm program iyileştirmesi olmadan, iyileştirmeler modül başına (compiland) temelinde gerçekleştirilir.

Tüm program iyileştirmesi varsayılan olarak kapalıdır ve açıkça etkinleştirilmesi gerekir. Ancak, ile açıkça devre dışı bırakmak da mümkündür **`/GL-`** .

Tüm modüller hakkında bilgi içeren derleyici şunları yapabilir:

- İşlev sınırları genelinde yazmaçların kullanımını iyileştirin.

- Genel verilerde yapılan değişiklikleri izlemeye daha iyi bir iş yapın ve yükleme sayısı ve depolar için bir azalma sağlar.

- İşaretçi başvurusu tarafından değiştirilen olası öğe kümesini izleyin ve gerekli yüklemeleri ve depoları azaltır.

- İşlev başka bir modülde tanımlansa bile, modülde satır içi bir işlev.

*`.obj`* ile oluşturulan dosyalar **`/GL`** ve gibi bağlayıcı yardımcı programları tarafından kullanılamaz [`EDITBIN`](editbin-reference.md) [`DUMPBIN`](dumpbin-reference.md) .

Programınızı ve ile derlerseniz **`/GL`** [`/c`](c-compile-without-linking.md) , çıktı dosyasını oluşturmak için/LTCG bağlayıcı seçeneğini kullanmanız gerekir.

[`/ZI`](z7-zi-zi-debug-information-format.md) ile kullanılamaz **`/GL`**

Geçerli sürümde ile oluşturulan dosyaların biçimi, **`/GL`** Visual Studio 'nun sonraki sürümlerinde ve MSVC araç takımının okunmamamasından kaynaklanır. *`.lib`* Tüm Visual Studio sürümleri için dosyanın kopyalarını teslim etmek zorunda olmadığınız takdirde, artık kullanıcılarınızın kullanmasını beklediğinizi ve gelecekte *`.lib`* tarafından oluşturulan dosyalardan bir dosya göndermeyin *`.obj`* **`/GL`** . Daha fazla bilgi için bkz. [ikili uyumlulukta kısıtlamalar](../../porting/binary-compat-2015-2017.md#restrictions).

*`.obj`* Dosya, dosyayı **`/GL`** *`.lib`* *`.lib`* üreten aynı makineye bağlanmadığı müddetçe, ve önceden derlenmiş üst bilgi dosyaları tarafından oluşturulan dosyalar bir dosya oluşturmak için kullanılmamalıdır **`/GL`** *`.obj`* . *`.obj`* Dosyanın ön derlenmiş üstbilgi dosyasındaki bilgiler bağlantı sırasında gereklidir.

İle kullanılabilen iyileştirmeler ve tüm program iyileştirmesinin sınırlamaları hakkında daha fazla bilgi için bkz [`/LTCG`](ltcg-link-time-code-generation.md) ..  **`/GL`** Ayrıca profil temelli iyileştirme kullanılabilir hale gelir. Profil temelli iyileştirmeler için derleme yaparken ve profil temelli iyileştirmelerinden işlev sıralamasını istiyorsanız, [`/Gy`](gy-enable-function-level-linking.md) /g, ' ı belirten bir derleyici seçeneği veya derleme yapmanız gerekir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

Geliştirme ortamında belirtme hakkında daha fazla bilgi için **`/GL`** bkz. [ `/LTCG` (bağlama zamanı kodu oluşturma)](ltcg-link-time-code-generation.md) .

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
