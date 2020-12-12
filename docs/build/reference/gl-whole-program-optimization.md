---
description: Daha fazla bilgi edinin:/GL (tüm program Iyileştirmesi)
title: /GL (Bütün Program İyileştirmesi)
ms.date: 11/04/2016
f1_keywords:
- /gl
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
ms.openlocfilehash: ad42eaeeacf897686831c9b415aa62026b5644f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200201"
---
# <a name="gl-whole-program-optimization"></a>/GL (Bütün Program İyileştirmesi)

Tüm program iyileştirmesini mümkün hale getirme.

## <a name="syntax"></a>Syntax

```
/GL[-]
```

## <a name="remarks"></a>Açıklamalar

Tüm program iyileştirmesi derleyicinin programdaki tüm modüller hakkındaki bilgilerle iyileştirmeler gerçekleştirmesine olanak sağlar. Tüm program iyileştirmesi olmadan, iyileştirmeler modül başına (compiland) temelinde gerçekleştirilir.

Tüm program iyileştirmesi varsayılan olarak kapalıdır ve açıkça etkinleştirilmesi gerekir. Ancak, bunu **/GL-** ile açıkça devre dışı bırakmak da mümkündür.

Tüm modüller hakkında bilgi içeren derleyici şunları yapabilir:

- İşlev sınırları genelinde yazmaçların kullanımını iyileştirin.

- Genel verilerde yapılan değişiklikleri izlemeye daha iyi bir iş yapın ve yükleme sayısı ve depolar için bir azalma sağlar.

- Bir işaretçi başvurusu tarafından değiştirilen olası öğe kümesini izlemenin daha iyi bir işi yapın, yükleme ve mağaza sayısını azaltır.

- İşlev başka bir modülde tanımlansa bile, modülde satır içi bir işlev.

**/GL** ile oluşturulan. obj dosyaları [editbin](editbin-reference.md) ve [dumpbin](dumpbin-reference.md)gibi bağlayıcı yardımcı programları tarafından kullanılamaz.

Programınızı **/GL** ve [/c](c-compile-without-linking.md)ile derlerseniz, çıktı dosyasını oluşturmak için/LTCG bağlayıcı seçeneğini kullanmanız gerekir.

[/Zi](z7-zi-zi-debug-information-format.md) **/GL** ile kullanılamaz

Geçerli sürümde **/GL** ile oluşturulan dosyaların biçimi, sonraki Visual C++ sürümleri tarafından okunamayabilir. Kullanıcılarınızın, şimdi ve gelecekte kullanmasını istediğiniz tüm Visual C++ sürümleri için. lib dosyasının kopyalarını teslim etmek istemediğiniz müddetçe, **/GL** ile oluşturulan. lib dosyasını sunmamalıdır.

**/GL** ve önceden derlenmiş üst bilgi dosyalarıyla oluşturulan. obj dosyaları,. lib dosyası **/GL** . obj dosyasını üreten aynı makineye bağlanmadığı müddetçe bir. lib dosyası oluşturmak için kullanılmamalıdır. . Obj dosyasının ön derlenmiş üstbilgi dosyasındaki bilgiler bağlantı zamanında gerekecektir.

İle kullanılabilen iyileştirmeler ve tüm program iyileştirmesinin sınırlamaları hakkında daha fazla bilgi için bkz. [/LTCG](ltcg-link-time-code-generation.md).  **/GL** Ayrıca profil temelli iyileştirme kullanılabilir hale gelir; bkz./LTCG.  Profil temelli iyileştirmeler için derleme yaparken ve profil temelli iyileştirmelerinden işlev sıralamasını istiyorsanız, [/GY](gy-enable-function-level-linking.md) veya/gy' ı belirten bir derleyici seçeneğini derlemeniz gerekir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Geliştirme ortamında **/GL** belirtme hakkında bilgi için bkz. [/LTCG (bağlantı zamanı kodu oluşturma)](ltcg-link-time-code-generation.md) .

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
