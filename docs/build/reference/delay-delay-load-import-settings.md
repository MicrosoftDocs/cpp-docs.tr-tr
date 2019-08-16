---
title: /DELAY (Gecikme Yükü İçe Aktarma Ayarları)
ms.date: 11/04/2016
f1_keywords:
- /delay
- VC.Project.VCLinkerTool.DelayNoBind
- VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL
- VC.Project.VCLinkerTool.DelayUnload
helpviewer_keywords:
- delayed loading of DLLs, /DELAY option
- DELAY linker option
- /DELAY linker option
- -DELAY linker option
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
ms.openlocfilehash: ef6f5f768cf86f470d1322fa2a7bee6db794c2ef
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493002"
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (Gecikme Yükü İçe Aktarma Ayarları)

```
/DELAY:UNLOAD
/DELAY:NOBIND
```

## <a name="remarks"></a>Açıklamalar

/DELAY seçeneği, dll 'lerin [gecikmeli yüklenmesini](linker-support-for-delay-loaded-dlls.md) denetler:

- KALDıRMA niteleyicisi, gecikme Yükleme Yardımcısı işlevine DLL 'nin açıkça kaldırılmasını desteklememesini söyler. Içeri aktarma adres tablosu (ıAT) orijinal biçimine sıfırlanır, ıAT işaretçilerine geçersiz kılınır ve üzerine yazılmasına neden olur.

   Kaldır ' ı seçmezseniz, [FUnloadDelayLoadedDLL](explicitly-unloading-a-delay-loaded-dll.md) çağrısı başarısız olur.

- NOBIND niteleyicisi, bağlayıcının son görüntüde bağlanabilir bir ıAT içermeyeceğini söyler. Varsayılan olarak, Gecikmeli yüklenen dll 'Ler için bağlanabilir ıAT oluşturulur. Elde edilen görüntü, statik olarak bağlanamaz. (Bağlanabilir IATS içeren görüntüler, yürütmeden önce statik olarak bağlanabilir.) Bkz. [/bind](bind.md).

   DLL bağlı ise yardımcı işlevi, başvurulan içeri aktarmaların her birinde [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) çağırmak yerine bağlı bilgileri kullanmayı dener. Zaman damgası ya da tercih edilen adres, yüklenen DLL 'nin olanlarla eşleşmezse, yardımcı işlev, ıAT 'nın, o 'nun güncel olmadığını varsayar ve BAĞLANıAT yok gibi devam eder.

   NOBIND, program görüntünüzün daha büyük olmasına neden olur, ancak DLL yükleme süresini hızlandırabilir. DLL 'yi bağlamayı hiç düşünmüyorsanız, NOBIND bağlı ıAT 'in oluşturulmasını engeller.

Yük gecikmesi olacak dll 'Leri belirtmek için [/delayload](delayload-delay-load-import.md) seçeneğini kullanın.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Bilgi için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**' ni ve **bağlayıcı**' yı genişletin ve **Gelişmiş**' i seçin.

1. **Yüklenen dll 'Yi geciktir** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
