---
title: -arch (ARM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 17f0f0735981c0a851bcab62ca1ad39c97af3965
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700691"
---
# <a name="arch-arm"></a>/arch (ARM)

ARM üzerinde kod oluşturma mimarisini belirtir. Ayrıca bkz: [/arch (x86)](../../build/reference/arch-x86.md) ve [/arch (x64)](../../build/reference/arch-x64.md).

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

Kullanırken [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) derlemek için **/arch** kod oluşturma için yönetilen işlevler üzerinde etkisi yoktur. **/ arch** yalnızca kod oluşturma için yerel işlevleri etkiler.

### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Visual Studio'da /arch:ARMv7VE veya /arch:VFPv4 derleyici seçeneğini ayarlamak için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **C/C++** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler** kutusunda `/arch:ARMv7VE` veya `/arch:VFPv4`.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/ arch (en düşük CPU Mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)