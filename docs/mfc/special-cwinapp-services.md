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
ms.openlocfilehash: 04c7357d67dc1a5daee4b8b8135c9a54eda8504a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127835"
---
# <a name="special-cwinapp-services"></a>Özel CWinApp Hizmetleri

İleti döngüsünü çalıştırmanın yanı sıra uygulamayı başlatmak ve sonrasında temizlemek için bir fırsat vererek, [CWinApp](../mfc/reference/cwinapp-class.md) birçok farklı hizmeti sağlar.

##  <a name="_core_shell_registration"></a>Kabuk kaydı

Varsayılan olarak, MFC Uygulama Sihirbazı, kullanıcının uygulamanızın oluşturduğu veri dosyalarını dosya Gezgini veya dosya yöneticisi 'nde çift tıklayarak açmasını mümkün hale getirir. Uygulamanız bir MDI uygulaması ise ve uygulamanızın oluşturduğu dosyalar için bir uzantı belirtirseniz, MFC Uygulama Sihirbazı, sizin için yazdığı `InitInstance` geçersiz kılmak için, [CWinApp](../mfc/reference/cwinapp-class.md) 'ın [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) ve [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen) üye işlevlerine çağrılar ekler.

`RegisterShellFileTypes`, uygulamanızın belge türlerini dosya Gezgini veya Dosya Yöneticisi ile kaydeder. İşlevi, girdileri Windows 'un koruduğu kayıt veritabanına ekler. Girdiler her belge türünü kaydeder, dosya uzantısını dosya türüyle ilişkilendirir, uygulamayı açmak için bir komut satırı belirtir ve bu türden bir belgeyi açmak için bir dinamik veri değişimi (DDE) komutu belirtir.

`EnableShellOpen`, uygulamanızın dosya Gezgini 'nden veya dosya yöneticisinden DDE komutları almasına izin vererek Kullanıcı tarafından seçilen dosyayı açmasını sağlayarak işlemi tamamlar.

`CWinApp` ' deki bu otomatik kayıt desteği, uygulamanıza bir. reg dosyası gönderme veya özel yükleme çalışması gereksinimini ortadan kaldırır.

Uygulamanız için GDI+ başlatmak istiyorsanız ( [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) Işlevinizde [Gdılusstartup](/windows/win32/api/gdiplusinit/nf-gdiplusinit-gdiplusstartup) ' ı çağırarak), GDI+ arka plan iş parçacığını bastırın.

Bunu, [Gdılusstartupınput](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput) yapısının `SuppressBackgroundThread` üyesini **true**olarak ayarlayarak yapabilirsiniz. GDI+ arka plan iş parçacığını bastırdığınızda, `NotificationHook` ve `NotificationUnhook` çağrılarının yalnızca uygulamanın ileti döngüsünden çıkmadan önce yapılması gerekir. Bu çağrılar hakkında daha fazla bilgi için bkz. [Gdılusstartupoutput](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput). Bu nedenle `GdiplusStartup` çağrısı yapmak için iyi bir yer vardır ve kanca bildirim işlevleri aşağıda gösterildiği gibi, [CWinApp:: Run](../mfc/reference/cwinapp-class.md#run)sanal işlevindeki bir geçersiz kılmada olacaktır:

[!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]

Arka plan GDI+ iş parçacığını bastırmadıysanız, ana penceresi oluşturulduktan sonra, DDE komutları uygulamaya erken verilmeyebilir. Kabuk tarafından verilen DDE komutları zamanından önce iptal edilebilir ve bu da hata iletilerine neden olabilir.

##  <a name="_core_file_manager_drag_and_drop"></a>Dosya Yöneticisi sürükleme ve bırakma

Dosyalar, dosya yöneticisi veya dosya Gezgini 'ndeki dosya görünümü penceresinden uygulamanızdaki bir pencereye sürüklenebilir. Örneğin, bir veya daha fazla dosyanın bir MDI uygulamasının ana penceresine sürüklenmesi için, uygulamanın dosya adlarını alabildiği ve bu dosyalar için MDI alt pencerelerini açabilbileceği durumlar olabilir.

Uygulamanızda dosya sürüklemeyi ve bırakmayı etkinleştirmek için, MFC Uygulama Sihirbazı `InitInstance`ana çerçeve pencereniz için [CWnd](../mfc/reference/cwnd-class.md) üye Işlevi [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) öğesine bir çağrı yazar. Sürükle ve bırak özelliğini uygulamak istemiyorsanız bu çağrıyı kaldırabilirsiniz.

> [!NOTE]
>  Ayrıca, OLE ile verileri belgeler arasında veya belge içinde sürükleyerek daha genel sürükle ve bırak özellikleri de uygulayabilirsiniz. Bilgi için [OLE sürükle ve bırak](../mfc/drag-and-drop-ole.md)makalesine bakın.

##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a>En son kullanılan belgeleri takip tutma

Kullanıcı, dosyaları açıp kapattığında, uygulama nesnesi en son kullanılan dört dosyayı izler. Bu dosyaların adları Dosya menüsüne eklenir ve değiştiğinde güncelleştirilir. Çerçeve bu dosya adlarını kayıt defterinde veya. ini dosyasında, projenizle aynı ada sahip olacak şekilde depolar ve uygulamanız başlatıldığında onları dosyadan okur. MFC Uygulama Sihirbazı 'nın sizin için oluşturduğu `InitInstance` geçersiz kılma, en son kullanılan dosya adları da dahil olmak üzere kayıt defteri veya. ini dosyasından bilgileri yükleyen [CWinApp](../mfc/reference/cwinapp-class.md) üye Işlevi [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings)öğesine bir çağrı içerir.

Bu girişler aşağıdaki gibi depolanır:

- Windows NT, Windows 2000 ve sonraki sürümlerde, değer bir kayıt defteri anahtarına depolanır.

- Windows 3. x ' de, değer WIN 'da depolanır. INı dosyası.

- Windows 95 ve üzeri sürümlerde, bu değer WIN 'ın önbelleğe alınmış bir sürümünde depolanır. Dosyası.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
