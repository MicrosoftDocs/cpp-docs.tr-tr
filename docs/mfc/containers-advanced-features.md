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
ms.openlocfilehash: a68cc85062f9ca711c453ef98f69a7c5ea114d94
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214363"
---
# <a name="containers-advanced-features"></a>Kapsayıcılar: Gelişmiş Özellikler

Bu makalede, mevcut kapsayıcı uygulamalarına isteğe bağlı gelişmiş özellikler eklemek için gereken adımlar açıklanmaktadır. Bu özellikler şunlardır:

- [Hem kapsayıcı hem de sunucu olan uygulama](#_core_creating_a_container_server_application)

- [Katıştırılmış nesneye OLE bağlantısı](#_core_links_to_embedded_objects)

##  <a name="creating-a-containerserver-application"></a><a name="_core_creating_a_container_server_application"></a>Kapsayıcı/sunucu uygulaması oluşturma

Kapsayıcı/sunucu uygulaması, hem kapsayıcı hem de sunucu olarak davranan bir uygulamadır. Windows için Microsoft Word buna bir örnektir. Windows belgelerini Word 'e başka uygulamalara ekleyebilirsiniz ve ayrıca Windows belgeleri için Word 'e öğe ekleyebilirsiniz. Kapsayıcı uygulamanızı hem kapsayıcı hem de tam sunucu olarak değiştirme işlemi (bir bileşim kapsayıcı veya minıver uygulaması oluşturamazsınız) tam sunucu oluşturma işlemine benzerdir.

Makale [sunucuları: sunucu](../mfc/servers-implementing-a-server.md) uygulama, bir sunucu uygulaması uygulamak için gereken sayıda görevi listeler. Bir kapsayıcı uygulamasını bir kapsayıcı/sunucu uygulamasına dönüştürürseniz, aynı görevlerden bazılarını gerçekleştirmeniz ve kodu kapsayıcıya eklemek gerekir. Aşağıda dikkate alınması gereken önemli noktalar listelenmiştir:

- Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu, OLE alt sistemini zaten başlatır. Bu destek için herhangi bir şey değiştirmeniz veya eklemeniz gerekmez.

- Bir belge sınıfının temel sınıfının `COleDocument`olduğu her yerde, temel sınıfı `COleServerDoc`olarak değiştirin.

- Sunucu yerinde düzenlemek için kullanıldığı sırada öğelerin yerinde düzenlenmesinden kaçınmak için `COleClientItem::CanActivate` geçersiz kılın.

   Örneğin, MFC OLE örnek [Oclient](../overview/visual-cpp-samples.md) , Kapsayıcınız/sunucu uygulamanız tarafından oluşturulan bir öğeyi katıştırmıştır. OCLIENT uygulamasını açarsınız ve kapsayıcı/sunucu uygulamanız tarafından oluşturulan öğeyi yerinde düzenleyebilirsiniz. Uygulamanızın öğesini düzenlenirken, MFC OLE örnek [Hiersvr](../overview/visual-cpp-samples.md)tarafından oluşturulan bir öğeyi eklemek istediğinize karar verirsiniz. Bunu yapmak için yerinde etkinleştirme kullanamazsınız. Bu öğeyi etkinleştirmek için HIERSVR 'yi tamamen açmanız gerekir. Microsoft Foundation Class Kitaplığı bu OLE özelliğini desteklemediğinden, `COleClientItem::CanActivate` geçersiz kılmak bu durumu denetlemenizi ve uygulamanızda olası bir çalışma zamanı hatasını önlemenize olanak sağlar.

Yeni bir uygulama oluşturuyorsanız ve bir kapsayıcı/sunucu uygulaması olarak çalışmasını istiyorsanız, uygulama Sihirbazı 'ndaki OLE seçenekleri iletişim kutusunda bu seçeneği belirleyin ve bu destek otomatik olarak oluşturulur. Daha fazla bilgi için bkz. [genel bakış: ActiveX Denetim kapsayıcısı oluşturma](../mfc/reference/creating-an-mfc-activex-control-container.md). MFC örnekleri hakkında daha fazla bilgi için bkz. [MFC örnekleri](../overview/visual-cpp-samples.md#mfc-samples).

MDI uygulamasını kendi içine ekleyemeyeceğinize unutmayın. Bir SDI uygulaması olmadığı müddetçe kapsayıcı/sunucu olan bir uygulama kendi kendine eklenemez.

##  <a name="links-to-embedded-objects"></a><a name="_core_links_to_embedded_objects"></a>Katıştırılmış nesne bağlantıları

Katıştırılmış nesne bağlantıları özelliği, bir kullanıcının kapsayıcı uygulamanızın içindeki katıştırılmış bir nesneye OLE bağlantısı olan bir belge oluşturmasını sağlar. Örneğin, bir Word işlemcisinde ekli bir elektronik tablo içeren bir belge oluşturun. Uygulamanız gömülü nesnelere bağlantıları destekliyorsa, Word işlemcinin belgesinde yer alan elektronik tabloya bir bağlantı yapıştırabilir. Bu özellik, uygulamanızın elektronik tabloda bulunan bilgileri, sözcük işlemcisinin ilk olarak aldığı yeri bilmeden kullanmasına izin verir.

#### <a name="to-link-to-embedded-objects-in-your-application"></a>Uygulamanızdaki katıştırılmış nesnelere bağlantı sağlamak için

1. Belge sınıfınızı `COleDocument`yerine `COleLinkingDoc` türetirsiniz.

1. OLE geliştirme araçlarına dahil edilen sınıf KIMLIĞI oluşturucusunu kullanarak uygulamanız için bir OLE sınıfı KIMLIĞI (**CLSID**) oluşturun.

1. Uygulamayı OLE ile kaydedin.

1. Uygulama sınıfınızın bir üyesi olarak bir `COleTemplateServer` nesnesi oluşturun.

1. Uygulama sınıfınızın `InitInstance` üye işlevinde şunları yapın:

   - Nesnenin `ConnectTemplate` üye işlevini çağırarak `COleTemplateServer` nesneniz belge şablonlarınıza bağlayın.

   - Tüm sınıf nesnelerini OLE sistemine kaydetmek için `COleTemplateServer::RegisterAll` member işlevini çağırın.

   - `COleTemplateServer::UpdateRegistry`çağırın. Uygulamanın "/Embedded" anahtarıyla başlatılmadığından `UpdateRegistry` için tek parametre *OAT_CONTAINER* olmalıdır. Bu, uygulamayı gömülü nesnelere bağlantıları destekleyebilen bir kapsayıcı olarak kaydeder.

      Uygulama "/Embedded" anahtarıyla başlatılırsa, bir sunucu uygulamasına benzer şekilde ana penceresini göstermemelidir.

MFC OLE örnek [Oclient](../overview/visual-cpp-samples.md) bu özelliği uygular. Bunun nasıl yapıldığını gösteren bir örnek için, Oclient içindeki `InitInstance` işlevine bakın *.* Bu örnek UYGULAMANıN cpp dosyası.

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](../mfc/containers.md)<br/>
[Sunucular](../mfc/servers.md)
