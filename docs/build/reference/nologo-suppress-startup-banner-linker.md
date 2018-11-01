---
title: /NOLOGO (Başlangıç Başlığını Gösterme) (Bağlayıcı)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
ms.openlocfilehash: d246da2e10f7c16f7c194962841e2e44d1fd1758
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515550"
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (Başlangıç Başlığını Gösterme) (Bağlayıcı)

```
/NOLOGO
```

## <a name="remarks"></a>Açıklamalar

/ Nologo seçeneği telif hakkı iletisi ve sürüm numarasını görüntülenmesini önler.

Bu seçenek, ayrıca komut dosyaları Yankı bastırır. Ayrıntılar için bkz [LINK komut dosyaları](../../build/reference/link-command-files.md).

Varsayılan olarak, bu bilgiler, çıkış penceresine bağlayıcı tarafından gönderilir. Komut satırında, bunu standart çıktıya gönderilir ve bir dosyaya yönlendirilebilir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Bu seçenek, yalnızca komut satırından kullanılmalıdır.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bu bağlayıcı seçeneğini program aracılığıyla değiştirilemez.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)