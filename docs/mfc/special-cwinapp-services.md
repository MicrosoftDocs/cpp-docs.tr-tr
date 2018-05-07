---
title: Özel CWinApp Hizmetleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
dev_langs:
- C++
helpviewer_keywords:
- files [MFC], most recently used
- DragAcceptFiles method [MFC]
- MRU lists
- GDI+, initializing for MFC
- GDI+, suppressing background thread [MFC]
- CWinApp class [MFC], shell registration
- application objects [MFC], services
- CWinApp class [MFC], initializing GDI+
- MFC, shell registration
- CWinApp class [MFC], File Manager drag and drop
- LoadStdProfileSettings method [MFC]
- MFC, most-recently-used file list
- RegisterShellFileTypes method [MFC]
- drag and drop [MFC], files
- registering file types
- Shell, registering file types
- services, provided by CWinApp
- CWinApp class [MFC], recently used documents
- CWinApp class [MFC], services
- files [MFC], drag and drop
- EnableShellOpen method [MFC]
- registry [MFC], most recently used files
- MFC, file operations
- registration [MFC], shell
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81c3804ccc4f9e30e2d287102c408c98a77c6833
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="special-cwinapp-services"></a>Özel CWinApp Hizmetleri
İleti döngüsü çalıştıran ve uygulamayı başlatın ve sonra temizleme fırsatı veren yanı sıra [CWinApp](../mfc/reference/cwinapp-class.md) birkaç diğer hizmetler sağlar.  
  
##  <a name="_core_shell_registration"></a> Kabuk kaydı  
 Varsayılan olarak, MFC Uygulama Sihirbazı'nı dosya Gezgini veya Dosya Yöneticisi'ni tıklatarak, uygulamanızın oluşturduğu veri dosyalarını açmak kullanıcının sağlar. Uygulamanızı bir MDI uygulamasıdır ve uygulamanızın oluşturduğu dosyaları için bir uzantısı belirtirseniz, MFC Uygulama Sihirbazı'nı çağrıları ekler [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) ve [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)üye işlevlerini [CWinApp](../mfc/reference/cwinapp-class.md) için `InitInstance` sizin için yazar geçersiz kılma.  
  
 `RegisterShellFileTypes` Uygulamanızın belge türleri, dosya Gezgini'ni veya Dosya Yöneticisi ile kaydeder. İşlev Windows korur kaydı veritabanı girdileri ekler. Girişleri her belge türü kaydetmek, bir dosya uzantısı dosya türü ile ilişkilendirmek, uygulamayı açmak için bir komut satırı belirtin ve bu tür bir belgeyi açmak için dinamik veri değişimi (DDE) komutunu belirtin.  
  
 `EnableShellOpen` Dosya Gezgini'ni veya Dosya Yöneticisi kullanıcı tarafından seçilen dosyayı açmaya DDE komutlarını almak için uygulamanızı vererek işlemini tamamlar.  
  
 Bu otomatik kayıt Destek `CWinApp` .reg dosyasını uygulamanızla birlikte sevk etmek veya özel yükleme yapması için gereksinimini ortadan kaldırır.  
  
 GDI + uygulamanız için başlatmak istiyorsanız (çağırarak [GdiplusStartup](https://msdn.microsoft.com/library/ms534077) içinde [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) işlevi), GDI + arka plan iş parçacığı gizlemek vardır.  
  
 Bunu ayarlayarak yapabilirsiniz **SuppressBackgroundThread** üyesi [GdiplusStartupInput](https://msdn.microsoft.com/library/ms534067) için yapı **doğru**. Ne zaman gizleme GDI + arka plan iş parçacığı, **NotificationHook** ve **NotificationUnhook** çağrıları yapılan yalnızca önceki girerek ve uygulama ileti döngüsü çıkılıyor. Bu çağrıları hakkında daha fazla bilgi için bkz: [GdiplusStartupOutput](https://msdn.microsoft.com/library/ms534068). Çağrılacak bu nedenle, uygun bir yerdir **GdiplusStartup** ve sanal işlev bir geçersiz kılma kanca bildirim işlevleri olacağını [CWinApp::Run](../mfc/reference/cwinapp-class.md#run), aşağıda gösterildiği gibi:  
  
 [!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]  
  
 GDI + iş parçacığı arka plan bastırmak değil, kendi ana penceresi oluşturmadan önce DDE komutlarını erken de uygulamaya verilebilir. Kabuk tarafından verilen DDE komutları erken, hata iletilerine kaynaklanan iptal.  
  
##  <a name="_core_file_manager_drag_and_drop"></a> Dosya Yöneticisi sürükleme ve bırakma  
 Dosyaları dosya Görünümü penceresinden Dosya Yöneticisi veya dosya Gezgini'nde, uygulamanızdaki bir pencere için sürüklenebilir. Örneğin, burada uygulama dosya adları alabilir ve bu dosyalar için MDI alt pencereleri açık bir MDI uygulamanın ana penceresinde için sürüklenebilir bir veya daha fazla etkinleştirebilir.  
  
 MFC Uygulama Sihirbazı'nı dosya Sürükle etkinleştirmek ve uygulamanızda bırakma için bir çağrı Yazar [CWnd](../mfc/reference/cwnd-class.md) üye işlevi [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) ana çerçeve penceresinde için `InitInstance`. Sürükle ve bırak özelliği uygulamak isterseniz, o çağrının kaldırabilirsiniz.  
  
> [!NOTE]
>  Daha fazla genel sürükle ve bırak yeteneklerini de uygulayabilirsiniz — belgeler içinde veya arasında veri sürükleme — OLE ile. Bilgi için bkz: [sürükleme ve bırakma (OLE)](../mfc/drag-and-drop-ole.md).  
  
##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> Çoğu izlemek son kullanılan belgeler  
 Kullanıcı dosyaları açıp kapatan gibi uygulama nesnesinin dört en son kullanılan dosyalar izler. Bu dosyaların adlarını dosya menüsüne eklenir ve bunlar değiştirdiğinizde güncelleştirildi. Framework bu dosya adları ya da kayıt defteri veya projenizin aynı ada sahip .ini dosyasında depolar ve uygulamanız başladığında dosyadan okur. `InitInstance` Çağrısı içeriyor için MFC Uygulama Sihirbazı'nı oluşturur geçersiz kılma [CWinApp](../mfc/reference/cwinapp-class.md) üye işlevi [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings), kayıt defteri ya da .ini bilgi yükler Dosya, dosya adlarını en yakın zamanda de dahil olmak üzere kullanılır.  
  
 Bu girişler gibi depolanır:  
  
-   Windows NT, Windows 2000 ve daha sonra bir kayıt defteri anahtarı değeri depolanır.  
  
-   Windows 3.x, değer WIN depolanır. INI dosyası.  
  
-   Windows 95 ve daha sonra değer WIN önbelleğe alınmış bir sürümünde depolanır. INI.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)