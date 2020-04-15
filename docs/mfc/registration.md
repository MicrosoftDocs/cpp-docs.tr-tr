---
title: Kayıt
ms.date: 11/04/2016
helpviewer_keywords:
- servers [MFC], initializing
- initializing servers [MFC]
- OLE, registration
- installing servers [MFC]
- registry [MFC], OLE item database
- registration databases [MFC]
- servers [MFC], installing
- OLE server applications [MFC], registering servers
ms.assetid: 991d5684-72c1-4f9e-a09a-9184ed12bbb9
ms.openlocfilehash: 82411e53620e92eff3484f7d3f7955030fd439ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372837"
---
# <a name="registration"></a>Kayıt

Bir kullanıcı bir uygulamaya Bir OLE öğesi eklemek istediğinde, OLE aralarından seçim yapabileceğiniz nesne türlerinin bir listesini sunar. OLE bu listeyi tüm sunucu uygulamaları tarafından sağlanan bilgileri içeren sistem kayıt veritabanından alır. Bir sunucu kendisini kaydettiğinde, sistem kayıt veritabanına (Kayıt Defteri) koyduğu girişler, sağladığı her nesne türünü, dosya uzantılarını ve diğer bilgilerin yanı sıra kendisine giden yolu tanımlar.

Çerçeve ve OLE sistemi dinamik bağlantı kitaplıkları (DLL), sistemde ne tür OLE öğelerinin kullanılabileceğini belirlemek için bu kayıt defterini kullanır. OLE sistemi DLl'leri, bağlantılı veya katıştırılmış bir nesne etkinleştirildiğinde sunucu uygulamasının nasıl başlatılabildiğini belirlemek için de bu kayıt defterini kullanır.

Bu makalede, her sunucu uygulaması yüklendiğinde ve her yürütüldüğünde ne yapması gerektiği açıklanmaktadır.

Sistem kayıt veritabanı ve güncellemek için kullanılan .reg dosyalarının biçimi hakkında ayrıntılı bilgi için *OLE Programcısının Başvurusu'na*bakın.

## <a name="server-installation"></a><a name="_core_server_installation"></a>Sunucu Kurulumu

Sunucu uygulamanızı ilk yüklediğinizde, desteklediği tüm OLE öğelerini kaydetmelidir. Ayrıca, sunucunun sistem kayıt veritabanını tek başına bir uygulama olarak her çalıştırdığınızda güncelleştirmesini de sağlayabilirsiniz. Bu, sunucunun çalıştırılabilir dosyası taşınırsa kayıt veritabanını güncel tutar.

> [!NOTE]
> Uygulama sihirbazı tarafından oluşturulan MFC uygulamaları, tek başına uygulamalar olarak çalıştırıldığında kendilerini otomatik olarak kaydeder.

Yükleme sırasında başvurunuzu kaydetmek istiyorsanız, RegEdit.exe programını kullanın. Uygulamanızla birlikte bir kurulum programı eklerseniz, kurulum programının "RegEdit /S *appname*.reg" çalıştırılsın. (/S bayrağı sessiz işlemi gösterir, diğer bir şekilde komutun başarıyla tamamladığını bildiren iletişim kutusunu görüntülemez.) Aksi takdirde, kullanıcıya RegEdit'i el ile çalıştırmasını emredin.

> [!NOTE]
> Uygulama sihirbazı tarafından oluşturulan .reg dosyası, yürütülebilir için tam yolu içermez. Yükleme programınız .reg dosyasını yürütülebilir yolun tamamını içerecek şekilde değiştirmeli veya PATH ortamı değişkenini yükleme dizini içerecek şekilde değiştirmelidir.

RegEdit,..reg metin dosyasının içeriğini kayıt veritabanında birleştirir. Veritabanını doğrulamak veya onarmak için kayıt defteri düzenleyicisini kullanın. Temel OLE girişlerini silmemeye dikkat edin.

## <a name="server-initialization"></a><a name="_core_server_initialization"></a>Sunucu Başlatma

Uygulama sihirbazı yla bir sunucu uygulaması oluşturduğunuzda, sihirbaz sizin için tüm başlatma görevlerini otomatik olarak tamamlar. Bu bölümde, bir sunucu uygulamasını el ile yazarsanız ne yapmanız gerektiği açıklanmaktadır.

Bir kapsayıcı uygulaması tarafından bir sunucu uygulaması başlatıldığında, OLE sistemi DLL'leri sunucunun komut satırına "/Gömme" seçeneğini ekler. Bir sunucu uygulamasının davranışı bir kapsayıcı tarafından başlatılıp başlatılmadığına bağlı olarak değişir, bu nedenle yürütme başladığında bir uygulamanın yapması gereken ilk şey komut satırında "/Embedding" veya "-Embedding" seçeneğini denetlemektir. Bu anahtar varsa, sunucunun yerinde etkin veya tamamen açık olduğunu gösteren farklı bir kaynak kümesi yükleyin. Daha fazla bilgi için [Menüler ve Kaynaklar: Sunucu Eklemeleri'ne](../mfc/menus-and-resources-server-additions.md)bakın.

Sunucu uygulamanız komut `CWinApp::RunEmbedded` satırını ayrışdırmak için işlevini de aramalıdır. Sıfır olmayan bir değer döndürürse, tek başına bir uygulama olarak değil, bir kapsayıcı uygulamasından çalıştırıldığı için uygulama penceresini göstermemelidir. Bu işlev, sunucunun sistem kayıt veritabanındaki girişini `RegisterAll` güncelleştirir ve örnek kaydı gerçekleştiren üye işlevini sizin için çağırır.

Sunucu uygulamanız başlatılırken, örnek kaydı gerçekleştirebileceğinden emin olmalısınız. Örnek kaydı, OLE sistemi DLs'lerine sunucunun etkin olduğunu ve kapsayıcılardan istek almaya hazır olduğunu bildirir. Kayıt veritabanına giriş eklemez. Sunucunun örnek kaydını, `ConnectTemplate` tanımlanan üye işlevi çağırarak gerçekleştirin. `COleTemplateServer` Bu nesneyi `CDocTemplate` `COleTemplateServer` nesneye bağlar.

İşlev `ConnectTemplate` üç parametre alır: sunucunun *CLSID'si,* `CDocTemplate` nesneye işaretçi ve sunucunun birden çok örneği destekleyip desteklemediğini belirten bir bayrak. Bir mini sunucu birden çok örneği destekleyebilmeli, diğer bir süre sunucunun birden çok örneğinin aynı anda çalışması mümkün olmalıdır, her kapsayıcı için bir tane. Sonuç olarak, bir mini sunucu başlatırken bu bayrak için **TRUE'yı** geçirin.

Eğer bir miniserver yazıyorsanız, tanımı gereği her zaman bir kapsayıcı tarafından başlatılan olacaktır. "/Embedding" seçeneğini denetlemek için komut satırını ayrıştırmalısınız. Komut satırında bu seçeneğin olmaması, kullanıcının mini sunucuyu tek başına bir uygulama olarak başlatmaya çalıştığı anlamına gelir. Bu durumda, sunucuyu sistem kayıt veritabanına kaydedin ve ardından kullanıcıya bir kapsayıcı uygulamasından mini sunucuyu başlatmasını bildiren bir ileti kutusu görüntüleyin.

## <a name="see-also"></a>Ayrıca bkz.

[OLE](../mfc/ole-in-mfc.md)<br/>
[Sunucular](../mfc/servers.md)<br/>
[CwinApp::RunAutomated](../mfc/reference/cwinapp-class.md#runautomated)<br/>
[Cwinapp::RunEmbedded](../mfc/reference/cwinapp-class.md#runembedded)<br/>
[COleTemplateServer Sınıfı](../mfc/reference/coletemplateserver-class.md)
