---
title: MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: 6949f136890e8274f225a49496b2eb1b8f78b6fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351829"
---
# <a name="mfc-application-wizard"></a>MFC Uygulama Sihirbazı

MFC Uygulama Sihirbazı, derlendiğinde, windows çalıştırılabilir (.exe) uygulamasının temel özelliklerini uygulayan bir uygulama oluşturur. MFC başlangıç uygulaması C++ kaynak (.cpp) dosyaları, kaynak (.rc) dosyaları, üstbilgi (.h) dosyaları ve bir proje (.vcxproj) dosyasını içerir. Bu başlangıç dosyalarında oluşturulan kod MFC'yi temel adatır.

> [!NOTE]
> Sihirbaz, seçtiğiniz seçeneklere bağlı olarak projenizde ek dosyalar oluşturur. Örneğin, [Gelişmiş Özellikler](../../mfc/reference/advanced-features-mfc-application-wizard.md) sayfasında **İçeriğe duyarlı yardımı** seçerseniz, sihirbaz projenin Yardım dosyalarını derlemek için gerekli dosyaları oluşturur. Sihirbazın oluşturduğu dosyalar hakkında daha fazla bilgi için [Visual Studio C++ projeleri için Oluşturulan Dosya Türleri'ne](../../build/reference/file-types-created-for-visual-cpp-projects.md)bakın ve projedeki Readme.txt dosyasına bakın.

## <a name="overview"></a>Genel Bakış

Bu sihirbaz sayfası, oluşturduğunuz MFC uygulaması için geçerli uygulama ayarlarını açıklar. Varsayılan olarak, sihirbaz aşağıdaki gibi bir proje oluşturur:

- [Uygulama Türü, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md)

  - Proje sekmeli çoklu belge arabirimi (MDI) desteği ile oluşturulur. Daha fazla bilgi için Bkz. [SDI ve MDI.](../../mfc/sdi-and-mdi.md)

  - Proje, [Belge/Görünüm Mimarisini](../../mfc/document-view-architecture.md)kullanır.

  - Proje, Unicode kitaplıklarını kullanır.

  - Proje Visual Studio proje stili kullanılarak oluşturulur ve görsel stil geçişi sağlar.

  - Proje paylaşılan bir DLL MFC kullanır. Daha fazla bilgi için Visual [Studio'da C/C++ DL'ler oluştur'a](../../build/dlls-in-visual-cpp.md)bakın.

- [Bileşik Belge Desteği, MFC Uygulama Sihirbazı](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

  - Proje bileşik belgeler için destek sağlamaz.

- [Belge Şablon Dizeleri, MFC Uygulama Sihirbazı](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

  - Proje, varsayılan belge şablon dizeleri için proje adını kullanır.

- [Veritabanı Desteği, MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md)

  - Proje veritabanları için destek sağlamaz.

- [Kullanıcı Arabirimi Özellikleri, MFC Uygulama Sihirbazı](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

  - Proje, sistem menüsü, durum çubuğu, kutuları en üst düzeye çıkarma ve simge durumuna geçirme, **Hakkında** kutusu, standart menü çubuğu ve yerleştirme araç çubuğu ve alt çerçeveler gibi standart Windows kullanıcı arabirimi özelliklerini uygular.

- [Gelişmiş Özellikler, MFC Uygulama Sihirbazı](../../mfc/reference/advanced-features-mfc-application-wizard.md)

  - Proje, yazdırma ve yazdırma önizlemesini destekler.

  - Proje ActiveX denetimlerini destekler. Daha fazla bilgi için [ActiveX Denetimleri Oluşturmak için Operasyon Dizisi'ne](../../mfc/sequence-of-operations-for-creating-activex-controls.md)bakın.

  - Proje [Otomasyon,](../../mfc/automation.md) [MAPI,](../../mfc/mapi-support-in-mfc.md)Windows [Soketleri](../../mfc/windows-sockets-in-mfc.md)veya Etkin Erişilebilirlik için destek sağlamaz.

  - Proje, **Explorer** yerleştirme bölmesini, **Çıktı** yerleştirme bölmesini ve **Özellikler** yerleştirme bölmesini destekler.

- [Oluşturulan Sınıflar, MFC Uygulama Sihirbazı](../../mfc/reference/generated-classes-mfc-application-wizard.md)

  - Projenin görünüm sınıfı [CView Sınıfından](../../mfc/reference/cview-class.md)türetilmiştir.

  - Projenin uygulama sınıfı [CWinAppEx Sınıfından](../../mfc/reference/cwinappex-class.md)türetilmiştir.

  - Projenin belge sınıfı [CDocument Sınıfından](../../mfc/reference/cdocument-class.md)türetilmiştir.

  - Projenin ana çerçeve sınıfı [CMDIFrameWndEx Sınıfından](../../mfc/reference/cmdiframewndex-class.md)türetilmiştir.

  - Projenin alt çerçeve sınıfı [CMDIChildWndEx Sınıfından](../../mfc/reference/cmdichildwndex-class.md)türetilmiştir.

Bu varsayılan ayarları değiştirmek için sihirbazın sol sütunundaki uygun sekme başlığını tıklatın ve görünen sayfada değişiklikleri yapın.

Bir MFC uygulama projesi oluşturduktan sonra, Visual C++ [kod sihirbazlarını](../../ide/adding-functionality-with-code-wizards-cpp.md)kullanarak projenize nesneler veya denetimler ekleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulaması Oluşturma](../../mfc/reference/creating-an-mfc-application.md)<br/>
[MFC Masaüstü Uygulamaları](../../mfc/mfc-desktop-applications.md)<br/>
[Windows Uygulamaları Yazmak için Sınıfları Kullanma](../../mfc/using-the-classes-to-write-applications-for-windows.md)
