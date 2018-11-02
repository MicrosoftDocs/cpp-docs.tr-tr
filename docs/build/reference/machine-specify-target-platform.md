---
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
ms.openlocfilehash: 872370269e9ab8acaaa8cafe7fb47b1121bcbb97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546449"
---
# <a name="machine-specify-target-platform"></a>/MACHINE (Hedef Platformu Belirt)

```
/MACHINE:{ARM|EBC|X64|X86}
```

## <a name="remarks"></a>Açıklamalar

/ MACHINE seçeneği program için hedef platformu belirtir.

Genellikle, / MACHINE seçeneği belirtmeniz gerekmez. BAĞLANTI .obj dosyaları makine türünden çıkarır. Ancak, bazı durumlarda, bağlantı sorunları ve makine türü belirlenemiyor bir [Bağlayıcı araçları hatası LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md). Böyle bir hata oluşursa/Machine belirtin.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **hedef makine** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)