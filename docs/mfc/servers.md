---
title: "Sunucuları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC]
- OLE server applications [MFC], activation
- full-server
- servers
- mini-server
- OLE server applications [MFC], server types
- server applications [MFC]
ms.assetid: e45172e8-eae3-400a-8139-0fa009a42fdc
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: be83831c79b398de9e9b0791d172cf7608e322aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="servers"></a>Sunucular
Bir sunucu uygulaması (veya bileşen uygulama) OLE öğeleri (veya bileşenleri) kullanmak için kapsayıcı uygulamaları tarafından oluşturur. Görsel düzenleme sunucu uygulaması, görsel düzenleme veya yerinde etkinleştirme de destekler. OLE sunucu başka bir biçimidir bir [Otomasyon sunucusu](../mfc/automation-servers.md). Bazı sunucu uygulamaları yalnızca katıştırılmış öğeleri oluşturulmasını destekler; Başkalarının katıştırılmış ve bağlantılı öğeler oluşturulmasını destekler. Bu nadir olmasına rağmen bazı yalnızca bağlama destekler. Kullanıcı bir öğeyi düzenlemek istediğinde tüm sunucu uygulamaları tarafından kapsayıcı uygulamaları etkinleştirme desteklemesi gerekir. Bir uygulama, bir kapsayıcı ve bir sunucu olabilir. Diğer bir deyişle, onu hem de kendi belgelerine verileri birleştirmek ve diğer uygulamaların belgelerine öğeleri olarak birleştirilebilir veri oluşturun.  
  
 Bir miniserver yalnızca kapsayıcı tarafından başlatılan sunucu uygulaması özel bir türde değil. Microsoft Draw ve Microsoft Graph miniservers örnekleridir. Bir miniserver diskteki dosyaları olarak belgeleri depolamaz. Bunun yerine, kendi belgelerini okur ve onları kapsayıcılara ait belgelerde öğelerine yazar. Sonuç olarak, bir miniserver, bağlama değil yalnızca katıştırma destekler.  
  
 Tam sunucu, tek başına bir uygulama olarak çalıştırın veya bir kapsayıcı uygulama tarafından başlatılan. Tam sunucu belgeleri diskteki dosyaları olarak depolayabilirsiniz. Yalnızca her iki katıştırma katıştırma ve bağlama ya da yalnızca bağlama destekleyebilir. Bir kapsayıcı uygulama kullanıcı, sunucu ve kapsayıcısında Yapıştır komut kesme veya kopyalama komutu seçerek katıştırılmış bir öğe oluşturabilirsiniz. Bağlantılı bir öğe kopyalama sunucusu ve Bağlantı Yapıştır komutunu kapsayıcısında seçerek oluşturulur. Alternatif olarak, kullanıcı bir katıştırılmış veya bağlantılı bir öğe Nesne Ekle iletişim kutusunu kullanarak oluşturabilirsiniz.  
  
 Aşağıdaki tabloda sunucuları farklı türdeki özellikleri özetlenmektedir:  
  
### <a name="server-characteristics"></a>Sunucu Özellikleri  
  
|Sunucu türü|Birden çok örneği destekler|Belge başına öğe sayısı|Örneği başına belgeleri|  
|--------------------|---------------------------------|------------------------|----------------------------|  
|Miniserver|Evet|1.|1.|  
|SDI tam sunucu|Evet|1 (bağlama destekleniyorsa, 1 veya daha fazla)|1.|  
|MDI tam sunucu|Hayır (gerekli değil)|1 (bağlama destekleniyorsa, 1 veya daha fazla)|0 veya daha fazla|  
  
 Birden fazla kapsayıcı katıştırılmış veya bağlantılı bir öğe düzenlemek için kullanılan olay, bir sunucu uygulaması aynı anda birden çok kapsayıcı desteklemelidir. Sunucu bir SDI uygulama (veya bir iletişim kutusu arabirimle miniserver) ise, sunucunun birden çok örneği aynı anda çalıştırabilirsiniz olması gerekir. Bu uygulamanın her kapsayıcı isteği işlemek için ayrı bir örneğini sağlar.  
  
 Sunucu bir MDI uygulama ise, bir kapsayıcı öğe düzenlemek için gereken her zaman yeni bir MDI alt pencere oluşturabilirsiniz. Bu şekilde, birden çok kapsayıcı uygulama tek bir örneğini destekler.  
  
 Sunucu uygulamanızı OLE sistem DLL'leri başka bir kapsayıcı hizmetlerini istediğinde sunucunun bir örneği zaten çalışıyor olursa Yapılacaklar söylemelisiniz: olup, sunucu yeni bir örneğini başlatabilir veya bir örneğine tüm kapsayıcıları isteklerini doğrudan Sunucu.  
  
 Sunucuları hakkında daha fazla bilgi için bkz:  
  
-   [Sunucular: sunucu uygulama](../mfc/servers-implementing-a-server.md)  
  
-   [Sunucular: Sunucu belgeleri uygulama](../mfc/servers-implementing-server-documents.md)  
  
-   [Sunucular: Yerinde çerçeve pencereleri uygulama](../mfc/servers-implementing-in-place-frame-windows.md)  
  
-   [Sunucular: Sunucu öğeleri](../mfc/servers-server-items.md)  
  
-   [Sunucular: Kullanıcı arabirimi sorunları](../mfc/servers-user-interface-issues.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE](../mfc/ole-in-mfc.md)   
 [Kapsayıcıları](../mfc/containers.md)   
 [Kapsayıcılar: Gelişmiş Özellikler](../mfc/containers-advanced-features.md)   
 [Menüler ve kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)   
 [Kayıt](../mfc/registration.md)   
 [Otomasyon sunucuları](../mfc/automation-servers.md)

