---
title: ASP, ATL Active Server sayfası Bileşen Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.asp.asp
dev_langs:
- C++
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfe27a64a2086f08c5a29e2961d069771fdbc4e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356145"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP, ATL Active Server sayfası Bileşen Sihirbazı
Bilgileri ve durumu, ASP bileşenle ilgili işlemek için isteğe bağlı ayarları belirtmek için bu sayfayı ATL etkin sunucu sayfası Bileşen Sihirbazı'nı kullanın.  
  
 **İsteğe bağlı yöntemler**  
 İsteğe bağlı ASP yöntemleri ekler **OnStartPage** ve **OnEndPage**, nesnenize. Bu seçenek, Active Server Pages iç nesneleri ayarlamak için seçilmelidir. Varsayılan olarak, seçili.  
  
-   **OnStartPage/OnEndPage** [OnStartPage](https://msdn.microsoft.com/library/ms691624.aspx) komut dosyası çalıştığında nesneye erişmek için ilk kez çağrılır. **OnEndPage** nesne tamamlandığında adlı komut dosyasını işleme.  
  
 **İç nesne**  
 Seçmelisiniz **OnStartPage/OnEndPage** tüm ASP iç nesneler ayarlamak üzere seçeneği.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**İstek**|Active Server Pages iç erişim sağlayan **isteği** nesnesi. İstek nesnesi bir HTTP isteği geçirmek için kullanılır.|  
|**Yanıt**|Active Server Pages iç erişim sağlayan **yanıt** nesnesi. Bir isteğe yanıt olarak, yanıt nesnesini bilgileri kullanıcıya tarayıcıya gönderir.|  
|**Oturum**|Active Server Pages iç erişim sağlayan **oturum** nesnesi. **Oturum** nesne depolamak ve durum bilgilerini alma dahil olmak üzere geçerli kullanıcı oturum bilgilerini korur.|  
|**Uygulama**|Active Server Pages iç erişim sağlayan **uygulama** nesnesi. **Uygulama** nesnesi birden çok ASP nesne arasında paylaşılan durumu yönetir.|  
|**Sunucu**|Active Server Pages iç erişim sağlayan **Server** nesnesi. **Server** nesne diğer ASP nesneleri oluşturmanıza olanak sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Active Server sayfası Bileşen Sihirbazı](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server sayfası bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)

