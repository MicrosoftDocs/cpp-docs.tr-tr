---
title: Otomasyon istemcileri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9cfb6aae5c947d1f36019e548c72b22a3304aa12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="automation-clients"></a>Otomasyon İstemcileri
Otomasyon nesneleri başka bir uygulamaya uygulanan işlemek için ya da bunlar işlenebilir nesnelerini ortaya çıkarmak için uygulamanız için mümkün kılar. Bir otomasyon istemci, başka bir uygulamaya ait gösterilen nesneleri işleyebileceğiniz bir uygulamadır. Nesneleri gösteren uygulama Otomasyon sunucusu adı verilir. İstemci, bu nesnelerin özelliklerini ve işlevlerini erişerek sunucu uygulamasının nesneleri yönetir.  
  
### <a name="types-of-automation-clients"></a>Otomasyon istemcileri türleri  
 Otomasyon istemcileri iki tür vardır:  
  
-   İstemciler, dinamik olarak (çalışma zamanında) özelliklerini ve sunucu işlemlerini hakkında bilgi edinin.  
  
-   Özelliklerini ve sunucu işlemlerini belirtir statik bilgileri (derleme zamanında sağlanır) sahip istemciler.  
  
 İlk tür istemcileri OLE sistemin sorgulayarak sunucunun yöntemleri ve özellikleri hakkında bilgi alma `IDispatch` mekanizması. Dinamik istemciler için kullanmak yeterli olmakla `IDispatch` burada güdümlü gereken bilinen adresindeki nesneleri derleme zamanı statik istemciler için kullanılacak zordur. Statik bağlı istemciler için Microsoft Foundation sınıfları sağlayan [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) sınıfı.  
  
 Statik bağımlı istemciler istemci uygulama ile statik olarak bağlantılı bir proxy sınıfını kullanın. Bu sınıf, bir tür kullanımı uyumlu C++ kapsülleme sunucu uygulamasının özelliklerini ve işlemlerin sağlar.  
  
 Sınıf `COleDispatchDriver` asıl otomasyon istemci tarafı desteği sağlar. Kullanarak `Add New Item` iletişim kutusunda, oluşturduğunuz türetilmiş bir sınıf `COleDispatchDriver`.  
  
 Ardından, özelliklerini ve işlevlerini sunucu uygulamasının nesnesinin açıklayan tür kitaplığı dosya de belirtin. Öğe Ekle iletişim kutusunda bu dosyasını okur ve oluşturur `COleDispatchDriver`-türetilmiş bir tür kullanımı uyumlu şekilde c++ sunucu uygulamasının nesnelere erişmek için uygulamanız çağırabilir üye işlevleri ile sınıf. Ek işlevsellik devralınan `COleDispatchDriver` uygun Otomasyon sunucusu çağırma işlemini basitleştirir.  
  
### <a name="handling-events-in-automation-clients"></a>Otomasyon istemcileri olayları işleme  
 Otomasyon İstemcisi'nde olayları işlemek istiyorsanız, bir havuz arabirimi eklemeniz gerekir. MFC ActiveX denetimleri için havuz arabirimlerini ekleyin, ancak diğer COM sunucuları için desteklemiyor için sihirbaz desteği sağlar. COM sunucuları tarafından tanımlanan kaynak arabirimleri için MFC istemcisinde bir havuz arabirimi ekleme hakkında daha fazla bilgi için bkz: nasıl yapılır: MFC-Based COM istemcisi (KB 181845) havuz arabiriminde oluşturmak [http://support.microsoft.com/default.aspxscid=kb;en-us; 181845](http://support.microsoft.com/default.aspxscid=kb;en-us;181845).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomasyon istemcileri: Tür kitaplıklarını kullanma](../mfc/automation-clients-using-type-libraries.md)   
 [Otomasyon](../mfc/automation.md)   
 [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)

