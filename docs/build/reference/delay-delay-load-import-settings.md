---
title: -DELAY (gecikme yükü içe aktarma ayarları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /delay
- VC.Project.VCLinkerTool.DelayNoBind
- VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL
- VC.Project.VCLinkerTool.DelayUnload
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, /DELAY option
- DELAY linker option
- /DELAY linker option
- -DELAY linker option
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ce585f9dc8439a02a2883229e8d9ec006c29c24
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717697"
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (Gecikme Yükü İçe Aktarma Ayarları)

```
/DELAY:UNLOAD
/DELAY:NOBIND
```

## <a name="remarks"></a>Açıklamalar

/ Delay seçeneği denetimleri [Gecikmeli yükleme](../../build/reference/linker-support-for-delay-loaded-dlls.md) DLL'lerin:

- UNLOAD niteleyicisi gecikme yükleme yardımcı işlevine açık DLL'i kaldırma desteklemek için söyler. İçeri aktarma adres tablosu (IAT), özgün formuna IAT işaretçileri geçersiz kılınması ve bunları üzerine yazılmasına neden sıfırlanır.

   UNLOAD belirlemezseniz herhangi çağrısı [FUnloadDelayLoadedDLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md) başarısız olur.

- NOBIND niteleyicisi bağlayıcıya son görüntüde bağlanabilir IAT eklememesini söyler. Gecikmeli yüklenen DLL'ler için bağlanabilir IAT oluşturmak için varsayılandır. Elde edilen görüntü statik olarak bağlanamaz. (Bağlanabilir IATs görüntülerle yürütme önce statik olarak bağlanabilir.) Bkz: [/bağlama](../../build/reference/bind.md).

   DLL bağlıysa yardımcı işlevini çağırmak yerine ilişkili bilgileri kullanmak deneyecek [GetProcAddress](https://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) her başvurulan alır. Zaman damgası veya tercih edilen adresi bu yüklenen DLL'nin ile eşleşmiyorsa yardımcı işlevini ilişkili IAT güncel değil ve ilişkili IAT yoksa olarak devam edecek varsayar.

   Programınızı büyük olacak şekilde görüntü ancak hızlandırabilirsiniz NOBIND nedenleri DLL'nin zaman yükleyin. Hiçbir zaman DLL'yi bağlamak istiyorsanız, NOBIND ilişkili IAT oluşturulmasını engeller.

Gecikme yükü DLL'lerini belirtmek için kullanın [/delayload](../../build/reference/delayload-delay-load-import.md) seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri**, **bağlayıcı**ve ardından **Gelişmiş**.

1. Değiştirme **Gecikmeli yüklenen DLL'i** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)