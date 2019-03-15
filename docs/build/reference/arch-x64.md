---
title: /arch (x64)
ms.date: 11/04/2016
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
ms.openlocfilehash: c515307ee3a49ef746eea939e90d7aecbd661b95
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809320"
---
# <a name="arch-x64"></a>/arch (x64)

X64 kod oluşturma mimarisini belirtir. Ayrıca bkz: [/arch (x86)](arch-x86.md) ve [/arch (ARM)](arch-arm.md).

## <a name="syntax"></a>Sözdizimi

```
/arch:[AVX|AVX2]
```

## <a name="arguments"></a>Arguments

**/ arch:**<br/>
Intel Gelişmiş vektör uzantıları yönergelerinin kullanımını etkinleştirir.

**/arch:AVX2**<br/>
Intel Gelişmiş vektör uzantıları 2 yönergeleri kullanımını etkinleştirir.

## <a name="remarks"></a>Açıklamalar

**/ arch** yalnızca kod oluşturma için yerel işlevleri etkiler. Kullanırken [/CLR](clr-common-language-runtime-compilation.md) derlemek için **/arch** kod oluşturma için yönetilen işlevler üzerinde etkisi yoktur.

`__AVX__` Önişlemci sembolü tanımlı olduğunda **/arch:** derleyici seçeneği belirtildi. `__AVX2__` Önişlemci sembolü tanımlı olduğunda **/arch:AVX2** derleyici seçeneği belirtildi. Daha fazla bilgi için [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md). **/Arch:AVX2** seçeneği, Visual Studio 2013 Update 2 ', sürüm 12.0.34567.1 tanıtılmıştır.

### <a name="to-set-the-archavx-or-archavx2-compiler-option-in-visual-studio"></a>Visual Studio'da / arch: veya /arch:AVX2 derleyici seçeneğini ayarlamak için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri**, **C/C++** klasör.

1. Seçin **kod oluşturma** özellik sayfası.

1. İçinde **etkinleştirme gelişmiş yönerge kümesi** açılan kutusunda **Gelişmiş vektör Uzantıları (/ arch: AVX)** veya **Gelişmiş vektör uzantıları 2 (/ arch: AVX2)**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/arch (En Düşük CPU Mimarisi)](arch-minimum-cpu-architecture.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
