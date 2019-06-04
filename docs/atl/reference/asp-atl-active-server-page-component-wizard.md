---
title: ASP, ATL Active Server Page bileşeni Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.asp
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
ms.openlocfilehash: b88dffe2874d29918315af65c6ea093c24695f97
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503407"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP, ATL Active Server Page bileşeni Sihirbazı

ATL Active Server sayfa bileşeni Sihirbazı bu sayfa, bilgileri ve durum, ASP bileşenle ilgili işlemek için isteğe bağlı ayarları belirtmek için kullanın.

- **İsteğe bağlı yöntemler**

   İsteğe bağlı ASP yöntemleri ekler **OnStartPage** ve **OnEndPage**, nesneniz için. Tüm Active Server Pages iç nesneler ayarlamak için bu seçeneği seçilmelidir. Varsayılan olarak, seçili.

- **OnStartPage/OnEndPage**

   [OnStartPage](/previous-versions//ms691624\(v=vs.85\)) komut dosyası çalıştığında nesneye erişmek için ilk kez çağrılır. **OnEndPage** nesne tamamlandığında adlı komut dosyası işleme.

- **İç nesne**

   Seçmelisiniz **OnStartPage/OnEndPage** tüm ASP iç nesneler ayarlamak için seçeneği.

|Seçenek|Açıklama|
|------------|-----------------|
|**İstek**|Active Server Pages iç erişim sağlayan **istek** nesne. İstek nesnesi, bir HTTP isteği geçirmek için kullanılır.|
|**Yanıt**|Active Server Pages iç erişim sağlayan **yanıt** nesne. Bir isteğe yanıt olarak, yanıt nesnesi kullanıcıya göstermek için tarayıcı bilgileri gönderir.|
|**Oturum**|Active Server Pages iç erişim sağlayan **oturumu** nesne. **Oturumu** nesne durumu bilgileri depolamak ve almak da dahil olmak üzere geçerli kullanıcı oturum bilgilerini tutar.|
|**Uygulama**|Active Server Pages iç erişim sağlayan **uygulama** nesne. **Uygulama** nesnesi birden fazla ASP nesneler arasında paylaşılan durum yönetir.|
|**Sunucu**|Active Server Pages iç erişim sağlayan **sunucu** nesne. **Sunucu** nesnesinin diğer ASP nesneleri oluşturmanızı sağlar.|

## <a name="see-also"></a>Ayrıca bkz.

[ATL Active Server Page Bileşeni Sihirbazı](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server Page bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)
