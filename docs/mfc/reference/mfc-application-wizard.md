---
description: 'Daha fazla bilgi edinin: MFC Uygulama Sihirbazı'
title: MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: 645f0e1ed3f1f35c109d524a8c63fa36231bc61a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219219"
---
# <a name="mfc-application-wizard"></a>MFC Uygulama Sihirbazı

MFC Uygulama Sihirbazı, derlendikleri zaman bir Windows yürütülebilir (. exe) uygulamasının temel özelliklerini uygulayan bir uygulama oluşturur. MFC başlangıç uygulaması C++ kaynak (. cpp) dosyalarını, kaynak (. RC) dosyalarını, üst bilgi (. h) dosyalarını ve bir proje (. vcxproj) dosyasını içerir. Bu başlangıç dosyalarında oluşturulan kod MFC 'yi temel alır.

> [!NOTE]
> Belirlediğiniz seçeneklere bağlı olarak, sihirbaz projenizde ek dosyalar oluşturur. Örneğin, [Gelişmiş Özellikler](../../mfc/reference/advanced-features-mfc-application-wizard.md) sayfasında **bağlama duyarlı yardım** ' ı seçerseniz, sihirbaz, projenin Yardım dosyalarını derlemek için gerekli olan dosyaları oluşturur. Sihirbazın oluşturduğu dosyalar hakkında daha fazla bilgi için bkz. [Visual Studio C++ projeleri Için oluşturulan dosya türleri](../../build/reference/file-types-created-for-visual-cpp-projects.md)ve projede Readme.txt dosyasına bakın.

## <a name="overview"></a>Genel Bakış

Bu sihirbaz sayfası oluşturmakta olduğunuz MFC uygulaması için geçerli uygulama ayarlarını açıklar. Varsayılan olarak, sihirbaz aşağıdaki gibi bir proje oluşturur:

- [Uygulama türü, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md)

  - Proje sekmeli çoklu belge arabirimi (MDI) desteğiyle oluşturulur. Daha fazla bilgi için bkz. [SDI ve MDI](../../mfc/sdi-and-mdi.md).

  - Proje [belge/görünüm mimarisini](../../mfc/document-view-architecture.md)kullanır.

  - Proje Unicode kitaplıklarını kullanır.

  - Proje Visual Studio proje stili kullanılarak oluşturulur ve görsel stil geçişi etkinleştirilir.

  - Proje, paylaşılan bir DLL 'de MFC 'yi kullanır. Daha fazla bilgi için bkz. [Visual Studio 'Da C/C++ dll 'Leri oluşturma](../../build/dlls-in-visual-cpp.md).

- [Birleşik belge desteği, MFC Uygulama Sihirbazı](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

  - Proje, bileşik belgeler için destek sağlamaz.

- [Belge şablonu dizeleri, MFC Uygulama Sihirbazı](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

  - Proje varsayılan belge şablonu dizeleri için proje adını kullanır.

- [Veritabanı desteği, MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md)

  - Proje veritabanları için destek sağlamaz.

- [Kullanıcı Arabirimi Özellikleri, MFC Uygulama Sihirbazı](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

  - Proje, bir sistem menüsü, bir durum çubuğu, Ekranı Kapla ve Simgeleştir kutuları, bir **hakkında** kutusu, standart bir menü çubuğu ve yerleştirme araç çubuğu ve alt çerçeveler gibi standart Windows Kullanıcı arabirimi özelliklerini uygular.

- [Gelişmiş özellikler, MFC Uygulama Sihirbazı](../../mfc/reference/advanced-features-mfc-application-wizard.md)

  - Proje yazdırma ve baskı önizlemeyi destekler.

  - Proje ActiveX denetimlerini destekler. Daha fazla bilgi için bkz. [ActiveX denetimleri oluşturmak Için Işlem dizisi](../../mfc/sequence-of-operations-for-creating-activex-controls.md).

  - Proje [Automation](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows Yuvaları](../../mfc/windows-sockets-in-mfc.md)veya etkin erişilebilirlik için destek sağlamaz.

  - Proje, bir **Gezgin** yerleştirme bölmesini, **Çıkış** yerleştirme bölmesini ve **Özellikler** sabitleme bölmesini destekler.

- [Oluşturulan sınıflar, MFC Uygulama Sihirbazı](../../mfc/reference/generated-classes-mfc-application-wizard.md)

  - Projenin View sınıfı [CView sınıfından](../../mfc/reference/cview-class.md)türetilir.

  - Projenin uygulama sınıfı [CWinAppEx sınıfından](../../mfc/reference/cwinappex-class.md)türetilir.

  - Projenin belge sınıfı [CDocument sınıfından](../../mfc/reference/cdocument-class.md)türetilir.

  - Projenin ana çerçeve sınıfı [CMDIFrameWndEx sınıfından](../../mfc/reference/cmdiframewndex-class.md)türetilir.

  - Projenin alt çerçeve sınıfı [Cmdictepdwndex sınıfından](../../mfc/reference/cmdichildwndex-class.md)türetilir.

Bu varsayılan ayarları değiştirmek için, sihirbazın sol sütununda uygun sekme başlığına tıklayın ve görüntülenen sayfada değişiklikleri yapın.

MFC Uygulama projesi oluşturduktan sonra, Visual C++ [kod sihirbazları](../../ide/adding-functionality-with-code-wizards-cpp.md)kullanarak projenize nesne veya denetim ekleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md)<br/>
[MFC masaüstü uygulamaları](../../mfc/mfc-desktop-applications.md)<br/>
[Windows uygulamaları yazmak için sınıfları kullanma](../../mfc/using-the-classes-to-write-applications-for-windows.md)
