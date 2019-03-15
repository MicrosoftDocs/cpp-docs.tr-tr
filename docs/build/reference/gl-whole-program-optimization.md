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
ms.openlocfilehash: 6251209dac74a504bb0635f0c544c39935090a42
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812388"
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

.obj dosyalarını üretilen ile **/GL** böyle bağlayıcı ölçeklendirebilirlik kullanılabilir olmayacak [EDITBIN](editbin-reference.md) ve [DUMPBIN](dumpbin-reference.md).

Programınızı ile derleme yaparsanız **/GL** ve [/c](c-compile-without-linking.md), çıktı dosyasını oluşturmak için/LTCG bağlayıcı seçeneği kullanmanız gerekir.

[/Zı](z7-zi-zi-debug-information-format.md) kullanılamaz **/GL**

Dosya biçimi ile üretilen **/GL** ' ın geçerli sürümünde Visual C++'ın sonraki sürümleri tarafından okunabilir olmayabilir. İle üretilmiş .obj dosyaları oluşan bir .lib dosyasına sevk etmesi değil **/GL** Visual C++'ın tüm sürümleri için .lib dosyası kopyalarını göndermeye hazır olduğunuz sürece, şimdi ve gelecekte kullanmak üzere kullanıcılarınızın beklediği.

.obj dosyalarını üretilen ile **/GL** ve .lib dosyası üretilen aynı makineye bağlanacak sürece bir .lib dosyası oluşturmak için önceden derlenmiş üst bilgi dosyaları kullanılmamalıdır **/GL** .obj dosyası. Bağlantı zamanında bilgileri .obj dosya önceden derlenmiş üst bilgi dosyası gereklidir.

En iyi duruma getirme ile kullanılabilir ve bütün program iyileştirmesi sınırlamaları hakkında daha fazla bilgi için bkz. [/LTCG](ltcg-link-time-code-generation.md).  **/GL** yapar ayrıca profil destekli iyileştirme kullanılabilir; / LTCG bakın.  En iyi duruma getirme ve sıralama, profil temelli en iyileştirmeler işlevi istiyorsanız profil temelli için derleme yaparken ile derleme [/Gy](gy-enable-function-level-linking.md) veya gelir /Gy derleyici seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Bkz: [/LTCG (bağlama zamanı kodu oluşturma)](ltcg-link-time-code-generation.md) belirtme hakkında daha fazla bilgi için **/GL** geliştirme ortamında.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
