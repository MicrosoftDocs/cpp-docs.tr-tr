---
title: ASP, ATL Active Server Page bileşeni Sihirbazı | Microsoft Docs
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
ms.openlocfilehash: 63f945f90f6a862a3b16cd3dcc41859b0c21b984
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761950"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP, ATL Active Server Page bileşeni Sihirbazı

ATL Active Server sayfa bileşeni Sihirbazı bu sayfa, bilgileri ve durum, ASP bileşenle ilgili işlemek için isteğe bağlı ayarları belirtmek için kullanın.

**İsteğe bağlı yöntemler**  
İsteğe bağlı ASP yöntemleri ekler **OnStartPage** ve **OnEndPage**, nesneniz için. Tüm Active Server Pages iç nesneler ayarlamak için bu seçeneği seçilmelidir. Varsayılan olarak, seçili.

- **OnStartPage/OnEndPage** [OnStartPage](https://msdn.microsoft.com/library/ms691624.aspx) komut dosyası çalıştığında nesneye erişmek için ilk kez çağrılır. **OnEndPage** nesne tamamlandığında adlı komut dosyası işleme.

**İç nesne**  
Seçmelisiniz **OnStartPage/OnEndPage** tüm ASP iç nesneler ayarlamak için seçeneği.

|Seçenek|Açıklama|
|------------|-----------------|
|**İstek**|Active Server Pages iç erişim sağlayan **istek** nesne. İstek nesnesi, bir HTTP isteği geçirmek için kullanılır.|
|**Yanıt**|Active Server Pages iç erişim sağlayan **yanıt** nesne. Bir isteğe yanıt olarak, yanıt nesnesi kullanıcıya göstermek için tarayıcı bilgileri gönderir.|
|**Oturum**|Active Server Pages iç erişim sağlayan **oturumu** nesne. **Oturumu** nesne durumu bilgileri depolamak ve almak da dahil olmak üzere geçerli kullanıcı oturum bilgilerini tutar.|
|**Uygulama**|Active Server Pages iç erişim sağlayan **uygulama** nesne. **Uygulama** nesnesi birden fazla ASP nesneler arasında paylaşılan durum yönetir.|
|**Sunucu**|Active Server Pages iç erişim sağlayan **sunucu** nesne. **Sunucu** nesnesinin diğer ASP nesneleri oluşturmanızı sağlar.|

## <a name="see-also"></a>Ayrıca Bkz.

[ATL Active Server Page bileşeni Sihirbazı](../../atl/reference/atl-active-server-page-component-wizard.md)   
[ATL Active Server Page bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)

