---
title: "Gelişmiş Özellikler, MFC Uygulama Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.exe.advanced
dev_langs: C++
helpviewer_keywords: MFC Application Wizard, advanced features
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 957894b69953f9b2c596f61cd0004c47c6d6e1cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="advanced-features-mfc-application-wizard"></a>Gelişmiş Özellikler, MFC Uygulama Sihirbazı
Bu başlıkta; uygulamanıza yönelik, Yardım, yazdırma desteği vb. gibi ek özelliklerin seçenekleri listelenmiştir. Her bölümde, bu gelişmiş özelliklere yönelik ek destek belirtin.  
  
 **Bağlama duyarlı Yardım (HTML)**  
 F1'e ve Yardım menüsünü kullanarak veya tıklatarak kullanılabilen bağlama duyarlı Yardım için Yardım dosyaları kümesi oluşturur bir **yardımcı** bir iletişim kutusu düğmesinde. Yardım desteği yardım derleyicisi gerektirir. Yardım derleyicisini yüklemediyseniz, Kur'u yeniden çalıştırarak yükleyebilirsiniz.  
  
 Bkz: [HTML Yardımı: Context-Sensitive yardımcı olmak için programlarınızı](../../mfc/html-help-context-sensitive-help-for-your-programs.md) ve [Yardım dosyaları (HTML Yardım)](../../ide/help-files-html-help.md) daha fazla bilgi için.  
  
 **Yazdırmayı ve Baskı Önizleme**  
 Yazdırma işlemek, üye işlevlerini çağırma tarafından yazdırma Kurulum ve Baskı Önizleme komutları için kod oluşturur [CView sınıfı](../../mfc/reference/cview-class.md) MFC Kitaplığı. Ayrıca, sihirbaz, bu işlevlerin komutlarını uygulamanın menüsüne ekler. Yazdırma desteği belirttiğiniz uygulamalar için kullanılabilir **belge/görünüm mimarisi desteği** içinde [uygulama türü, MFC Uygulama Sihirbazı'nı](../../mfc/reference/application-type-mfc-application-wizard.md) Sihirbazı sayfası. Varsayılan olarak, belge/görünüm uygulamaları yazdırma desteğine sahiptir.  
  
 **Otomasyon**  
 Uygulamanın başka bir uygulamada yerleştirilen nesneleri işleyebileceğini belirtir ya da uygulamayı otomasyon istemcilerine açık hale getirir.  
  
 **ActiveX denetimleri**  
 ActiveX denetimlerini (varsayılan) destekler. Değil Bu seçeneği seçin ve daha sonra ActiveX denetimlerini projenize eklemek istediğiniz bir çağrı ekleyin [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) , uygulamanızın içinde [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) üyesi işlev.  
  
 **MAPI (İleti API)**  
 Uygulamanın e-posta iletilerini oluşturabileceğini, kullanabileceğini, aktarabileceğini ve depolayabileceğini belirtir.  
  
 **Windows Yuvaları**  
 TCP/IP ağları üzerinden iletişim kuran uygulamaları yazmak için kullanabileceğiniz Windows yuvalarını destekler.  
  
 **Etkin Erişilebilirlik**  
 İçin destek ekler [IAccessible](http://msdn.microsoft.com/library/windows/desktop/dd318466) için [CWnd](../../mfc/reference/cwnd-class.md)-türetilmiş erişilebilirlik istemcileri ile daha iyi etkileşim için kullanıcı arabirimini özelleştirmek için kullanabileceğiniz sınıfları.  
  
 **Ortak denetim bildirimi**  
 Varsayılan olarak etkindir. Microsoft Windows XP ve daha yeni işletim sistemleri ile birlikte gelen, Ortak Denetim DLL'sini etkinleştirmek üzere bir uygulama bildirimi oluşturur.  
  
 Ortak Denetim DLL 6 sürümü, varolan uygulamalarınızın kullandığı Ortak Denetimlerin önceki sürümünü otomatik olarak güncelleştirmez. Ortak Denetim DLL 6 sürümünü kullanmak için, uygulamanızı DLL'yi yüklemeye yönlendiren bir uygulama bildirimi oluşturmanız gerekir. Bu Ortak Denetim DLL Windows XP temalarını da destekler.  
  
 Bir uygulama bildirimi, diğer DLL'leri ve uygulamanızın ihtiyaç duyduğu sürümleri de belirtebilir. Uygulama bildirimleri hakkında daha fazla bilgi için bkz: [yalıtılmış uygulamalar ve yan yana derlemeler](http://msdn.microsoft.com/library/dd408052) Windows SDK'sındaki.  
  
 **Destek yeniden başlatma Yöneticisi**  
 İçin destek ekler [Windows yeniden başlatma Yöneticisi](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx). Bu videoda yeniden başlatma Yöneticisi'nden MFC kullanmayı gösterir: [I: kullanma yeni yeniden başlatma Yöneticisi](http://msdn.microsoft.com/vstudio/ee886407).  
  
 **Gelişmiş çerçeve bölmeleri**  
 |Seçenek|Açıklama|  
|------------|-----------------|  
|**Explorer takma bölmesi**|Visual Studio benzer bir takma bölmesini oluşturur **Çözüm Gezgini** ana çerçeve penceresi solundaki.|  
|**Çıktı takma çerçeve**|Visual Studio benzer bir takma bölmesini oluşturur **çıkış** ana çerçeve penceresi altında bulunan bölmesi.|  
|**Özellikler bölmesinde yerleştirme**|Visual Studio benzer bir takma bölmesini oluşturur **özellikleri** ana çerçeve penceresinin sağ bölmesinde.|  
|**Gezinti Bölmesi**|Outlook gezinti çubuğuna benzer ve ana çerçeve penceresinin sol tarafında bulunan bir yerleştirme bölmesi oluşturur.|  
|**Başlık çubuğu**|Ana çerçeve penceresinin üzerinde, Office stili bir başlık çubuğu oluşturur.|  
  
 **Son kullanılan dosya listesi dosya sayısı**  
 En son kullanılan listesinde listelenen dosyaların sayısını belirtir. Varsayılan sayı 4'tür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)

