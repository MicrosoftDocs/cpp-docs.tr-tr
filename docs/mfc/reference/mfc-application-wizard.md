---
title: "MFC Uygulama Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.exe.overview
dev_langs: C++
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d4997d2d793102119e5021ba1110db2674e1b42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-application-wizard"></a>MFC Uygulama Sihirbazı
MFC Uygulama Sihirbazı bir uygulama oluşturur, derlendiğinde bir Windows yürütülebilir dosyanın (.exe) uygulaması, temel özellikleri uygular. MFC başlangıç uygulaması C++ kaynak (.cpp) dosyaları, kaynak (.rc) dosyaları, üstbilgi (.h) dosyaları ve bir proje (.vcxproj) dosyası içerir. Bu Başlatıcı dosyalarda oluşturulan kod MFC temel alır.  
  
> [!NOTE]
>  Belirlediğiniz seçeneklere bağlı olarak sihirbazın projenizde ek dosyaları oluşturur. Örneğin, **bağlama duyarlı Yardım** üzerinde [Gelişmiş Özellikler](../../mfc/reference/advanced-features-mfc-application-wizard.md) sayfasında, sihirbazın projenin Yardım dosyalarını derlemek için gerekli olan dosyaları oluşturur. Sihirbazın oluşturduğu dosyaları hakkında daha fazla bilgi için bkz: [Visual C++ projeleri için oluşturulan dosya türleri](../../ide/file-types-created-for-visual-cpp-projects.md)ve projedeki Readme.txt dosyasına bakın.  
  
## <a name="overview"></a>Genel Bakış  
 Bu sihirbaz sayfası oluşturmakta olduğunuz MFC uygulaması için geçerli uygulama ayarları açıklanır. Varsayılan olarak, sihirbaz aşağıdaki gibi bir proje oluşturur:  
  
-   [Uygulama Türü, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md)  
  
    -   Proje sekmeli birden çok belge arabirimi (MDI) desteği ile oluşturulur. Daha fazla bilgi için bkz: [SDI ve MDI](../../mfc/sdi-and-mdi.md).  
  
    -   Projenin kullandığı [belge/görünüm mimarisinin](../../mfc/document-view-architecture.md).  
  
    -   Proje Unicode kitaplıklarını kullanır.  
  
    -   Projeyi Visual Studio Proje stili kullanılarak oluşturulur ve görsel stil geçiş sağlar.  
  
    -   Proje MFC paylaşılan DLL'de kullanır. Daha fazla bilgi için bkz: [DLL'leri Visual C++'ta](../../build/dlls-in-visual-cpp.md).  
  
-   [Birleşik Belge Desteği, MFC Uygulama Sihirbazı](../../mfc/reference/compound-document-support-mfc-application-wizard.md)  
  
    -   Proje bileşik belgeler için destek sağlar.  
  
-   [Belge Şablonu Dizeleri, MFC Uygulama Sihirbazı](../../mfc/reference/document-template-strings-mfc-application-wizard.md)  
  
    -   Proje için varsayılan belge şablonu dizeleri proje adı kullanır.  
  
-   [Veritabanı Desteği, MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md)  
  
    -   Proje veritabanları için destek sağlar.  
  
-   [Kullanıcı Arabirimi Özellikleri, MFC Uygulama Sihirbazı](../../mfc/reference/user-interface-features-mfc-application-wizard.md)  
  
    -   Kullanıcı arabirimi özellikleri sistem menüsü, durum çubuğu, en üst düzeye çıkarmak ve kutularında, en aza indirmek gibi standart Windows proje uygulayan bir **hakkında** kutusu, bir standart menü çubuğu ve yerleştirme araç ve alt çerçeve.  
  
-   [Gelişmiş Özellikler, MFC Uygulama Sihirbazı](../../mfc/reference/advanced-features-mfc-application-wizard.md)  
  
    -   Proje yazdırmayı ve baskı önizlemeyi destekler.  
  
    -   Proje ActiveX denetimlerini destekler. Daha fazla bilgi için bkz: [ActiveX denetimleri oluşturmak için işlem dizisi](../../mfc/sequence-of-operations-for-creating-activex-controls.md).  
  
    -   Proje desteği sağlar [Otomasyon](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows Sockets](../../mfc/windows-sockets-in-mfc.md), ya da Etkin Erişilebilirlik.  
  
    -   Proje destekler bir **Explorer** takma bölmesinde, bir **çıkış** takma bölmesinde ve bir **özellikleri** takma bölmesi.  
  
-   [Oluşturulan Sınıflar, MFC Uygulama Sihirbazı](../../mfc/reference/generated-classes-mfc-application-wizard.md)  
  
    -   Projenin görünüm sınıfı türetilir [CView sınıfı](../../mfc/reference/cview-class.md).  
  
    -   Projenin uygulama sınıfı türetilir [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md).  
  
    -   Projenin belge sınıfı türetilir [CDocument sınıfı](../../mfc/reference/cdocument-class.md).  
  
    -   Projenin ana çerçeve sınıfı türetilir [CMDIFrameWndEx sınıfı](../../mfc/reference/cmdiframewndex-class.md).  
  
    -   Projenin alt çerçeve sınıfı türetilir [CMDIChildWndEx sınıfı](../../mfc/reference/cmdichildwndex-class.md).  
  
 Bu varsayılan ayarları değiştirmek için sihirbazın sol sütunda uygun sekmeyi başlığını tıklatın ve görüntülenen sayfada değişiklikleri yapın.  
  
 MFC Uygulama projesi oluşturduktan sonra nesneler veya denetimleri Visual C++ kullanarak projenize ekleyebileceğiniz [kod sihirbazları](../../ide/adding-functionality-with-code-wizards-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md)   
 [MFC Masaüstü uygulamaları](../../mfc/mfc-desktop-applications.md)   
 [Windows Uygulamaları Yazmak için Sınıfları Kullanma](../../mfc/using-the-classes-to-write-applications-for-windows.md)
