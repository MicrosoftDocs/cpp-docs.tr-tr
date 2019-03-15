---
title: /arch (ARM)
ms.date: 11/04/2016
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
ms.openlocfilehash: b732a74d5fe223fdaf3b161d4ae92093ab5df407
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807877"
---
# <a name="arch-arm"></a>/arch (ARM)

ARM üzerinde kod oluşturma mimarisini belirtir. Ayrıca bkz: [/arch (x86)](arch-x86.md) ve [/arch (x64)](arch-x64.md).

## <a name="syntax"></a>Sözdizimi

```
/arch:[ARMv7VE|VFPv4]
```

## <a name="arguments"></a>Arguments

**/arch:ARMv7VE**<br/>
Sanallaştırma uzantıları ARMv7VE yönergelerinin kullanımını etkinleştirir.

**/arch:VFPv4**<br/>
ARM VFPv4 yönergelerinin kullanımını etkinleştirir. Bu seçenek belirtilmezse, VFPv3 varsayılandır.

## <a name="remarks"></a>Açıklamalar

`_M_ARM_FP` Makrosu (yalnızca ARM için) gösterir, eğer varsa, **/arch** derleyici seçeneği kullanıldı. Daha fazla bilgi için [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

Kullanırken [/CLR](clr-common-language-runtime-compilation.md) derlemek için **/arch** kod oluşturma için yönetilen işlevler üzerinde etkisi yoktur. **/ arch** yalnızca kod oluşturma için yerel işlevleri etkiler.

### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Visual Studio'da /arch:ARMv7VE veya /arch:VFPv4 derleyici seçeneğini ayarlamak için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **C/C++** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler** kutusunda `/arch:ARMv7VE` veya `/arch:VFPv4`.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/arch (En Düşük CPU Mimarisi)](arch-minimum-cpu-architecture.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
