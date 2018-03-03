---
title: "-errorReport (dahili derleme hatalarını raporla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
- /errorreport
dev_langs:
- C++
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b34df09ca53441789fc90061748ad591149d6b2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport (Dahili Derleme Hatalarını Raporla)
Doğrudan Microsoft'a iç derleyici hatası (çok) bilgileri sağlamanıza olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## <a name="arguments"></a>Arguments  
 **yok**  
 İç derleyici hataları hakkında raporlar değil toplanmayacak veya Microsoft'a gönderilir.  
  
 **istemi**  
 Derleyici iç hatası aldığınızda, bir raporu göndermek isteyip istemediğinizi sorar. **İstemi** bir uygulama geliştirme ortamında derlendiğinde varsayılandır.  
  
 **sırası**  
 Hata raporu sıralar. Yönetici ayrıcalıklarıyla oturum kapatışınızda oturum en son ne zaman bu yana hataları rapor için bir pencere görüntülenir (üç günde birden çok kez hata raporu göndermek için istenir değildir). **sıra** uygulamanın bir komut isteminde derlendiğinde varsayılandır.  
  
 **Gönder**  
 Otomatik olarak raporlama tarafından Windows hata bildirimi sistem ayarları etkinse, iç derleyici hata raporlarını Microsoft'a gönderir.  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak kodu dosyasının derleyici işleyemediğinde iç derleyici hatası (çok) sonuçlanır. Bir çok oluştuğunda derleyici çıktı dosyası ya da kodunuzu düzeltmek için kullanabileceğiniz herhangi bir kullanışlı tanılama üretmez.  
  
 Bir çok aldığınız zaman önceki sürümlerde, sorunu bildirmek için Microsoft Ürün Destek Hizmetleri'ne çağırmak için önerilir. İle **/errorreport**, doğrudan Microsoft'a çok bilgi sağlayabilir. Hata raporlarını gelecek derleyici sürümler artırmaya yardımcı olabilir.  
  
 Bir kullanıcının, raporları göndermek becerisini bilgisayar ve kullanıcı ilkesi izinlerine bağlıdır.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **hata raporlama** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)