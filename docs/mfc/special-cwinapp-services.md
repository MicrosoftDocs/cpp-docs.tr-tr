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
ms.openlocfilehash: 1f5abcdab3eda1304879b122acc8072951a0e6c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363912"
---
# <a name="special-cwinapp-services"></a>Özel CWinApp Hizmetleri

[CWinApp,](../mfc/reference/cwinapp-class.md) mesaj döngüsyenini çalıştırmanın ve uygulamayı başlatma ve ondan sonra temizleme fırsatı vermenin yanı sıra, başka hizmetler de sunar.

## <a name="shell-registration"></a><a name="_core_shell_registration"></a>Kabuk Kaydı

Varsayılan olarak, MFC Uygulama Sihirbazı, kullanıcının dosya gezgini veya Dosya Yöneticisi'nde çift tıklayarak uygulamanızın oluşturduğu veri dosyalarını açmasını mümkün kılar. Uygulamanız `InitInstance` bir MDI uygulamasıysa ve uygulamanızın oluşturduğu dosyalar için bir uzantı belirtirseniz, MFC Uygulama Sihirbazı sizin için yazdığı geçersiz kılmaya [CWinApp'ın](../mfc/reference/cwinapp-class.md) [RegisterShellFileTypes ve EnableShellOpen](../mfc/reference/cwinapp-class.md#registershellfiletypes) üye işlevlerine çağrılar ekler. [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)

`RegisterShellFileTypes`uygulamanızın belge türlerini Dosya Gezgini veya Dosya Yöneticisi ile kaydeder. İşlev, Windows'un koruduğu kayıt veritabanına girişler ekler. Girişler her belge türünü kaydeder, dosya uzantısını dosya türüyle ilişkilendirin, uygulamayı açmak için bir komut satırı belirtir ve bu tür bir belgeyi açmak için dinamik bir veri değişimi (DDE) komutu belirtir.

`EnableShellOpen`uygulamanızın Kullanıcı tarafından seçilen dosyayı açması için Dosya Gezgini veya Dosya Yöneticisi'nden DDE komutları almasına izin vererek işlemi tamamlar.

Bu otomatik kayıt `CWinApp` desteği, uygulamanızla birlikte bir .reg dosyası gönderme veya özel kurulum işi yapma gereksinimini ortadan kaldırır.

Uygulamanız için GDI+ başlatılmasını istiyorsanız [(InitInstance](../mfc/reference/cwinapp-class.md#initinstance) işlevinizde [GdiplusStartup'ı](/windows/win32/api/gdiplusinit/nf-gdiplusinit-gdiplusstartup) arayarak), GDI+ arka plan iş parçacığının bastırılması gerekir.

`SuppressBackgroundThread` [Bunu, GdiplusStartupInput](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput) yapısının üyesini **TRUE'ya**ayarlayarak yapabilirsiniz. GDI+ arka plan iş parçacığı `NotificationHook` `NotificationUnhook` bastırırken, ve aramalar uygulamanın ileti döngüsüne girmeden ve çıkmadan hemen önce yapılmalıdır. Bu aramalar hakkında daha fazla bilgi için [GdiplusStartupOutput'e](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput)bakın. Bu nedenle, aramak `GdiplusStartup` için iyi bir yer ve kanca bildirim fonksiyonları sanal işlev CWinApp bir geçersiz kılma [olacaktır::Çalıştırın](../mfc/reference/cwinapp-class.md#run), aşağıda gösterildiği gibi:

[!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]

Arka plan GDI+ iş parçacığını bastırmazsanız, DDE komutları ana penceresi oluşturulmadan önce uygulamaya erken verilebilir. Kabuk tarafından verilen DDE komutları zamanından önce iptal edilebilir ve bu da hata iletilerine neden olabilir.

## <a name="file-manager-drag-and-drop"></a><a name="_core_file_manager_drag_and_drop"></a>Dosya Yöneticisi Sürükle ve Bırak

Dosyalar Dosya Yöneticisi veya Dosya Gezgini'ndeki dosya görünümü penceresinden uygulamanızdaki bir pencereye sürüklenebilir. Örneğin, bir veya daha fazla dosyanın, uygulamanın dosya adlarını alıp bu dosyalar için MDI alt pencerelerini açabileceği bir MDI uygulamasının ana penceresine sürüklenmesini sağlayabilirsiniz.

Uygulamanızda dosya sürükleme ve bırakma sağlamak için, MFC Uygulama Sihirbazı [cwnd](../mfc/reference/cwnd-class.md) üye işlevi [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) için ana çerçeve pencerenizde `InitInstance`bir çağrı yazar. Sürükle ve bırak özelliğini uygulamak istemiyorsanız bu aramayı kaldırabilirsiniz.

> [!NOTE]
> Ayrıca, OLE ile belgeler arasında veya içinde veri sürükleyerek daha genel sürükle ve bırak özellikleri de uygulayabilirsiniz. Daha fazla bilgi için, [OLE sürükleyin ve bırakın](../mfc/drag-and-drop-ole.md)makalesine bakın.

## <a name="keeping-track-of-the-most-recently-used-documents"></a><a name="_core_keeping_track_of_the_most_recently_used_documents"></a>En Son Kullanılan Belgelerin İzini Tutma

Kullanıcı dosyaları açıp kapattıkça, uygulama nesnesi en son kullanılan dört dosyayı izler. Bu dosyaların adları Dosya menüsüne eklenir ve değiştirildiğinde güncelleştirilir. Çerçeve, bu dosya adlarını kayıt defterinde veya .ini dosyasında, projenizle aynı adla depolar ve başvurunuz başlatıldığında dosyadan okur. `InitInstance` MFC Uygulama Sihirbazı'nın sizin için oluşturduğu geçersiz kılma, en son kullanılan dosya adları da dahil olmak üzere kayıt defterinden veya .ini dosyasından bilgi yükleyen [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings)adlı [CWinApp](../mfc/reference/cwinapp-class.md) üye işlevine yapılan aramayı içerir.

Bu girişler aşağıdaki gibi depolanır:

- Windows NT, Windows 2000 ve daha sonra, değer bir kayıt defteri anahtarına depolanır.

- Windows 3.x'te değer WIN'de depolanır. INI dosyası.

- Windows 95 ve sonraki sürümlerde, değer WIN'in önbelleğe alınmış sürümünde depolanır. ını.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
