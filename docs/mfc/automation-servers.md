---
title: Otomasyon sunucuları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 337d5a1ec25e8fc80cf867aecef0452b1d03fb2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="automation-servers"></a>Otomasyon Sunucuları
Otomasyon nesneleri başka bir uygulamaya uygulanan işlemek için ya da bunlar işlenebilir nesnelerini ortaya çıkarmak için uygulamanız için mümkün kılar. Otomasyon sunucusu (Otomasyon nesneleri olarak adlandırılır) programlanabilir nesneleri başka uygulamalar için kullanıma sunan bir uygulamasıdır (adlı [Otomasyon istemcileri](../mfc/automation-clients.md)). Otomasyon sunucuları bazen Otomasyon bileşenleri olarak adlandırılır.  
  
 Otomasyon nesneleri gösterme nesneleri doğrudan erişerek bazı yordamları otomatikleştirmek için istemcileri etkinleştirir ve işlevselliği sunucu kullanılabilir hale getirir. Uygulamaların diğer uygulamalar için yararlı olan işlevselliği sağladığınızda, nesneleri bu şekilde gösterme faydalıdır. Örneğin, diğer programları kullanabilmesi sözcük işlemci yazım denetimi işlevselliğini doğurabilir. Nesneleri riskini böylece diğer uygulamaları hazır işlevselliğini kullanarak kendi uygulamalarında işlevselliğini geliştirmek üzere satıcılar sağlar.  
  
 Bu Otomasyon nesneleri kendi dış arabirimi olarak özellikleri ve yöntemleri vardır. Otomasyon nesnesi özniteliklerini adlandırılmış özellikler. Özellikler veri C++ sınıfı gibi üyeleridir. Otomasyon nesneler üzerinde çalışan işlevler yöntemleridir. C++ sınıfı gibi ortak üye işlevleri yöntemleridir.  
  
> [!NOTE]
>  C++ veri üyeleri gibi özellikleri olsa da, bunlar doğrudan erişilebilir değildir. Saydam erişim sağlamak için bir iç değişken get/set üye işlevleri çifti ile Otomasyon nesnesindeki bunlara erişmek için ayarlayın.  
  
 Uygulama işlevselliği ortak, iyi tanımlanmış bir arabirim aracılığıyla göstererek Otomasyonu, bir tek genel programlama dilinde yerine Microsoft Visual Basic gibi çeşitli, uygulamaya özgü makrosu uygulamalarda derleme mümkün kılar Diller.  
  
##  <a name="_core_support_for_automation_servers"></a> Otomasyon sunucuları desteği  
 Visual C++ ve MFC çerçevesi otomasyon sunucuları için kapsamlı destek sağlar. Uygulamanın işlevselliğini çabalarınız odaklanabilirsiniz bir Otomasyon sunucusu yaparken söz konusu yükünü çoğunu işleyin.  
  
 Otomasyon desteklemek için framework'ün asıl gönderme eşlemesi, bildirimler ve yöntemleri ve özellikleri için OLE kullanıma sunmak için gereken çağrıları genişler makroları birtakım mekanizmadır. Tipik gönderme harita şöyle görünür:  
  
 [!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]  
  
 Sınıf Görünümü ve Özellikler penceresini eşlemeleri dağıtma bakımıyla yardımcı. Bir sınıfa yeni yöntemi veya özelliği eklediğinizde, Visual C++ karşılık gelen ekler `DISP_FUNCTION` veya `DISP_PROPERTY` makrosu gösteren sınıf adı, yöntemi veya özelliği ve veri türlerinin iç ve dış adlarını parametrelere sahip.  
  
 **Sınıfı Ekle** iletişim kutusu ayrıca Otomasyon sınıfları bildirimi ve bunların özelliklerini ve işlemlerini yönetimini basitleştirir. Projeniz için bir sınıf eklemek için Sınıf Ekle iletişim kutusu kullandığınızda devralınabilir. taban sınıf belirtin. Taban Sınıf Otomasyonu izin veriyorsa, Sınıf Ekle iletişim kutusu denetimleri yeni sınıf Otomasyonu, desteklemesi gerekip gerekmediğini "creatable OLE (diğer bir deyişle, olup nesneleri sınıfının bir COM istemciden istek üzerine oluşturulabilir)" olup olmadığını belirtmek için kullanın görüntüler. ve kullanmak COM istemcisi için dış adı.  
  
 **Sınıfı Ekle** iletişim kutusunda daha sonra bir sınıf bildirimi oluşturur, OLE özellikleri için uygun makroları de dahil olmak üzere belirtmiş. Ayrıca, sınıfınızın üye işlevleri uyarlamasını iskelet kodunu ekler.  
  
 MFC Uygulama Sihirbazı'nı devre dışı zemin Otomasyon sunucu uygulamanızı alınırken adımlar basitleştirir. Seçerseniz **Otomasyon** onay kutusundan **Gelişmiş Özellikler** sayfasında, MFC Uygulama Sihirbazı'nı, uygulamanızın ekler `InitInstance` Automation'ınızı kaydetmek için gereken çağrılarını işlevi nesneleri ve Otomasyon sunucusu olarak uygulamanızı çalıştırın.  
  
### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz  
  
-   [Otomasyon istemcileri hakkında bilgi edinin](../mfc/automation-clients.md)  
  
-   [CCmdTarget sınıfı hakkında daha fazla bilgi edinin](../mfc/reference/ccmdtarget-class.md)  
  
-   [Sınıf COleDispatchDriver hakkında daha fazla bilgi edinin](../mfc/reference/coledispatchdriver-class.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomasyon](../mfc/automation.md)   
 [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)

