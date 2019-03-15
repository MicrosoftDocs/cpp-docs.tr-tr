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
ms.openlocfilehash: d3c32ba04cbad509ff2819020a35102698d6ceb3
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821345"
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (Gecikme Yükü İçe Aktarma Ayarları)

```
/DELAY:UNLOAD
/DELAY:NOBIND
```

## <a name="remarks"></a>Açıklamalar

/ Delay seçeneği denetimleri [Gecikmeli yükleme](linker-support-for-delay-loaded-dlls.md) DLL'lerin:

- UNLOAD niteleyicisi gecikme yükleme yardımcı işlevine açık DLL'i kaldırma desteklemek için söyler. İçeri aktarma adres tablosu (IAT), özgün formuna IAT işaretçileri geçersiz kılınması ve bunları üzerine yazılmasına neden sıfırlanır.

   UNLOAD belirlemezseniz herhangi çağrısı [FUnloadDelayLoadedDLL](explicitly-unloading-a-delay-loaded-dll.md) başarısız olur.

- NOBIND niteleyicisi bağlayıcıya son görüntüde bağlanabilir IAT eklememesini söyler. Gecikmeli yüklenen DLL'ler için bağlanabilir IAT oluşturmak için varsayılandır. Elde edilen görüntü statik olarak bağlanamaz. (Bağlanabilir IATs görüntülerle yürütme önce statik olarak bağlanabilir.) Bkz: [/bağlama](bind.md).

   DLL bağlıysa yardımcı işlevini çağırmak yerine ilişkili bilgileri kullanmak deneyecek [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) her başvurulan alır. Zaman damgası veya tercih edilen adresi bu yüklenen DLL'nin ile eşleşmiyorsa yardımcı işlevini ilişkili IAT güncel değil ve ilişkili IAT yoksa olarak devam edecek varsayar.

   Programınızı büyük olacak şekilde görüntü ancak hızlandırabilirsiniz NOBIND nedenleri DLL'nin zaman yükleyin. Hiçbir zaman DLL'yi bağlamak istiyorsanız, NOBIND ilişkili IAT oluşturulmasını engeller.

Gecikme yükü DLL'lerini belirtmek için kullanın [/delayload](delayload-delay-load-import.md) seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri**, **bağlayıcı**ve ardından **Gelişmiş**.

1. Değiştirme **Gecikmeli yüklenen DLL'i** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
