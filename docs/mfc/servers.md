---
description: 'Daha fazla bilgi edinin: sunucular'
title: Sunucular
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC]
- OLE server applications [MFC], activation
- full-server
- servers
- mini-server
- OLE server applications [MFC], server types
- server applications [MFC]
ms.assetid: e45172e8-eae3-400a-8139-0fa009a42fdc
ms.openlocfilehash: 5e9a9dd7cbb1ab237712b5ad0c84e3114a119ee3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217308"
---
# <a name="servers"></a>Sunucular

Sunucu uygulaması (veya bileşen uygulaması), kapsayıcı uygulamaları tarafından kullanılmak üzere OLE öğeleri (veya bileşenleri) oluşturur. Görsel olarak düzenlenen bir sunucu uygulaması da görsel düzenlemeler veya yerinde etkinleştirmeyi destekler. Başka bir OLE sunucusu biçimi de [Otomasyon sunucusudur](../mfc/automation-servers.md). Bazı sunucu uygulamaları yalnızca katıştırılmış öğelerin oluşturulmasını destekler; Başkaları hem katıştırılmış hem de bağlantılı öğelerin oluşturulmasını destekler. Bazı destek yalnızca bağlantı kurarak, ancak nadir bir durumdur. Tüm sunucu uygulamaları, Kullanıcı bir öğeyi düzenlemek istediğinde kapsayıcı uygulamalara etkinleştirmeyi desteklemelidir. Bir uygulama hem kapsayıcı hem de sunucu olabilir. Diğer bir deyişle, her ikisi de belgelerine veri ekleyebilir ve diğer uygulamaların belgelerine öğe olarak dahil edilebilir veriler oluşturabilir.

Minıver, yalnızca bir kapsayıcı tarafından başlatılabilen özel bir tür sunucu uygulamasıdır. Microsoft Draw ve Microsoft Graph, miniservers örnekleri. Minıver, belgeleri diskte dosya olarak depolamaz. Bunun yerine, belgelerini öğesinden okur ve kapsayıcılara ait belgelerdeki öğeleri bunlara yazar. Sonuç olarak, bir minıver bağlama değil yalnızca katıştırmayı destekler.

Tam sunucu tek başına bir uygulama olarak çalıştırılabilir veya bir kapsayıcı uygulaması tarafından başlatılabilir. Bir tam sunucu, belgeleri diskte dosya olarak saklayabilir. Yalnızca katıştırma, katıştırma ve bağlama veya yalnızca bağlama desteği sağlayabilir. Bir kapsayıcı uygulamasının kullanıcısı, sunucuda Kes veya Kopyala komutunu ve kapsayıcıdaki Yapıştır komutunu seçerek katıştırılmış bir öğe oluşturabilir. Bağlantılı bir öğe, kapsayıcıdaki Kopyala komutu ve kapsayıcıda Paste link komutu seçilerek oluşturulur. Alternatif olarak, Kullanıcı nesne Ekle iletişim kutusunu kullanarak katıştırılmış veya bağlantılı bir öğe oluşturabilir.

Aşağıdaki tabloda farklı sunucu türlerinin özellikleri özetlenmektedir:

### <a name="server-characteristics"></a>Sunucu özellikleri

|Sunucu türü|Birden çok örneği destekler|Belge başına öğe|Örnek başına belge|
|--------------------|---------------------------------|------------------------|----------------------------|
|Minıver|Evet|1|1|
|SDI tam sunucu|Evet|1 (bağlama destekleniyorsa, 1 veya daha fazla)|1|
|MDI tam sunucu|Hayır (zorunlu değil)|1 (bağlama destekleniyorsa, 1 veya daha fazla)|0 veya daha fazla|

Bir sunucu uygulaması, katıştırılmış veya bağlantılı bir öğeyi düzenlemek için birden fazla kapsayıcının kullanılacağı olayda aynı anda birden çok kapsayıcıyı desteklemelidir. Sunucu bir SDI uygulaması (veya bir iletişim kutusu arabirimine sahip bir mini sürüm) ise, sunucunun birden çok örneğinin aynı anda çalıştırılabilmesi gerekir. Bu, uygulamanın ayrı bir örneğinin her kapsayıcı isteğini işlemesini sağlar.

Sunucu bir MDI uygulamasıise, her kapsayıcının bir öğeyi düzenlemesini gerektiren her seferinde yeni bir MDI alt penceresi oluşturabilir. Bu şekilde, uygulamanın tek bir örneği birden çok kapsayıcıyı destekleyebilir.

Sunucu uygulamanız, başka bir kapsayıcı hizmetlerini istediğinde sunucunun bir örneği zaten çalışıyorsa OLE sistem dll 'Lerine ne yapılacağını anlatmalıdır: sunucunun yeni bir örneğini başlatıp çalıştırmayacağını ya da tüm kapsayıcıların isteklerini bir sunucu örneğine yönlendirmelidir.

Sunucular hakkında daha fazla bilgi için bkz.

- [Sunucular: sunucu uygulama](../mfc/servers-implementing-a-server.md)

- [Sunucular: sunucu belgeleri uygulama](../mfc/servers-implementing-server-documents.md)

- [Sunucular: In-Place çerçeve pencerelerini uygulama](../mfc/servers-implementing-in-place-frame-windows.md)

- [Sunucular: sunucu öğeleri](../mfc/servers-server-items.md)

- [Sunucular: User-Interface sorunları](../mfc/servers-user-interface-issues.md)

## <a name="see-also"></a>Ayrıca bkz.

[OLE](../mfc/ole-in-mfc.md)<br/>
[Kapsayıcılar](../mfc/containers.md)<br/>
[Kapsayıcılar: Gelişmiş Özellikler](../mfc/containers-advanced-features.md)<br/>
[Menüler ve kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Kaydını](../mfc/registration.md)<br/>
[Otomasyon sunucuları](../mfc/automation-servers.md)
