---
title: Uygulama Türü, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.apptype
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
ms.openlocfilehash: c6d8a57c577dad20ac7bb8f579220a77d2a34850
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708261"
---
# <a name="application-type-mfc-application-wizard"></a>Uygulama Türü, MFC Uygulama Sihirbazı

Bu sayfanın kullanın [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md) tasarlayıp temel özellikleri eklemek için yeni bir MFC uygulaması.

- **Uygulama türü**

  Uygulamanızı oluşturmak istediğiniz belge desteği türünü belirtir. Seçtiğiniz uygulama türüne, uygulamanız için kullanılabilen kullanıcı arabirimi seçenekleri belirler. Bkz: [kullanıcı arabirimi özellikleri, MFC Uygulama Sihirbazı](../../mfc/reference/user-interface-features-mfc-application-wizard.md) daha fazla bilgi için.

   Belge türleri hakkında daha fazla bilgi için bkz:

  - [SDI ve MDI](../../mfc/sdi-and-mdi.md)

  - [Çerçeve Pencereleri](../../mfc/frame-windows.md)

  - [Çerçeve Penceresi Sınıfları](../../mfc/frame-window-classes.md)

  - [Belgeler, Görünümler ve Çerçeve](../../mfc/documents-views-and-the-framework.md)

  - [İletişim Kutuları](../../mfc/dialog-boxes.md)

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Tek belge**|Burada view sınıfı üzerinden hesaplanmıştır uygulamanız için bir tek Belgeli Arabirim (SDI) mimarisi oluşturur [CView sınıfı](../../mfc/reference/cview-class.md). Temel Sınıf Görünümü'nde için değiştirebileceğiniz [oluşturulan sınıflar, MFC Uygulama Sihirbazı](../../mfc/reference/generated-classes-mfc-application-wizard.md) Sihirbazı sayfası. Örneğin, form tabanlı bir uygulama oluşturmak için kullanın [CFormView sınıfı](../../mfc/reference/cformview-class.md) için Görünüm sınıfı.<br /><br /> İçinde bu tür bir uygulama, tek bir belge belgenin çerçeve penceresi barındırabilir.|
  |**Birden çok belge**|Burada view sınıfı üzerinden hesaplanmıştır uygulamanız için bir birden çok belge arabirimi (MDI) mimarisi oluşturur `CView`. Temel Sınıf Görünümü'nde için değiştirebileceğiniz **oluşturulan sınıflar** Sihirbazı sayfası. Örneğin, form tabanlı bir uygulama oluşturmak için kullanın `CFormView` için Görünüm sınıfı.<br /><br /> İçinde bu tür bir uygulama belgenin çerçeve penceresinde windows birden fazla alt barındırabilir.|
  |**Sekmeli Belge**|Her belge için ayrı bir sekmede yerleştirir.|
  |**İletişim kutusu tabanlı**|Burada bir iletişim kutusu sınıfı temel uygulamanız için bir iletişim kutusu tabanlı mimarisi oluşturur `CDialog`. (Bir HTML iletişim kutusu oluşturmak için kutusunu **kullanım HTML iletişim**.)|
  |**HTML iletişim kutusunu kullanın**|İletişim kutusu için yalnızca uygulamaları. İletişim sınıfından türetilen [CDHtmlDialog sınıfı](../../mfc/reference/cdhtmldialog-class.md) yerine [CDialog sınıfı](../../mfc/reference/cdialog-class.md). Bu kutuyu işaretlerseniz `CDHtmlDialog` listelenir **temel sınıfı** kutusunda [oluşturulan sınıflar, MFC Uygulama Sihirbazı](../../mfc/reference/generated-classes-mfc-application-wizard.md) Sihirbazı sayfası.<br /><br /> A `CDHtmlDialog`-türetilmiş iletişim kutusu görüntüler HTML tabanlı iletişim kutuları, HTML veri denetler ve HTML olayları işler.|
  |**Birden çok en üst düzey belge**|Burada view sınıfı üzerinden hesaplanmıştır uygulamanız için birden çok üst düzey bir mimari oluşturur `CView`.<br /><br /> Bu tür bir uygulama, kullanıcı tıkladığında **yeni** (veya **yeni çerçeve**) üzerinde **dosya** menüsünde, uygulama ana olan örtük olarak masaüstü bir pencere oluşturur. Yeni belge çerçeve, görev çubuğunda görünür ve uygulama penceresinin istemci alanına sınırlı değildir.|

- **Belge/görünüm mimarisi desteği**

  Belge/görünüm mimarisi kullanarak uygulamanızda eklenip eklenmeyeceğini belirtir [CDocument sınıfı](../../mfc/reference/cdocument-class.md) ve [CView sınıfı](../../mfc/reference/cview-class.md) (varsayılan). MFC olmayan uygulama bağlantı noktası oluşturma veya derlenmiş yürütülebilir dosyanızın boyutunu küçültmek istiyorsanız bu onay kutusunu temizleyin. Varsayılan olarak, bir uygulama olmadan belge/görünüm mimarisi türetilen [CWinApp sınıfı](../../mfc/reference/cwinapp-class.md), ve bir disk dosyasından bir belgeyi açmak için MFC desteği içermez.

- **Kaynak dili**

  Kaynaklarınızın dili ayarlar. Listede kullanılabilir diller, sisteminizde Visual Studio tarafından yüklenmiş olarak görüntülenir. Sistem dilinizi dışında bir dil seçmek istiyorsanız, bu dil için uygun şablon klasörü zaten yüklü olmalıdır.

  Seçtiğiniz dili yansıtılır **yerelleştirilmiş dizeleri** seçeneği [belge şablonu dizeleri, MFC Uygulama Sihirbazı](../../mfc/reference/document-template-strings-mfc-application-wizard.md) Sihirbazı sayfası.

- **Unicode kitaplıklarını kullanma**

  MFC kitaplıkları bir Unicode veya Unicode olmayan sürümünün kullanılıp kullanılmayacağını belirtir.

- **Proje stili**

  Uygulamanızı bir standart MFC, dosya Gezgini, Visual Studio veya Office mimarisi ve görüntü olup olmadığını gösterir. Daha fazla bilgi için [dosya Gezgini stilinde MFC uygulaması oluşturma](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md).

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**MFC standart**|Standart bir MFC Uygulama mimarisi sağlar.|
  |**Dosya Gezgini**|Sol bölmede olduğu bir ayırıcı penceresi kullanarak bir dosyayı Gezgin benzeri uygulama uygulayan bir [CTreeView sınıfı](../../mfc/reference/ctreeview-class.md) ve sağ bölmede bir [CListView sınıfı](../../mfc/reference/clistview-class.md).|
  |**Visual Studio**|Dört yerleştirilebilir bölmeleri içeren Visual Studio benzeri uygulamasını uygular (**dosya görünümü**, **sınıf görünümü**, **özellikleri**, ve **çıkış**) sınıfından türetilen [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) ve türetilen bir ana çerçeve penceresi [Cmdıframewndex sınıfı](../../mfc/reference/cmdiframewndex-class.md) (varsayılan).|
  |**Office**|Türetilen bir Şerit içeren bir Office benzeri uygulama uygulayan [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md), türetilen bir Outlook Çubuğu [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md), türetilen bir başlık çubuğu [CMFCCaptionBar sınıfı](../../mfc/reference/cmfccaptionbar-class.md), türetilen bir ana çerçeve [Cmdıframewndex sınıfı](../../mfc/reference/cmdiframewndex-class.md).|

- **Görsel stil ve renkler**

  Uygulamanın görsel stilini belirler. Aşağıdaki seçenekler mevcuttur:

  - **Windows yerel/varsayılan**

  - **Office 2003**

  - **Visual Studio 2005**

  - **Office 2007 (mavi tema)**

  - **Office 2007 (siyah tema)**

  - **Office 2007 (Gümüş tema)**

  - **Office 2007 (açık mavi tema)**

- **Görsel stil geçişini etkinleştir**

  Kullanıcının görsel stili uygulamanın çalışma zamanında, genellikle bir menü veya Şerit uygun görsel stil seçerek değiştirip değiştiremeyeceğini belirtir.

- **MFC'nin kullanımı**

  MFC Kitaplığı'na bağlama belirtir. Varsayılan olarak, MFC paylaşılan DLL olarak bağlanır.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Paylaşılan DLL'de MFC kullan**|MFC Kitaplığı uygulamanın paylaşılan DLL olarak bağlar. Uygulama çalışma zamanında MFC Kitaplığı çağrılar. Bu seçenek, MFC Kitaplığı kullanan birden fazla yürütülebilir dosya oluşan uygulamaları disk ve bellek gereksinimlerini azaltır. Win32 ve MFC uygulamaları (varsayılan), DLL işlevleri çağırabilir|
  |**MFC'yi statik kitaplıkta kullan**|Uygulamanın statik MFC Kitaplığı için derleme zamanında bağlar.|

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)<br/>
[Oluşturulan türleri için Visual Studio dosya C++ projeleri](../../build/reference/file-types-created-for-visual-cpp-projects.md)
