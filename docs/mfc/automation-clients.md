---
title: Otomasyon İstemcileri
ms.date: 11/04/2016
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
ms.openlocfilehash: 098c41ea981d9d0069130d5439632aa7b0d6cbbd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304502"
---
# <a name="automation-clients"></a>Otomasyon İstemcileri

Otomasyon, uygulamanız nesneleri başka bir uygulamaya uygulanan değiştirmek ya da bunlar işlenebilir nesneleri kullanıma sunmak için mümkün kılar. Bir otomasyon istemci, sunulan nesneleri başka bir uygulamaya ait işleyebileceğiniz bir uygulamadır. Nesneleri ortaya koyan uygulamayı Otomasyon sunucusu olarak adlandırılır. İstemci, sunucu uygulamasının nesneleri bu nesnelerin özellikleri ve işlevleri erişerek yönetir.

### <a name="types-of-automation-clients"></a>Otomasyon istemcileri türleri

Otomasyon istemcileri iki tür vardır:

- İstemciler, dinamik olarak (çalışma zamanında) işlem sunucusunun ve özellikleri hakkında bilgi edinin.

- Özellik ve sunucu işlemlerini belirtir (derleme zamanında sağlanan) statik bilgilerini sahip istemcilerin.

İlk tür istemcileri OLE sistemin sorgulayarak sunucunun yöntemleri ve özellikleri hakkında bilgi edinme `IDispatch` mekanizması. Dinamik istemciler için yeterli olmakla `IDispatch` temelli gerekir bilinir, nesneleri derleme zamanı burada statik istemciler için kullanılacak zordur. Statik bağlı istemciler için Microsoft Foundation sınıfları sağlayan [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) sınıfı.

Statik bağlı istemciler, istemci uygulaması ile statik olarak bağlanan bir proxy sınıfı kullanır. Bu sınıf, bir tür kullanımı uyumlu C++ kapsülleme sunucu uygulamasının özellikleri ve işlemleri sağlar.

Sınıf `COleDispatchDriver` asıl otomasyon istemci tarafı desteği sağlar. Kullanarak **Yeni Öğe Ekle** iletişim kutusu, türetilen bir sınıf oluşturma `COleDispatchDriver`.

Ardından sunucu uygulamasının nesnesinin işlevlerini ve özelliklerini açıklayan tür kitaplığı dosyası belirtin. Öğe Ekle iletişim kutusunda bu dosyasını okur ve oluşturur `COleDispatchDriver`-türetilmiş bir tür kullanımı uyumlu şekilde sunucu uygulamasının nesnelerinin C++ erişmek için uygulamanızı çağırabilir üye işlevleri ile bir sınıf. Ek işlevler öğesinden devralınan `COleDispatchDriver` uygun Otomasyon sunucusu çağırma işlemini basitleştirir.

### <a name="handling-events-in-automation-clients"></a>Otomasyon istemcileri olayları işleme

Otomasyon istemcinizi olayları işlemek istiyorsanız, bir havuzu arabirimini eklemeniz gerekir. MFC ActiveX denetimleri için havuz arabirimler, ancak diğer COM sunucuları için desteklemiyor için sihirbaz desteği sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Otomasyon istemcileri: Tür kitaplıklarını kullanma](../mfc/automation-clients-using-type-libraries.md)<br/>
[Otomatikleştirme](../mfc/automation.md)<br/>
[MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)
