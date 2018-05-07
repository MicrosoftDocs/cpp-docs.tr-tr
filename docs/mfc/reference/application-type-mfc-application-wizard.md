---
title: Uygulama türü, MFC Uygulama Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.apptype
dev_langs:
- C++
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5708e823c57ecdb8470a398c4192cba1a5b6e411
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="application-type-mfc-application-wizard"></a>Uygulama Türü, MFC Uygulama Sihirbazı
Bu sayfanın kullanmak [MFC Uygulama Sihirbazı'nı](../../mfc/reference/mfc-application-wizard.md) tasarımı ve yeni bir MFC uygulaması için temel özellikleri ekleyin.  
  
 **Uygulama türü**  
 Uygulamanızı oluşturmak istediğiniz belge desteği türünü belirtir. Seçtiğiniz uygulama türüne, uygulamanız için kullanılabilen kullanıcı arabirimi seçenekleri belirler. Bkz: [kullanıcı arabirimi özellikleri, MFC Uygulama Sihirbazı'nı](../../mfc/reference/user-interface-features-mfc-application-wizard.md) daha fazla bilgi için.  
  
 Belge türleri hakkında daha fazla bilgi için bkz:  
  
-   [SDI ve MDI](../../mfc/sdi-and-mdi.md)  
  
-   [Çerçeve Pencereleri](../../mfc/frame-windows.md)  
  
-   [Çerçeve Penceresi Sınıfları](../../mfc/frame-window-classes.md)  
  
-   [Belgeler, Görünümler ve Çerçeve](../../mfc/documents-views-and-the-framework.md)  
  
-   [İletişim Kutuları](../../mfc/dialog-boxes.md)  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Tek belge**|Burada bir görünüm sınıfı temel uygulamanız için bir tek belge arabirimi (SDI) mimarisini oluşturur [CView sınıfı](../../mfc/reference/cview-class.md). Görünüm için temel sınıfı değiştirebilirsiniz [oluşturulan sınıflar, MFC Uygulama Sihirbazı'nı](../../mfc/reference/generated-classes-mfc-application-wizard.md) Sihirbazı sayfası. Örneğin, form tabanlı bir uygulama oluşturmak için kullanın [Cformview'yu sınıfı](../../mfc/reference/cformview-class.md) görünüm sınıfı için.<br /><br /> İçinde bu tür bir uygulama, yalnızca tek bir belgenin belge çerçeve penceresi tutabilir.|  
|**Birden çok belge**|Burada bir görünüm sınıfı dayanır, uygulamanız için bir birden çok belge arabirimi (MDI) mimarisi oluşturur `CView`. Görünüm için temel sınıfı değiştirebilirsiniz **oluşturulan sınıflar** Sihirbazı sayfası. Örneğin, form tabanlı bir uygulama oluşturmak için kullanın `CFormView` görünüm sınıfı için.<br /><br /> İçinde bu tür bir uygulama, windows birden çok alt belge çerçeve penceresi basılı tutabilirsiniz.|  
|**Sekmeli belgeler**|Her bir belgenin ayrı bir sekmede yerleştirir.|  
|**Temel iletişim**|Burada bir iletişim kutusu sınıfı dayanır, uygulamanız için iletişim tabanlı bir mimari oluşturur `CDialog`. (Bir HTML iletişim kutusu oluşturmak için kutusunu **kullanım HTML iletişim**.)|  
|**HTML iletişim kutusunu kullanın**|İletişim kutusu için yalnızca uygulamaları. İletişim sınıfından türetilen [CDHtmlDialog sınıfı](../../mfc/reference/cdhtmldialog-class.md) yerine [CDialog sınıfı](../../mfc/reference/cdialog-class.md). Bu kutuyu işaretlerseniz `CDHtmlDialog` içinde listelenen **temel sınıfı** kutusunda [oluşturulan sınıflar, MFC Uygulama Sihirbazı'nı](../../mfc/reference/generated-classes-mfc-application-wizard.md) Sihirbazı sayfası.<br /><br /> A `CDHtmlDialog`-türetilen iletişim kutusu görüntüler HTML tabanlı iletişim kutuları, HTML alışverişleri verilerle denetler ve HTML olayları işler.|  
|**Birden çok üst düzey belgeleri**|Burada bir görünüm sınıfı dayanır, uygulamanız için birden çok üst düzey bir mimari oluşturur `CView`.<br /><br /> Bu tür bir uygulama, bir kullanıcı tıkladığında **yeni** (veya **yeni çerçeve**) üzerinde **dosya** menüsünde, uygulama, üst örtük olarak masaüstü bir penceresini oluşturur. Yeni belge çerçeve görev çubuğunda görünür ve uygulama penceresinin istemci alanını sınırlı değil.|  
  
 **Belge/görünüm mimarisi desteği**  
 Belge/görünüm mimarisi kullanarak, uygulamanızda dahil edilip edilmeyeceğini belirtir [CDocument sınıfı](../../mfc/reference/cdocument-class.md) ve [CView sınıfı](../../mfc/reference/cview-class.md) (varsayılan). MFC dışı uygulama bağlantı noktası oluşturma veya derlenmiş yürütülebilir dosyanın boyutunu küçültmek istiyorsanız bu onay kutusunu temizleyin. Varsayılan olarak, bir uygulama belge/görünüm mimarisinin olmadan türetildiği [CWinApp sınıfı](../../mfc/reference/cwinapp-class.md), ve bir disk dosyasından bir belgeyi açmak için MFC desteği içermez.  
  
 **Kaynak dili**  
 Kaynaklarınızın dili ayarlar. Kullanılabilir diller, sisteminizde yüklü Visual Studio tarafından olarak görüntüler. Sistem diliniz dışında bir dil seçmek istiyorsanız, o dil için uygun şablon klasör zaten yüklü olmalıdır. Türkçe kaynaklar kullanılabilir varsayılandan farklı yükleme hakkında daha fazla bilgi için **kaynak dili** listesinde, bkz: [diğer diller için sihirbaz desteği](../../ide/wizard-support-for-other-languages.md).  
  
 Seçtiğiniz dil yansıtılmıştır **dizeleri yerelleştirilmiş** seçeneği [belge şablonu dizeleri, MFC Uygulama Sihirbazı'nı](../../mfc/reference/document-template-strings-mfc-application-wizard.md) Sihirbazı sayfası.  
  
 **Unicode kitaplıkları kullanma**  
 MFC kitaplıkları Unicode veya Unicode olmayan sürümünü kullanılıp kullanılmayacağını belirtir.  
  
 **Proje stili**  
 Uygulamanızı bir standart MFC, dosya Gezgini'ni, Visual Studio veya Office mimarisi ve görüntü olup olmadığını gösterir. Daha fazla bilgi için bkz: [dosya Gezgini stilinde MFC uygulaması oluşturma](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md).  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**MFC standart**|Bir standart MFC Uygulama mimarisi sağlar.|  
|**Dosya Gezgini**|Sol bölmede olduğu Bölümlendirici penceresini kullanarak bir dosya gezginini benzeri uygulama uygulayan bir [CTreeView sınıfı](../../mfc/reference/ctreeview-class.md) ve sağ bölmede bir [CListView sınıfı](../../mfc/reference/clistview-class.md).|  
|**Visual Studio**|Dört dockable bölmeleri içeren Visual Studio benzeri uygulamasını uygular (**dosya görünümü**, **sınıf görünümü**, **özellikleri**, ve **çıkış**) öğesinden türetilen [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) ve türetilmiş bir ana çerçeve penceresi [CMDIFrameWndEx sınıfı](../../mfc/reference/cmdiframewndex-class.md) (varsayılan).|  
|**Office**|Türetilen bir Şerit içeren bir Office benzeri uygulama uygulayan [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md), türetilmiş bir Outlook Çubuğu [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md), türetilmiş bir başlık çubuğu [CMFCCaptionBar sınıfı](../../mfc/reference/cmfccaptionbar-class.md)ve türetilmiş bir ana çerçeve [CMDIFrameWndEx sınıfı](../../mfc/reference/cmdiframewndex-class.md).|  
  
 **Görsel stil ve renkleri**  
 Uygulama visual stilini belirler. Aşağıdaki seçenekler mevcuttur:  
  
-   **Windows yerel/varsayılan**  
  
-   **Office 2003**  
  
-   **Visual Studio 2005**  
  
-   **Office 2007 (mavi tema)**  
  
-   **Office 2007 (siyah tema)**  
  
-   **Office 2007 (Gümüş tema)**  
  
-   **Office 2007 (açık mavi tema)**  
  
 **Görsel stil geçiş etkinleştir**  
 Kullanıcının uygulamanın çalışma zamanında görsel stil genellikle bir menü veya Şerit uygun görsel stil seçerek değiştirip değiştiremeyeceğini belirler.  
  
 **MFC kullanımı**  
 MFC Kitaplığı'na bağlamak nasıl belirtir. Varsayılan olarak, MFC paylaşılan DLL olarak bağlanır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Paylaşılan DLL MFC kullanma**|MFC kitaplığını bir uygulamayı paylaşılan DLL olarak bağlar. Uygulamanın çalışma zamanında MFC kitaplığını çağrılar. Bu seçenek MFC kitaplığını kullanan birden fazla yürütülebilir dosya oluşur uygulamaların disk ve bellek gereksinimlerini azaltır. Win32 ve MFC uygulamaları (varsayılan), DLL işlevleri çağırabilir|  
|**MFC statik kitaplığa kullanın**|Statik MFC kitaplık uygulamaya derleme zamanında bağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)   
 [Visual C++ Projeleri için Oluşturulan Dosya Türleri](../../ide/file-types-created-for-visual-cpp-projects.md)

