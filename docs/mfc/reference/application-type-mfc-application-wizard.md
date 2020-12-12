---
description: 'Daha fazla bilgi edinin: uygulama türü, MFC Uygulama Sihirbazı'
title: Uygulama Türü, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.apptype
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
ms.openlocfilehash: 178e9c1319b17e356273fc3e59d2133c8d4aa54c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322791"
---
# <a name="application-type-mfc-application-wizard"></a>Uygulama Türü, MFC Uygulama Sihirbazı

Yeni bir MFC uygulamasına temel özellikler tasarlamak ve eklemek için [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md) ' nın bu sayfasını kullanın.

- **Uygulama türü**

  Uygulamanızda oluşturmak istediğiniz belge desteğinin türünü belirtir. Seçtiğiniz uygulamanın türü, uygulamanız için kullanılabilir olan kullanıcı arabirimi seçeneklerini belirler. Daha fazla bilgi için bkz. [Kullanıcı Arabirimi Özellikleri, MFC Uygulama Sihirbazı](../../mfc/reference/user-interface-features-mfc-application-wizard.md) .

   Belge türleri hakkında daha fazla bilgi için bkz.:

  - [SDI ve MDI](../../mfc/sdi-and-mdi.md)

  - [Çerçeve pencereleri](../../mfc/frame-windows.md)

  - [Çerçeve pencere sınıfları](../../mfc/frame-window-classes.md)

  - [Belgeler, görünümler ve çerçeve](../../mfc/documents-views-and-the-framework.md)

  - [İletişim kutuları](../../mfc/dialog-boxes.md)

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Tek belge**|Uygulamanız için bir görünüm sınıfının [CView sınıfını](../../mfc/reference/cview-class.md)temel alan bir tek belge arabirimi (SDI) mimarisi oluşturur. Sihirbazın temel sınıfını [, sihirbazın oluşturulan sınıflar, MFC Uygulama Sihirbazı](../../mfc/reference/generated-classes-mfc-application-wizard.md) sayfasında değiştirebilirsiniz. Form tabanlı bir uygulama oluşturmak için, örneğin, View sınıfı için [CFormView sınıfını](../../mfc/reference/cformview-class.md) kullanın.<br /><br /> Bu tür bir uygulamada, belgenin çerçeve penceresi yalnızca bir belge içerebilir.|
  |**Birden çok belge**|Uygulamanız için bir görünüm sınıfının temel aldığı birden çok belge arabirimi (MDI) mimarisi oluşturur `CView` . Sihirbazın **oluşturulan sınıflar** sayfasında görünümün temel sınıfını değiştirebilirsiniz. Form tabanlı bir uygulama oluşturmak için, örneğin, `CFormView` View sınıfı için kullanın.<br /><br /> Bu tür bir uygulamada, belgenin çerçeve penceresi birden çok alt pencere tutabilir.|
  |**Sekmeli belgeler**|Her belgeyi ayrı bir sekmeye koyar.|
  |**İletişim kutusu tabanlı**|Uygulamanız için bir iletişim kutusu sınıfının temel aldığı iletişim kutusu tabanlı bir mimari oluşturur `CDialog` . (Bir HTML iletişim kutusu oluşturmak için **HTML Kullan iletişim** kutusunu seçin.)|
  |**HTML iletişim kutusu kullan**|Yalnızca iletişim kutusu uygulamaları için. [CDialog sınıfı](../../mfc/reference/cdialog-class.md)yerine [CDHtmlDialog sınıfından](../../mfc/reference/cdhtmldialog-class.md) iletişim kutusu sınıfını türetiliyor. Bu kutuyu işaret ederseniz, `CDHtmlDialog` sihirbazın [oluşturulan SıNıFLAR, MFC Uygulama Sihirbazı](../../mfc/reference/generated-classes-mfc-application-wizard.md) sayfasında **temel sınıf** kutusunda listelenir.<br /><br /> Bir `CDHtmlDialog` -türetilmiş iletişim kutusu HTML tabanlı iletişim kutularını görüntüler, HTML denetimleriyle verileri değiş tokuş eder ve HTML olaylarını işler.|
  |**Birden çok üst düzey belge**|Uygulamanız için bir görünüm sınıfının temel aldığı birden çok üst düzey mimari oluşturur `CView` .<br /><br /> Bu tür bir uygulamada, bir Kullanıcı **Dosya** menüsünde **Yeni** (veya **yeni çerçeve**) ' ı tıkladığında, uygulama, üst öğesi örtülü olarak masaüstü olan bir pencere oluşturur. Yeni belge çerçevesi görev çubuğunda görünür ve uygulama penceresinin istemci alanıyla sınırlı değildir.|

- **Belge/görünüm mimarisi desteği**

  [CDocument sınıfı](../../mfc/reference/cdocument-class.md) ve [CView sınıfı](../../mfc/reference/cview-class.md) (varsayılan) kullanılarak uygulamanıza belge/görünüm mimarisinin eklenip eklenmeyeceğini belirtir. MFC olmayan bir uygulama taşıma yapıyorsanız veya derlenen yürütülebilir dosyanızın boyutunu azaltmak istiyorsanız bu onay kutusunu temizleyin. Varsayılan olarak, belge/görünüm mimarisi olmayan bir uygulama [CWinApp sınıfından](../../mfc/reference/cwinapp-class.md)türetilir ve bir disk dosyasından bir belge açmak için MFC desteği içermez.

- **Kaynak dili**

  Kaynaklarınızın dilini ayarlar. Liste, sisteminizde bulunan ve Visual Studio tarafından yüklenen dilleri görüntüler. Sistem diliniz dışında bir dil seçmek istiyorsanız, o dilin uygun şablon klasörü zaten yüklü olmalıdır.

  Seçtiğiniz dil, sihirbazın [belge şablonu dizeleri, MFC Uygulama Sihirbazı](../../mfc/reference/document-template-strings-mfc-application-wizard.md) sayfasının **yerelleştirilmiş dizeler** seçeneğinde yansıtılır.

- **Unicode kitaplıklarını kullanma**

  MFC kitaplıklarının Unicode veya Unicode olmayan sürümünün kullanılıp kullanılmayacağını belirtir.

- **Proje stili**

  Uygulamanızda standart bir MFC, dosya Gezgini, Visual Studio veya Office mimarisi olup olmadığını gösterir. Daha fazla bilgi için bkz. [MFC uygulaması Explorer-Style dosya oluşturma](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md).

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**MFC standart**|Standart bir MFC uygulaması mimarisi sağlar.|
  |**Dosya Gezgini**|Sol bölmenin bir [CTreeView sınıfı](../../mfc/reference/ctreeview-class.md) olduğu ve sağ bölmenin bir [Clienstview sınıfı](../../mfc/reference/clistview-class.md)olduğu bir ayırıcı pencere kullanarak dosya Gezgini benzeri bir uygulamayı uygular.|
  |**Visual Studio**|[CDockablePane sınıfından](../../mfc/reference/cdockablepane-class.md) türetilen ve [cmdiframewndex sınıfından](../../mfc/reference/cmdiframewndex-class.md) (varsayılan) türetilmiş bir ana çerçeve penceresinde bulunan dört yerleştirilebilir bölme (**dosya görünümü**, **sınıf görünümü**, **Özellikler** ve **Çıkış**) içeren Visual Studio benzeri bir uygulama uygular.|
  |**Office**|CMFCOutlookBar sınıfından türetilmiş bir şerit içeren bir Office benzeri [](../../mfc/reference/cmfcribbonbar-class.md)uygulama uygular. [CMFCOutlookBar sınıfından](../../mfc/reference/cmfcoutlookbar-class.md)türetilmiş bir Outlook çubuğu, [CMFCCaptionBar sınıfından](../../mfc/reference/cmfccaptionbar-class.md)türetilmiş bir başlık çubuğu ve [CMDIFrameWndEx sınıfından](../../mfc/reference/cmdiframewndex-class.md)türetilen bir ana çerçeve.|

- **Görsel stil ve renkler**

  Uygulamanın görsel stilini belirler. Aşağıdaki seçenekler kullanılabilir:

  - **Windows yerel/varsayılan**

  - **Office 2003**

  - **Visual Studio 2005**

  - **Office 2007 (mavi tema)**

  - **Office 2007 (Siyah Tema)**

  - **Office 2007 (Gümüş tema)**

  - **Office 2007 (deniz mavisi teması)**

- **Görsel stil geçişini etkinleştir**

  Kullanıcının çalışma zamanında uygulamanın görsel stilini değiştirip değiştiremeyeceğini, genellikle bir menü veya şeritten uygun görsel stilini seçerek belirler.

- **MFC kullanımı**

  MFC kitaplığına nasıl bağlantı yapılacağını belirtir. Varsayılan olarak, MFC paylaşılan bir DLL olarak bağlanır.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Paylaşılan bir DLL 'de MFC kullanma**|MFC kitaplığını bir uygulamaya paylaşılan DLL olarak bağlar. Uygulama, çalışma zamanında MFC kitaplığına çağrılar yapar. Bu seçenek, MFC kitaplığını kullanan birden fazla yürütülebilir dosyadan oluşan uygulamaların disk ve bellek gereksinimlerini azaltır. Hem Win32 hem de MFC uygulamaları, DLL 'inizdeki işlevleri çağırabilir (varsayılan)|
  |**Statik kitaplıkta MFC kullanma**|Derleme zamanında bir uygulamayı statik MFC kitaplığına bağlar.|

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)<br/>
[Visual Studio C++ projeleri için oluşturulan dosya türleri](../../build/reference/file-types-created-for-visual-cpp-projects.md)
