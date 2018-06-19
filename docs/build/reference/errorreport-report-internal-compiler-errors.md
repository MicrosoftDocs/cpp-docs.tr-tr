---
title: -errorReport (dahili derleme hatalarını raporla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
- /errorreport
dev_langs:
- C++
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67e87143d31de98039f5d679c102a5815dd87abb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377254"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport (Dahili Derleme Hatalarını Raporla)
Doğrudan Microsoft'a iç derleyici hatası (çok) bilgileri sağlamanıza olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## <a name="arguments"></a>Arguments  
 **Yok**  
 İç derleyici hataları hakkında raporlar değil toplanmayacak veya Microsoft'a gönderilir.  
  
 **istemi**  
 Derleyici iç hatası aldığınızda, bir raporu göndermek isteyip istemediğinizi sorar. **İstemi** bir uygulama geliştirme ortamında derlendiğinde varsayılandır.  
  
 **Sırası**  
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