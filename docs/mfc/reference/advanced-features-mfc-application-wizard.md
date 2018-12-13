---
title: Gelişmiş Özellikler, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.advanced
helpviewer_keywords:
- MFC Application Wizard, advanced features
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
ms.openlocfilehash: 1af16f7009ceb97ea86d641f47cf56ea5a398c26
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694302"
---
# <a name="advanced-features-mfc-application-wizard"></a>Gelişmiş Özellikler, MFC Uygulama Sihirbazı

Bu başlıkta; uygulamanıza yönelik, Yardım, yazdırma desteği vb. gibi ek özelliklerin seçenekleri listelenmiştir. Her bölümde, bu gelişmiş özelliklere yönelik ek destek belirtin.

- **Bağlama duyarlı Yardım (HTML)**

   Bağlama duyarlı Yardım için F1 ve Yardım menüsünü kullanarak veya tıklayarak kullanılabilir Yardım dosyaları kümesi üretir bir **yardımcı** bir iletişim kutusu düğmesine. Yardım desteği yardım derleyicisi gerektirir. Yardım derleyicisini yüklemediyseniz, Kur'u yeniden çalıştırarak yükleyebilirsiniz.

   Bkz: [HTML Yardımı: Programlarınız için Bağlama Duyarlı Yardım](../../mfc/html-help-context-sensitive-help-for-your-programs.md) ve [Yardım dosyaları (HTML Yardım)](../../ide/help-files-html-help.md) daha fazla bilgi için.

- **Yazdırmayı ve Baskı Önizleme**

   Üye işlevlerini çağırarak Yazdırma Kurulumu ve yazdırma önizleme komutlarını, yazdırma işlemek için kod oluşturur [CView sınıfı](../../mfc/reference/cview-class.md) MFC Kitaplığı'ndan. Ayrıca, sihirbaz, bu işlevlerin komutlarını uygulamanın menüsüne ekler. Yazdırma desteği yalnızca belirttiğiniz uygulamalar için kullanılabilir **belge/görünüm mimarisi desteği** içinde [Application Type, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md) Sihirbazı sayfası. Varsayılan olarak, belge/görünüm uygulamaları yazdırma desteğine sahiptir.

- **Otomatikleştirme**

   Uygulamanın başka bir uygulamada yerleştirilen nesneleri işleyebileceğini belirtir ya da uygulamayı otomasyon istemcilerine açık hale getirir.

- **ActiveX denetimleri**

   ActiveX denetimlerini (varsayılan) destekler. Bu seçeneği etmez ve daha sonra ActiveX denetimlerini projenize eklemek istiyorsanız, bir çağrı ekleyin [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) uygulamanızın [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) üyesi işlev.

- **MAPI (Messaging API)**

   Uygulamanın e-posta iletilerini oluşturabileceğini, kullanabileceğini, aktarabileceğini ve depolayabileceğini belirtir.

- **Windows Yuvaları**

   TCP/IP ağları üzerinden iletişim kuran uygulamaları yazmak için kullanabileceğiniz Windows yuvalarını destekler.

- **Etkin Erişilebilirlik**

   İçin destek ekler [IAccessible](/windows/desktop/api/oleacc/nn-oleacc-iaccessible) için [CWnd](../../mfc/reference/cwnd-class.md)-türetilmiş sınıflar, daha iyi Etkin Erişilebilirlik istemcileri için kullanıcı arabirimini özelleştirmek için kullanabilirsiniz.

- **Ortak denetim bildirimi**

   Varsayılan olarak etkindir. Microsoft Windows XP ve daha yeni işletim sistemleri ile birlikte gelen, Ortak Denetim DLL'sini etkinleştirmek üzere bir uygulama bildirimi oluşturur.

   Ortak Denetim DLL 6 sürümü, varolan uygulamalarınızın kullandığı Ortak Denetimlerin önceki sürümünü otomatik olarak güncelleştirmez. Ortak Denetim DLL 6 sürümünü kullanmak için, uygulamanızı DLL'yi yüklemeye yönlendiren bir uygulama bildirimi oluşturmanız gerekir. Bu Ortak Denetim DLL Windows XP temalarını da destekler.

   Bir uygulama bildirimi, diğer DLL'leri ve uygulamanızın ihtiyaç duyduğu sürümleri de belirtebilir. Uygulama bildirimleri hakkında daha fazla bilgi için bkz: [yalıtılmış uygulamalar ve yan yana derlemeler](/windows/desktop/SbsCs/isolated-applications-and-side-by-side-assemblies-portal) Windows SDK.

- **Yeniden başlatma Yöneticisi desteği**

   İçin destek ekler [Windows yeniden başlatma Yöneticisi](/windows/desktop/RstMgr/using-restart-manager). Bu videoda, MFC'den yeniden başlatma Yöneticisi işlemi gösterilir: [nasıl: kullanma yeni yeniden başlatma Yöneticisi](/previous-versions/visualstudio/visual-studio-2010/dd831853(v%3dvs.100)).

- **Gelişmiş çerçeve bölmeleri**

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Gezgin yerleştirme bölmesi**|Visual Studio benzeri bir yerleştirme bölmesi oluşturur **Çözüm Gezgini** ana çerçeve penceresinin sol.|
   |**Çıktı yerleştirme çerçevesi**|Visual Studio benzeri bir yerleştirme bölmesi oluşturur **çıkış** ana çerçeve penceresinin bölmesi.|
   |**Özellikler yerleştirme bölmesi**|Visual Studio benzeri bir yerleştirme bölmesi oluşturur **özellikleri** ana çerçeve penceresinin sağ bölmesindeki.|
   |**Gezinti Bölmesi**|Outlook gezinti çubuğuna benzer ve ana çerçeve penceresinin sol tarafında bulunan bir yerleştirme bölmesi oluşturur.|
   |**Başlık çubuğu**|Ana çerçeve penceresinin üzerinde, Office stili bir başlık çubuğu oluşturur.|

- **Son kullanılan dosya listesindeki dosya sayısı**

   En son kullanılan listesinde listelenen dosyaların sayısını belirtir. Varsayılan sayı 4'tür.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)

