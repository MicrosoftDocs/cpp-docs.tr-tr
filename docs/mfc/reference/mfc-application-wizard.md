---
title: MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: 808e8364764dd826ee82e445627ba21b06946ed6
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822671"
---
# <a name="mfc-application-wizard"></a>MFC Uygulama Sihirbazı

MFC Uygulama Sihirbazı bir uygulama oluşturur, bir Windows yürütülebilir (.exe) uygulamasının temel özelliklerini derlendiğinde uygular. MFC başlangıç uygulaması C++ kaynak (.cpp) dosyaları, kaynak (.rc) dosyaları, üstbilgi (.h) dosyaları ve proje (.vcxproj) dosyasını içerir. Bu Başlatıcı dosyalarında oluşturulan kodu MFC'ye dayalı.

> [!NOTE]
>  Seçtiğiniz seçeneklere bağlı olarak, sihirbaz projenize ek dosyaları oluşturur. Örneğin, **bağlama duyarlı Yardım** üzerinde [Gelişmiş Özellikler](../../mfc/reference/advanced-features-mfc-application-wizard.md) sayfasında, Sihirbazı, projenin Yardım dosyalarını derlemek için gerekli olan dosyaları oluşturur. Sihirbazın oluşturduğu dosyaları hakkında daha fazla bilgi için bkz. [Visual C++ projeleri için oluşturulan dosya türleri](../../build/reference/file-types-created-for-visual-cpp-projects.md)ve proje Readme.txt dosyasına bakın.

## <a name="overview"></a>Genel Bakış

Bu sihirbaz sayfası oluşturduğunuz MFC uygulamasını geçerli uygulama ayarlarını açıklar. Varsayılan olarak, Sihirbazı gibi bir proje oluşturur:

- [Uygulama Türü, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md)

   - Proje sekmeli Çok Belgeli Arabirim (MDI) desteği ile oluşturulur. Daha fazla bilgi için [SDI ve MDI](../../mfc/sdi-and-mdi.md).

   - Projenin kullandığı [belge/görünüm mimarisi](../../mfc/document-view-architecture.md).

   - Proje Unicode kitaplıklarını kullanır.

   - Proje, Visual Studio Proje stili kullanılarak oluşturulur ve görsel stilini değiştirme sağlar.

   - Proje MFC paylaşılan DLL olarak kullanır. Daha fazla bilgi için [Visual C++'ta DLL'ler](../../build/dlls-in-visual-cpp.md).

- [Birleşik Belge Desteği, MFC Uygulama Sihirbazı](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

   - Proje bileşik belgeler için destek sağlar.

- [Belge Şablonu Dizeleri, MFC Uygulama Sihirbazı](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

   - Proje için varsayılan belge şablonu dizeleri proje adı kullanır.

- [Veritabanı Desteği, MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md)

   - Proje veritabanları için destek sağlar.

- [Kullanıcı Arabirimi Özellikleri, MFC Uygulama Sihirbazı](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

   - Proje kullanıcı arabirimi özellikleri, durum çubuğu, bir sistem menüsünü en üst düzeye çıkarmak ve kutularında en aza indirmek gibi standart Windows uygulayan bir **hakkında** kutusunda, bir standart menü çubuğu ve takma araç çubuğu ve alt çerçeve.

- [Gelişmiş Özellikler, MFC Uygulama Sihirbazı](../../mfc/reference/advanced-features-mfc-application-wizard.md)

   - Proje yazdırmayı ve baskı önizlemeyi destekler.

   - Proje ActiveX denetimlerini destekler. Daha fazla bilgi için [ActiveX denetimleri oluşturmak için işlem dizisi](../../mfc/sequence-of-operations-for-creating-activex-controls.md).

   - Proje için destek sağlar [Otomasyon](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows Sockets](../../mfc/windows-sockets-in-mfc.md), ya da Active Accessibility.

   - Projeyi destekleyen bir **Gezgini** yerleştirme bölmesi, bir **çıkış** yerleştirme bölmesi ve **özellikleri** yerleştirme bölmesi.

- [Oluşturulan Sınıflar, MFC Uygulama Sihirbazı](../../mfc/reference/generated-classes-mfc-application-wizard.md)

   - Projenin görünüm sınıfı türetilen [CView sınıfı](../../mfc/reference/cview-class.md).

   - Projenin uygulama sınıfı türetilir [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md).

   - Projenin belge sınıfı türetilen [CDocument sınıfı](../../mfc/reference/cdocument-class.md).

   - Projenin ana çerçeve sınıf türetilir [Cmdıframewndex sınıfı](../../mfc/reference/cmdiframewndex-class.md).

   - Proje alt çerçeve sınıfı türetilen [Cmdıchildwndex sınıfı](../../mfc/reference/cmdichildwndex-class.md).

Bu varsayılan ayarları değiştirmek için sihirbazın sol sütununda uygun sekmeyi başlığa tıklayın ve görünen sayfa değişiklikleri yapın.

Bir MFC uygulaması projesi oluşturduktan sonra nesneler veya denetimler Visual C++ kullanarak projenize ekleyebilirsiniz [kod sihirbazları](../../ide/adding-functionality-with-code-wizards-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulaması Oluşturma](../../mfc/reference/creating-an-mfc-application.md)<br/>
[MFC Masaüstü Uygulamaları](../../mfc/mfc-desktop-applications.md)<br/>
[Windows Uygulamaları Yazmak için Sınıfları Kullanma](../../mfc/using-the-classes-to-write-applications-for-windows.md)
