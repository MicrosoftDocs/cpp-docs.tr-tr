---
title: Otomasyon İstemcileri
ms.date: 11/04/2016
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
ms.openlocfilehash: 9c34f6fccd06635dfb686e6eb1f2cf895bb86989
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626077"
---
# <a name="automation-clients"></a>Otomasyon İstemcileri

Otomasyon, uygulamanızın başka bir uygulamada uygulanan nesneleri işlemesini veya işlenebilmeleri için nesneleri kullanıma sunmasını mümkün kılar. Otomasyon istemcisi, başka bir uygulamaya ait gösterilen nesneleri işleyebileceğiniz bir uygulamadır. Nesneleri kullanıma sunan uygulamaya Otomasyon sunucusu denir. İstemci, bu nesnelerin özelliklerine ve işlevlerine erişerek sunucu uygulamasının nesnelerini yönetir.

### <a name="types-of-automation-clients"></a>Otomasyon Istemcilerinin türleri

İki tür Otomasyon istemcisi vardır:

- Dinamik olarak (çalışma zamanında) istemci, sunucunun özellikleri ve işlemleri hakkında bilgi elde edin.

- Sunucusunun özelliklerini ve işlemlerini belirten statik bilgilere (derleme sırasında sağlanmış) sahip istemciler.

İlk türdeki istemciler, OLE sisteminin mekanizmasını sorgulayarak sunucunun yöntemleri ve özellikleri hakkında bilgi elde edin `IDispatch` . Dinamik istemciler için kullanılması yeterlidir, ancak, `IDispatch` yürütülen nesnelerin derleme zamanında bilinmesi gereken statik istemciler için kullanılması zordur. Statik bağlantılı istemciler için, Microsoft Foundation sınıfları [Cotadispatchdriver](reference/coledispatchdriver-class.md) sınıfını sağlar.

Statik bağlı istemciler, istemci uygulamasıyla statik olarak bağlanmış bir proxy sınıfı kullanır. Bu sınıf, sunucu uygulamasının özelliklerini ve işlemlerini bir tür açısından güvenli C++ kapsüllemesini sağlar.

Sınıfı, `COleDispatchDriver` otomasyonun istemci tarafı için sorumlu desteği sağlar. **Yeni öğe Ekle** iletişim kutusunu kullanarak öğesinden türetilmiş bir sınıf oluşturursunuz `COleDispatchDriver` .

Ardından, sunucu uygulamasının nesnesinin özelliklerini ve işlevlerini açıklayan tür kitaplığı dosyasını belirtirsiniz. Öğe Ekle iletişim kutusu bu dosyayı okur ve `COleDispatchDriver` uygulama işlevleri ile türetilmiş bir sınıf oluşturur ve uygulamanızın C++ içindeki nesne nesnelerine tür kullanımı açısından güvenli bir şekilde erişmesini çağırabilir. Kaynağından devralınan ek işlevler `COleDispatchDriver` , doğru Otomasyon sunucusunu çağırma sürecini basitleştirir.

### <a name="handling-events-in-automation-clients"></a>Otomasyon Istemcilerinde olayları işleme

Otomasyon istemcinizdeki olayları işlemek istiyorsanız, bir havuz arabirimi eklemeniz gerekir. MFC, ActiveX denetimlerine yönelik havuz arabirimlerini eklemek için sihirbaz desteği sağlar, ancak diğer COM sunucuları için desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma](automation-clients-using-type-libraries.md)<br/>
[Otomasyon](automation.md)<br/>
[MFC Uygulama Sihirbazı](reference/mfc-application-wizard.md)
