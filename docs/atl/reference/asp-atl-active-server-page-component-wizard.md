---
description: 'Daha fazla bilgi edinin: ASP, ATL Active Server sayfa bileşeni Sihirbazı'
title: ASP, ATL Active Server Page bileşeni Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.asp
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
ms.openlocfilehash: e9cc11cf60c3a87d6891c98a72eb240729d1a739
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165543"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP, ATL Active Server Page bileşeni Sihirbazı

ASP bileşeninizin bilgilerini ve durumunu işlemeye yönelik isteğe bağlı ayarları belirtmek için ATL Active Server Page Bileşen Sihirbazı 'nın bu sayfasını kullanın.

- **İsteğe bağlı Yöntemler**

   Nesneniz için isteğe bağlı ASP yöntemlerini, **OnStartPage** ve **OnEndPage** öğesini ekler. Bu seçenek, Active Server sayfaları iç nesneleri ayarlamak için seçilmelidir. Varsayılan olarak, seçilidir.

- **OnStartPage/OnEndPage**

   [OnStartPage](/previous-versions//ms691624\(v=vs.85\)) , komut dosyası nesneye erişmeyi denediğinde ilk kez çağrılır. Nesne betiği işlemeyi tamamladığında **OnEndPage** çağrılır.

- **İç nesne**

   Herhangi bir ASP iç nesnesini ayarlamak için **OnStartPage/OnEndPage** seçeneğini seçmeniz gerekir.

|Seçenek|Açıklama|
|------------|-----------------|
|**İstek**|Active Server sayfaları iç **istek** nesnesine erişim sağlar. Istek nesnesi bir HTTP isteğini geçirmek için kullanılır.|
|**Response**|Active Server sayfaları iç **Yanıt** nesnesine erişim sağlar. Bir isteğe yanıt olarak, Response nesnesi kullanıcıya görüntülenecek bilgileri tarayıcıya gönderir.|
|**Oturum**|Active Server sayfaları iç **oturum** nesnesine erişim sağlar. **Oturum** nesnesi, durum bilgilerini depolamak ve almak dahil olmak üzere geçerli kullanıcı oturumu hakkındaki bilgileri saklar.|
|**Uygulama**|Active Server sayfaları iç **uygulama** nesnesine erişim sağlar. **Uygulama** nesnesi, bırden çok ASP nesnesi arasında paylaşılan durumu yönetir.|
|**Sunucu**|Active Server sayfaları iç **sunucu** nesnesine erişim sağlar. **Sunucu** nesnesi, diğer ASP nesneleri oluşturmanıza olanak sağlar.|

## <a name="see-also"></a>Ayrıca bkz.

[ATL Active Server Page Bileşeni Sihirbazı](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server sayfa bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)
