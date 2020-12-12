---
description: Daha fazla bilgi edinin:/Arch (ARM)
title: /arch (ARM)
ms.date: 11/04/2016
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
ms.openlocfilehash: 885b624eb6a470d24d691641d0be63515ee76a49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179570"
---
# <a name="arch-arm"></a>/arch (ARM)

ARM 'de kod oluşturma mimarisini belirtir. Ayrıca bkz. [/Arch (x86)](arch-x86.md) ve [/Arch (x64)](arch-x64.md).

## <a name="syntax"></a>Söz dizimi

```
/arch:[ARMv7VE|VFPv4]
```

## <a name="arguments"></a>Bağımsız değişkenler

**/Arch: ARMv7VE**<br/>
ARMv7VE sanallaştırma uzantıları yönergelerinin kullanımını mümkün.

**/Arch: VFPv4**<br/>
ARM VFPv4 yönergelerinin kullanımına izin vermez. Bu seçenek belirtilmezse, VFPv3 varsayılandır.

## <a name="remarks"></a>Açıklamalar

`_M_ARM_FP`Makro (yalnızca ARM için), varsa **/Arch** derleyici seçeneğinin kullanıldığını gösterir. Daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

Derlemek için [/clr](clr-common-language-runtime-compilation.md) kullandığınızda, **/Arch** yönetilen işlevler için kod üretimi üzerinde hiçbir etkiye sahip değildir. **/Arch** yalnızca yerel işlevler için kod oluşturmayı etkiler.

### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Visual Studio 'da/Arch: ARMv7VE veya/Arch: VFPv4 derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü seçin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusunda, `/arch:ARMv7VE` veya ekleyin `/arch:VFPv4` .

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Arch (en düşük CPU mimarisi)](arch-minimum-cpu-architecture.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
