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
ms.openlocfilehash: 350431975a4335fc06e436237b7e0d3388faab64
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152936"
---
# <a name="containers-advanced-features"></a>Kapsayıcılar: Gelişmiş Özellikler

Bu makalede, isteğe bağlı Gelişmiş Özellikler mevcut kapsayıcı uygulamalarınızı birleştirmek gereken adımları açıklar. Bu özellikler şunlardır:

- [Bir kapsayıcı hem bir sunucu bir uygulama](#_core_creating_a_container_server_application)

- [Katıştırılmış nesne için bir OLE bağlantısı](#_core_links_to_embedded_objects)

##  <a name="_core_creating_a_container_server_application"></a> Kapsayıcı/sunucu uygulaması oluşturma

Kapsayıcı/sunucu uygulaması, bir kapsayıcı ve bir sunucu gibi davranan bir uygulamadır. Windows için Microsoft Word, bu bir örnektir. Word için Windows belgeleri diğer uygulamalarda ekleyebilir ve Word için Windows belgelerine öğeleri de ekleyebilir. Kapsayıcı uygulamanızı bir kapsayıcı hem (bir birleşimi kapsayıcı/miniserver uygulama oluşturamaz) tam bir sunucu olarak değiştirme işlemi, bir tam sunucu oluşturma işlemi benzerdir.

Makaleyi [sunucuları: Sunucu uygulama](../mfc/servers-implementing-a-server.md) bir sunucu uygulaması uygulamak için gereken görevlerin sayısını listeler. Kapsayıcılı bir uygulama bir kapsayıcı/sunucu uygulaması dönüştürün, sonra aynı bu görevlerden bazılarını gerçekleştirmek kapsayıcıya kod ekleme gerekir. Dikkate alınması gereken önemli noktalar aşağıda listelenmiştir:

- Uygulama Sihirbazı tarafından önceden oluşturulmuş kapsayıcı kod OLE alt başlatır. Değiştirme veya ekleme desteği için herhangi bir şey gerekmez.

- Bir belge sınıfının temel sınıfı olduğu her durumda `COleDocument`, temel sınıfa değiştirme `COleServerDoc`.

- Geçersiz kılma `COleClientItem::CanActivate` sunucu yerinde düzenleme için kullanıldığı sırada öğeleri yerinde düzenleme önlemek için.

   Örneğin, MFC OLE örnek [OCLIENT](../overview/visual-cpp-samples.md) kapsayıcı/sunucu uygulamanız tarafından oluşturulan bir öğe katıştırılmış. OCLIENT uygulamayı açın ve yerinde kapsayıcı/sunucu uygulamanız tarafından oluşturulan öğenin düzenleyin. Uygulamanızın öğe düzenlenirken, MFC OLE örnek tarafından oluşturulan bir öğe eklemek istediğinize karar [HIERSVR](../overview/visual-cpp-samples.md). Bunu yapmak için yerinde etkinleştirme kullanamazsınız. Tam olarak bu öğesini etkinleştirmek için HIERSVR açmanız gerekir. Microsoft Foundation Class Kitaplığı Bu OLE özellik desteklemediği için geçersiz kılma `COleClientItem::CanActivate` bu durum için denetleyin ve uygulamanızdaki olası bir çalışma zamanı hatası önlemeye olanak tanır.

Yeni bir uygulama oluşturma ve kapsayıcı/sunucu uygulaması çalışabilmesi için istediğiniz seçeneği Uygulama Sihirbazı'nı ve bu destek OLE Seçenekler iletişim kutusundaki otomatik olarak oluşturulması'ı seçin. Daha fazla bilgi için bkz [genel bakış: Bir ActiveX denetimi kapsayıcısı oluşturma](../mfc/reference/creating-an-mfc-activex-control-container.md). MFC örnekleri MFC örnekleri hakkında daha fazla bilgi için bkz.

Kendi içine bir MDI uygulaması ekleyemeyeceğinizi unutmayın. Bir SDI uygulaması olmadığı sürece, bir kapsayıcı/sunucu olmayan bir uygulamanın kendi içine eklenemiyor.

##  <a name="_core_links_to_embedded_objects"></a> Katıştırılmış nesneler bağlantılar

Katıştırılmış nesneler özellik bağlanan kapsayıcı uygulamanızı içine katıştırılmış nesne için bir OLE bağlantısını içeren bir belge oluşturmak bir kullanıcı etkinleştirir. Örneğin, bir sözcük işlemcisi katıştırılmış bir elektronik tablo içeren bir belge oluşturun. Katıştırılmış nesneler bağlantılar uygulamanız destekliyorsa, word işlemcinin belgedeki elektronik bağlantısını yapıştırabilirsiniz. Bu özellik, uygulamanızın nerede sözcük işlemci başlangıçta anladım bilmeden elektronik tabloda yer alan bilgileri kullanmasına olanak sağlar.

#### <a name="to-link-to-embedded-objects-in-your-application"></a>Katıştırılmış nesneler uygulamanızı bağlamak için

1. Belge sınıfından türetilir `COleLinkingDoc` yerine `COleDocument`.

1. Bir OLE sınıf kimliği oluşturun (**CLSID**) sınıf kimliği OLE geliştirme araçları ile dahil Oluşturucu kullanarak uygulamanız için.

1. OLE ile uygulamayı kaydedin.

1. Oluşturma bir `COleTemplateServer` uygulama sınıfınızın bir üye olarak nesnesi.

1. Uygulama sınıfın içinde `InitInstance` üye işlev, aşağıdakileri yapın:

   - Bağlanma, `COleTemplateServer` nesnenin çağırarak belge şablonlarınızı nesnesine `ConnectTemplate` üye işlevi.

   - Çağrı `COleTemplateServer::RegisterAll` tüm sınıf nesnelerine OLE sistemine kaydetmek için üye işlevi.

   - Çağrı `COleTemplateServer::UpdateRegistry`. Tek parametre `UpdateRegistry` olmalıdır *oat_contaıner* uygulama "/ katıştırılmış" anahtarıyla başlatılmaz. Bu uygulama bağlantılar katıştırılmış nesneleri destekleyen bir kapsayıcı olarak kaydeder.

         If the application is launched with the "/Embedded" switch, it should not show its main window, similar to a server application.

MFC OLE örnek [OCLIENT](../overview/visual-cpp-samples.md) bu özelliği uygular. Bunun nasıl yapıldığına bir örnek için bkz `InitInstance` işlevi *OCLIENT. CPP* Bu örnek uygulamanın dosya.

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](../mfc/containers.md)<br/>
[Sunucular](../mfc/servers.md)
