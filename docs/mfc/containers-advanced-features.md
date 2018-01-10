---
title: "Kapsayıcılar: Gelişmiş Özellikler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e79b1c88996e835a907129fa5810d4c4dca0770
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="containers-advanced-features"></a>Kapsayıcılar: Gelişmiş Özellikler
Bu makalede, isteğe bağlı Gelişmiş Özellikler varolan kapsayıcı uygulamalarına kavramak gereken adımları açıklar. Bu özellikler şunlardır:  
  
-   [Bir kapsayıcı ve sunucu bir uygulama](#_core_creating_a_container_server_application)  
  
-   [Katıştırılmış nesne için bir OLE bağlantısı](#_core_links_to_embedded_objects)  
  
##  <a name="_core_creating_a_container_server_application"></a>Bir kapsayıcı/sunucu uygulaması oluşturma  
 Kapsayıcı/sunucu uygulaması, bir kapsayıcı ve bir sunucu gibi davranan bir uygulamadır. Windows için Microsoft Word, bu bir örnektir. Windows için Word belgeleri diğer uygulamalarda eklenebilir ve Windows için Word belgelerinde öğeleri de eklenebilir. Bir kapsayıcı ve (bir birleşimi kapsayıcı/miniserver uygulaması oluşturamazsınız) tam bir sunucu, kapsayıcı uygulamanızın değiştirme işlemi, bir tam sunucu oluşturma işlemi benzerdir.  
  
 Makaleyi [sunucular: sunucu uygulama](../mfc/servers-implementing-a-server.md) bir sunucu uygulaması uygulamak için gereken görevleri sayısını listeler. Bir kapsayıcı/sunucu uygulaması için bir kapsayıcı uygulama dönüştürürseniz, daha sonra aynı bu görevlerden bazılarını gerçekleştirmek kapsayıcıya kod ekleme gerekir. Aşağıda, dikkate alınması gereken önemli şeyler listelenmektedir:  
  
-   Uygulama Sihirbazı tarafından önceden oluşturulmuş kapsayıcı kodu OLE alt sistemi başlatır. Değiştirme veya ekleme desteği için herhangi bir şey gerekmez.  
  
-   Yerde bir belge sınıfın temel sınıf olan `COleDocument`, temel sınıf değiştirmek `COleServerDoc`.  
  
-   Geçersiz kılma `COleClientItem::CanActivate` yerinde düzenlemek için sunucu kullanılırken yerinde öğelerini düzenleme önlemek için.  
  
     Örneğin, MFC OLE örnek [OCLIENT](../visual-cpp-samples.md) kapsayıcı/sunucu uygulamanız tarafından oluşturulan bir öğe katıştırılmış. OCLIENT uygulamasını açın ve yerinde kapsayıcı/sunucu uygulamanız tarafından oluşturulan öğeyi düzenle. Uygulamanızın öğesi düzenlerken, MFC OLE örneği tarafından oluşturulan bir madde katıştır istemediğinize karar [HIERSVR](../visual-cpp-samples.md). Bunu yapmak için yerinde etkinleştirme kullanamazsınız. Bu öğe etkinleştirmek için HIERSVR tam olarak açmanız gerekir. Microsoft Foundation Class Kitaplığı Bu OLE özelliğini desteklemediği için geçersiz kılma `COleClientItem::CanActivate` , bu durumda denetlemek ve olası çalışma zamanı hata uygulamanızda önlemek sağlar.  
  
 Yeni bir uygulama oluşturma ve bir kapsayıcı/sunucu uygulaması olarak çalışabilmesi için istiyorsanız Uygulama Sihirbazı'nı ve bu destek OLE Seçenekleri iletişim kutusundaki seçeneği otomatik olarak oluşturulacağını seçin. Daha fazla bilgi için bkz: [genel bakış: bir ActiveX denetimi kapsayıcısı oluşturma](../mfc/reference/creating-an-mfc-activex-control-container.md). MFC örnekleri MFC örnekleri hakkında daha fazla bilgi için bkz.  
  
 Kendi içine bir MDI uygulama ekleyemiyor unutmayın. SDI uygulama olmadığı sürece bir kapsayıcı/sunucu uygulamanın kendi içine eklenemez.  
  
##  <a name="_core_links_to_embedded_objects"></a>Katıştırılmış nesneler bağlantılar  
 Katıştırılmış nesneler özelliği bağlanan bir belge kapsayıcı uygulamanızı içine katıştırılmış nesne için bir OLE bağlantısı oluşturmak bir kullanıcı sağlar. Örneğin, bir sözcük işlemci katıştırılmış bir elektronik tablo içeren bir belge oluşturun. Katıştırılmış nesneler bağlantılar uygulamanız destekliyorsa, word işlemcinin belgedeki elektronik tablo bağlantısını yapıştırın. Bu özellik, burada sözcük işlemci başlangıçta var bilmeden elektronik tabloda yer alan bilgileri kullanmak için uygulamanızı sağlar.  
  
#### <a name="to-link-to-embedded-objects-in-your-application"></a>Katıştırılmış nesneler, uygulamanızda bağlamak için  
  
1.  Belge sınıfından türetilen `COleLinkingDoc` yerine `COleDocument`.  
  
2.  OLE sınıfı kimlik oluşturun (**CLSID**) sınıf kimliği OLE geliştirme araçları ile dahil Oluşturucu kullanarak uygulamanız için.  
  
3.  Uygulamayı OLE ile kaydedin.  
  
4.  Oluşturma bir `COleTemplateServer` uygulama sınıfınızda bir üyesi olarak nesne.  
  
5.  Uygulama sınıfınızın içinde `InitInstance` üye işlev, aşağıdakileri yapın:  
  
    -   Bağlanma, `COleTemplateServer` nesnenin çağırarak belge şablonlarınızı nesnesine `ConnectTemplate` üye işlevi.  
  
    -   Çağrı **COleTemplateServer::RegisterAll** tüm sınıf nesnelerine OLE sistemine kayıt için üye işlevi.  
  
    -   Çağrı `COleTemplateServer::UpdateRegistry`. Tek parametre `UpdateRegistry` olmalıdır `OAT_CONTAINER` uygulama "/ katıştırılmış" anahtarıyla başlatılmadığı durumunda. Bu uygulama katıştırılmış nesnelere bağlantılarını desteklemek bir kapsayıcı olarak kaydeder.  
  
         Uygulama "/ katıştırılmış" anahtarıyla başlatılırsa, kendi ana penceresinde, bir sunucu uygulaması için benzer göstermelidir değil.  
  
 MFC OLE örnek [OCLIENT](../visual-cpp-samples.md) bu özellik uygular. Bunun nasıl yapılacağı ilişkin bir örnek için bkz: `InitInstance` OCLIENT işlevinde. Bu örnek uygulama CPP dosyası.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kapsayıcıları](../mfc/containers.md)   
 [Sunucular](../mfc/servers.md)

