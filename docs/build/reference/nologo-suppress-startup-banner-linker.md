---
description: Daha fazla bilgi edinin:/NOLOGO (başlangıç başlığını gösterme) (bağlayıcı)
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
ms.openlocfilehash: 48edea691e254f0754d29ab5ea4d8055221c4b69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196561"
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (Başlangıç Başlığını Gösterme) (Bağlayıcı)

```
/NOLOGO
```

## <a name="remarks"></a>Açıklamalar

/NOLOGO seçeneği telif hakkı iletisi ve sürüm numarasını görüntülemeyi önler.

Bu seçenek, komut dosyalarının yankısını de bastırır. Ayrıntılar için bkz. [komut dosyalarını bağlama](linking.md).

Varsayılan olarak, bu bilgiler bağlayıcı tarafından çıkış penceresine gönderilir. Komut satırında, standart çıktıya gönderilir ve bir dosyaya yönlendirilebilir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Bu seçenek yalnızca komut satırından kullanılmalıdır.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bu bağlayıcı seçeneği program aracılığıyla değiştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
