---
title: Özel CWinApp Hizmetleri
ms.date: 11/04/2016
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
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
ms.openlocfilehash: 910660253c9d306b13294a710021a6bbd36c1952
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307321"
---
# <a name="special-cwinapp-services"></a>Özel CWinApp Hizmetleri

İleti döngüsü çalıştırmak ve uygulamayı başlatın ve sonra temizleme fırsatı veren yanı sıra [CWinApp](../mfc/reference/cwinapp-class.md) diğer birçok hizmet sunar.

##  <a name="_core_shell_registration"></a> Kabuk kaydı

Varsayılan olarak, MFC Uygulama Sihirbazı bunları dosya Gezgini ya da Dosya Yöneticisi çift tıklayarak uygulamanızın oluşturduğu veri dosyalarını açmak kullanıcı sağlar. Uygulamanızı bir MDI uygulamasıdır ve uygulamanız tarafından oluşturulan dosyalar için bir uzantı belirtirseniz, MFC Uygulama Sihirbazı çağrıları ekler [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) ve [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)üye işlevleri [CWinApp](../mfc/reference/cwinapp-class.md) için `InitInstance` sizin yerinize yazar geçersiz kılma.

`RegisterShellFileTypes` Uygulamanızın belge türleri, dosya Gezgini ya da Dosya Yöneticisi ile kaydeder. İşlev girişleri Windows tutan kayıt veritabanına ekler. Girişleri her belge türünü kaydetmek, dosya türü ile bir dosya uzantısı ilişkilendirme, uygulamayı açmak için bir komut satırı belirtin ve bu tür bir belgeyi açmak için dinamik veri değişimi (DDE) komutu belirtin.

`EnableShellOpen` Dosya Gezgini veya Dosya Yöneticisi kullanıcı tarafından seçilen dosyayı açmaya DDE komutları almak üzere uygulamanızı vererek işlemi tamamlar.

Bu otomatik kayıt desteği `CWinApp` .reg dosyası kullanarak uygulamanızı dağıtmayı veya özel yükleme iş yapma ihtiyacını ortadan kaldırır.

GDI +'da, uygulamanız için başlatmak istiyorsanız (çağırarak [GdiplusStartup](/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusstartup) içinde [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) işlevi), GDI +'da arka plan iş parçacığı bastırmak vardır.

Bunu ayarlayarak yapabilirsiniz `SuppressBackgroundThread` üyesi [GdiplusStartupInput](/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput) için yapı **TRUE**. Ne zaman gizleme GDI +'da arka plan iş parçacığı `NotificationHook` ve `NotificationUnhook` çağrıları yapılacak yalnızca önceki girme ve uygulamanın ileti döngüsünden çıkılıyor. Bu çağrılar hakkında daha fazla bilgi için bkz. [GdiplusStartupOutput](/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput). Çağırmak için bu nedenle, iyi bir yer `GdiplusStartup` ve bildirim kanca işlevlerini raporlama sanal işlevi geçersiz kılma seçeneğinde olacağını [CWinApp::Run](../mfc/reference/cwinapp-class.md#run), aşağıda gösterildiği gibi:

[!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]

GDI +'da iş parçacığı arka plan bastırmayın, kendi ana pencere oluşturulmadan önce DDE komutları beklenenden önce de uygulamaya verilebilir. Kabuk tarafından verilen DDE komutları zamanından önce hata iletilerine kaynaklanan iptal.

##  <a name="_core_file_manager_drag_and_drop"></a> Dosya Yöneticisi sürükleme ve bırakma

Dosyaları Dosya Yöneticisi veya dosya Gezgini'nde dosya Görünümü penceresinden uygulamanızdaki bir pencere için sürüklenebilir. Örneğin, bir veya daha fazla dosyaları burada uygulama dosya adlarını alabilir ve bu dosyalara ilişkin MDI alt öğe pencerelerini açmak MDI uygulamanın ana pencere, sürüklenmesi etkinleştirebileceğiniz.

MFC Uygulama Sihirbazı dosya sürükle ve bırak uygulamanızda etkinleştirmek için bir çağrı Yazar [CWnd](../mfc/reference/cwnd-class.md) üye işlevi [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) için ana çerçeve pencerenizde, `InitInstance`. Sürükle ve bırak özelliğini uygulamak istemiyorsanız, bu çağrı kaldırabilirsiniz.

> [!NOTE]
>  Daha fazla genel sürükle ve bırak özellikleri de uygulayabilirsiniz: belge içinde veya arasında veri sürükleyerek — OLE ile. Bilgi için bkz [sürükleme ve bırakma (OLE)](../mfc/drag-and-drop-ole.md).

##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> En çok izlemek son kullanılan belgeler

Kullanıcı açılır ve dosyaları kapatır gibi uygulama nesnesi dört en son kullanılan dosyaları izler. Bu dosyaların dosya menüsüne eklenen ve bunlar değiştirdiğinizde güncelleştirilir. Framework, bu dosya adları ya da kayıt defteri veya projeniz gibi aynı ada sahip bir .ini dosyası içinde depolar ve uygulamanızı başladığında bunları dosyadan okur. `InitInstance` Geçersiz kılmak için bir çağrı içerdiğine MFC Uygulama Sihirbazı oluşturur [CWinApp](../mfc/reference/cwinapp-class.md) üye işlevi [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings), kayıt defteri ya da .ini bilgileri yükler Dosya, en yakın zamanda da dahil olmak üzere, dosya adları kullanılır.

Bu girişler gibi depolanır:

- Windows NT, Windows 2000 ve üstü, değer bir kayıt defteri anahtarında depolanır.

- Windows içinde 3.x değeri WIN depolanır. INI dosyası.

- Windows 95 ve sonraki sürümlerinde, değer WIN önbelleğe alınmış bir sürümünde depolanır. INI.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)
