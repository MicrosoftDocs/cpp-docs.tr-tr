---
title: Otomasyon istemcileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4a4327e1c3e4d65c5bdc3b822cf2cdfc1ec0353
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820600"
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

Otomasyon istemcinizi olayları işlemek istiyorsanız, bir havuzu arabirimini eklemeniz gerekir. MFC ActiveX denetimleri için havuz arabirimler, ancak diğer COM sunucuları için desteklemiyor için sihirbaz desteği sağlar. COM sunucuları tarafından tanımlanan kaynak arabirimleri için MFC istemcisinde havuzu arabirimini ekleme hakkında daha fazla bilgi için bkz: nasıl yapılır: bir havuz arabiriminde MFC-Based COM istemcisi (KB 181845) oluşturmak [ http://support.microsoft.com/default.aspxscid=kb; 181845](http://support.microsoft.com/default.aspxscid=kb;181845).

## <a name="see-also"></a>Ayrıca Bkz.

[Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma](../mfc/automation-clients-using-type-libraries.md)<br/>
[Otomatikleştirme](../mfc/automation.md)<br/>
[MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)

