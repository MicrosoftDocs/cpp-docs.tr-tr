---
description: Daha fazla bilgi edinin:/MACHINE (hedef platformu belirt)
title: /MACHINE (Hedef Platformu Belirt)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TargetMachine
- /machine
helpviewer_keywords:
- mapfiles, creating linker
- target platform
- -MACHINE linker option
- /MACHINE linker option
- MACHINE linker option
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
ms.openlocfilehash: a1bf87142fb99577672391356a43a2771ea0b09f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190815"
---
# <a name="machine-specify-target-platform"></a>/MACHINE (Hedef Platformu Belirt)

```
/MACHINE:{ARM|EBC|X64|X86}
```

## <a name="remarks"></a>Açıklamalar

/MACHıNE seçeneği program için hedef platformu belirtir.

Genellikle/MACHINE seçeneğini belirtmeniz gerekmez. BAĞLANTı,. obj dosyalarından makine türünü de haller. Ancak, bazı durumlarda bağlantı makine türünü belirleyemez ve [bağlayıcı araçları hatası LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md)yayınlar. Böyle bir hata oluşursa,/MACHINEBELIRTIN.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Gelişmiş** Özellik sayfasına tıklayın.

1. **Hedef makine** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
