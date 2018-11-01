---
title: /GL (Bütün Program İyileştirmesi)
ms.date: 11/04/2016
f1_keywords:
- /gl
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
ms.openlocfilehash: 7e9300c6c851eb013d8304bd90e3ca9aa4b2c022
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640835"
---
# <a name="gl-whole-program-optimization"></a>/GL (Bütün Program İyileştirmesi)

Tüm programın iyileştirilmesini etkinleştirir.

## <a name="syntax"></a>Sözdizimi

```
/GL[-]
```

## <a name="remarks"></a>Açıklamalar

Bütün program iyileştirmesi programdaki tüm modüllerin üzerinde en iyi duruma getirme bilgileriyle gerçekleştirmek derleyicinin sağlar. Bütün program iyileştirmesi en iyi duruma getirme üzerinde gerçekleştirilen bir modül (derlenecek) temelinde.

Bütün program iyileştirmesi, varsayılan olarak kapalıdır ve açıkça etkinleştirilmesi gerekir. Ancak, aynı zamanda ile açıkça devre dışı bırakmak mümkündür **/GL-**.

Tüm modüller hakkında daha fazla bilgi ile derleyici yapabilirsiniz:

- Yazmaçların kullanımı işlevi sınırlarında iyileştirin.

- Daha iyi iş yükleri ve depoları sayısını azaltma izin vererek, genel veri değişiklikleri izleme yapın.

- Olası bir işaretçi tarafından değiştirilen öğeleri kümesini başvuru, yükler ve depoları sayısı azaltma izleme konusunda daha iyi iş yapın.

- Satır içi işlevi başka bir modül tanımlandığında bile bir modüldeki bir işlev.

.obj dosyalarını üretilen ile **/GL** böyle bağlayıcı ölçeklendirebilirlik kullanılabilir olmayacak [EDITBIN](../../build/reference/editbin-reference.md) ve [DUMPBIN](../../build/reference/dumpbin-reference.md).

Programınızı ile derleme yaparsanız **/GL** ve [/c](../../build/reference/c-compile-without-linking.md), çıktı dosyasını oluşturmak için/LTCG bağlayıcı seçeneği kullanmanız gerekir.

[/Zı](../../build/reference/z7-zi-zi-debug-information-format.md) kullanılamaz **/GL**

Dosya biçimi ile üretilen **/GL** ' ın geçerli sürümünde Visual C++'ın sonraki sürümleri tarafından okunabilir olmayabilir. İle üretilmiş .obj dosyaları oluşan bir .lib dosyasına sevk etmesi değil **/GL** Visual C++'ın tüm sürümleri için .lib dosyası kopyalarını göndermeye hazır olduğunuz sürece, şimdi ve gelecekte kullanmak üzere kullanıcılarınızın beklediği.

.obj dosyalarını üretilen ile **/GL** ve .lib dosyası üretilen aynı makineye bağlanacak sürece bir .lib dosyası oluşturmak için önceden derlenmiş üst bilgi dosyaları kullanılmamalıdır **/GL** .obj dosyası. Bağlantı zamanında bilgileri .obj dosya önceden derlenmiş üst bilgi dosyası gereklidir.

En iyi duruma getirme ile kullanılabilir ve bütün program iyileştirmesi sınırlamaları hakkında daha fazla bilgi için bkz. [/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  **/GL** yapar ayrıca profil destekli iyileştirme kullanılabilir; / LTCG bakın.  En iyi duruma getirme ve sıralama, profil temelli en iyileştirmeler işlevi istiyorsanız profil temelli için derleme yaparken ile derleme [/Gy](../../build/reference/gy-enable-function-level-linking.md) veya gelir /Gy derleyici seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Bkz: [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md) belirtme hakkında daha fazla bilgi için **/GL** geliştirme ortamında.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)