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
ms.openlocfilehash: c898727504a8ae530bcdffb3e01bde68c31c8e87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (Gecikme Yükü İçe Aktarma Ayarları)
```  
/DELAY:UNLOAD  
/DELAY:NOBIND  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / Delay seçeneği denetimleri [Gecikmeli yüklemesi](../../build/reference/linker-support-for-delay-loaded-dlls.md) dll:  
  
-   UNLOAD niteleyici DLL'i açıkça kaldırma desteklemek için gecikme yükü yardımcı işlevini söyler. Alma Adresi Tablosu'nda (IAT) özgün formuna, IAT işaretçileri geçersiz kılınması ve bunları üzerine yazılmasına neden sıfırlanır.  
  
     UNLOAD seçmezseniz herhangi çağrısı [FUnloadDelayLoadedDLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md) başarısız olur.  
  
-   NOBIND niteleyicisi bağlanabilirse IAT son görüntüde içermeyecek şekilde bağlayıcı söyler. Gecikmeli yüklenen DLL'ler için bağlanabilirse IAT oluşturmak için varsayılandır. Elde edilen görüntü statik olarak bağlanamaz. (Bağlanabilirse IATs görüntülerle statik olarak yürütme önce bağlanmış olabilir.) Bkz: [/bağlama](../../build/reference/bind.md).  
  
     DLL bağlıysa yardımcı işlevini ilişkili bilgi arama yerine kullanmayı dener [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) her başvurulan alır. Zaman damgası veya tercih edilen adres olanlar yüklenen DLL'nin eşleşmiyorsa, yardımcı işlevini ilişkili IAT güncel değil ve ilişkili IAT yoksa olarak devam edecek varsayar.  
  
     Yükleme süresi dll programınızı büyük olacak şekilde görüntü ancak hızlandırabilir NOBIND neden olur. Hiçbir zaman DLL bağlamak istiyorsanız, NOBIND oluşturulmasını önler ilişkili IAT engeller.  
  
 Gecikme yükü DLL'lerini belirtmek için kullanın [/DELAYLOAD](../../build/reference/delayload-delay-load-import.md) seçeneği.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri**, **bağlayıcı**ve ardından **Gelişmiş**.  
  
3.  Değiştirme **Gecikmeli yüklenen DLL'i** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)