---
title: 'Kapsayıcılar: Gelişmiş Özellikler'
ms.date: 11/04/2016
helpviewer_keywords:
- links [MFC], to embedded OLE objects
- containers [MFC], links to embedded OLE objects
- containers [MFC], advanced features
- container/server applications [MFC]
- embedded objects [MFC]
- OLE controls [MFC], containers
- OLE containers [MFC], advanced features
- server/container applications [MFC]
- containers [MFC], container applications
ms.assetid: 221fd99c-b138-40fa-ad6a-974e3b3ad1f8
ms.openlocfilehash: cf130bf8dead5c59548821658b979785c4d54726
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376492"
---
# <a name="containers-advanced-features"></a>Kapsayıcılar: Gelişmiş Özellikler

Bu makalede, isteğe bağlı gelişmiş özellikleri varolan kapsayıcı uygulamalarına dahil etmek için gereken adımlar açıklanmaktadır. Bu özellikler şunlardır:

- [Hem kapsayıcı hem de sunucu olan bir uygulama](#_core_creating_a_container_server_application)

- [Katışdırılmış bir nesneye OLE bağlantısı](#_core_links_to_embedded_objects)

## <a name="creating-a-containerserver-application"></a><a name="_core_creating_a_container_server_application"></a>Kapsayıcı/Sunucu Uygulaması Oluşturma

Kapsayıcı/sunucu uygulaması, hem kapsayıcı hem de sunucu görevi gören bir uygulamadır. Windows için Microsoft Word buna bir örnektir. Diğer uygulamalara Windows için Word belgelerini katıştırabilir ve öğeleri Windows için Word belgelerine de katıştırabilirsiniz. Kapsayıcı uygulamanızı hem kapsayıcı hem de tam sunucu olarak değiştirme işlemi (bir kombinasyon kapsayıcısı/minisunucu uygulaması oluşturamazsınız) tam sunucu oluşturma işlemine benzer.

Makale [Sunucuları: Sunucu uygulama,](../mfc/servers-implementing-a-server.md) bir sunucu uygulaması uygulamak için gereken bir dizi görevi listeler. Bir kapsayıcı uygulamasını kapsayıcı/sunucu uygulamasına dönüştürürseniz, kapsayıcıya kod ekleyerek aynı görevlerden bazılarını gerçekleştirmeniz gerekir. Göz önünde bulundurulması gereken önemli şeyleri aşağıda sıralar:

- Uygulama sihirbazı tarafından oluşturulan kapsayıcı kodu zaten OLE alt sistemi başlatılır. Bu destek için herhangi bir şeyi değiştirmeniz veya eklemeniz gerekmez.

- Belge sınıfının taban sınıfınerede `COleDocument`olursa olsun, `COleServerDoc`taban sınıfı ' n ' olarak değiştirin.

- Sunucunun `COleClientItem::CanActivate` kendisi yerinde düzenlemek için kullanılırken öğeleri yerinde düzenlemekten kaçınmak için geçersiz kılın.

   Örneğin, MFC OLE örnek [OCLIENT](../overview/visual-cpp-samples.md) kapsayıcı /sunucu uygulaması tarafından oluşturulan bir öğe katışarttı. OCLIENT uygulamasını açar ve kapsayıcı/sunucu uygulamanız tarafından oluşturulan öğeyi yerinde düzenleme. Uygulamanızın öğesini düzenlerken, MFC OLE örnek [HIERSVR](../overview/visual-cpp-samples.md)tarafından oluşturulan bir öğeyi katıştırmak istediğinize karar verirsiniz. Bunu yapmak için yerinde etkinleştirme kullanamazsınız. Bu öğeyi etkinleştirmek için HIERSVR'ı tamamen açmanız gerekir. Microsoft Foundation Class Kitaplığı bu OLE özelliğini `COleClientItem::CanActivate` desteklemediği için geçersiz kılma, bu durumu denetlemenize ve uygulamanızda olası bir çalışma zamanı hatasını önlemenize olanak tanır.

Yeni bir uygulama oluşturuyorsanız ve kapsayıcı/sunucu uygulaması olarak çalışmasını istiyorsanız, uygulama sihirbazındaki OLE Seçenekleri iletişim kutusunda bu seçeneği seçin ve bu destek otomatik olarak oluşturulur. Daha fazla bilgi için makaleye [Genel Bakış: ActiveX Denetim Kapsayıcısı Oluşturma.](../mfc/reference/creating-an-mfc-activex-control-container.md) MFC örnekleri hakkında daha fazla bilgi için [MFC Örnekleri'ne](../overview/visual-cpp-samples.md#mfc-samples)bakın.

Kendine bir MDI uygulaması ekleyemeyeceğiniz unutmayın. Kapsayıcı/sunucu olan bir uygulama, SDI uygulaması olmadığı sürece kendisine eklenemez.

## <a name="links-to-embedded-objects"></a><a name="_core_links_to_embedded_objects"></a>Gömülü Nesnelere Bağlantılar

Katıştırılmış Nesnelere Bağlantılar özelliği, kullanıcının kapsayıcı uygulamanızın içindeki katıştırılmış nesneye OLE bağlantısı olan bir belge oluşturmasına olanak tanır. Örneğin, katıştırılmış bir elektronik tablo içeren bir sözcük işlemcisinde belge oluşturun. Uygulamanız katıştırılmış nesnelere bağlantıları destekliyorsa, sözcük işlemcinin belgesinde bulunan elektronik tabloya bir bağlantı yapıştırabilir. Bu özellik, uygulamanızın elektronik tabloda yer alan bilgileri, kelime işlemcisinin ilk olarak nereden aldığını bilmeden kullanmasına olanak tanır.

#### <a name="to-link-to-embedded-objects-in-your-application"></a>Uygulamanızdaki gömülü nesnelere bağlantı vermek için

1. Belge sınıfınızı `COleLinkingDoc` `COleDocument`' dan' yerine türetin

1. OLE Geliştirme Araçları ile birlikte sınıf kimliği üreteci kullanarak uygulamanız için bir OLE sınıfı kimlik **(CLSID)** oluşturun.

1. Başvuruyu OLE'ye kaydedin.

1. Uygulama `COleTemplateServer` sınıfınızın bir üyesi olarak bir nesne oluşturun.

1. Uygulama sınıfınızın `InitInstance` üye işlevinde aşağıdakileri yapın:

   - Nesnenin `COleTemplateServer` `ConnectTemplate` üye işlevini çağırarak nesnenizi belge şablonlarınıza bağlayın.

   - Tüm `COleTemplateServer::RegisterAll` sınıf nesnelerini OLE sistemine kaydetmek için üye işlevi arayın.

   - Arayın. `COleTemplateServer::UpdateRegistry` Uygulama "/Embedded" anahtarı ile başlatılmazsa `UpdateRegistry` *OAT_CONTAINER* olması gereken tek parametre. Bu, uygulamayı katışılmış nesnelere bağlantıları desteklenebilen bir kapsayıcı olarak kaydeder.

      Uygulama "/Embedded" anahtarıyla başlatılırsa, sunucu uygulamasına benzer ana penceresini göstermemelidir.

MFC OLE örneği [OCLIENT](../overview/visual-cpp-samples.md) bu özelliği uygular. Bunun nasıl yapıldığına bir örnek `InitInstance` olarak, *OCLIENT'daki işlevi görün. *Bu örnek uygulamanın CPP dosyası.

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](../mfc/containers.md)<br/>
[Sunucular](../mfc/servers.md)
