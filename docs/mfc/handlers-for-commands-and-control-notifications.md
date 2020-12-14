---
description: 'Hakkında daha fazla bilgi edinin: komut ve denetim bildirimleri için Işleyiciler'
title: Komutlar ve Denetim Bildirimleri için İşleyiciler
ms.date: 11/04/2016
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
ms.openlocfilehash: 1e5e3284d5898d1e6349765dc7a1bcdc864c80ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189190"
---
# <a name="handlers-for-commands-and-control-notifications"></a>Komutlar ve Denetim Bildirimleri için İşleyiciler

Komutlar veya denetim bildirim iletileri için varsayılan işleyici yok. Bu nedenle, yalnızca işleyicileri bu ileti kategorileriyle adlandırma kuralına göre bağladınız. Komut veya denetim bildirimini bir işleyiciye eşlediğinizde, [sınıf Sihirbazı](reference/mfc-class-wizard.md) komut kimliğine veya denetim bildirim koduna göre bir ad önerir. Önerilen adı kabul edebilir, değiştirebilir veya değiştirebilirsiniz.

Kural, işleyicileri temsil ettikleri Kullanıcı arabirimi nesnesi için her iki kategoride de ad atamanızı önerir. Bu nedenle, düzenleme menüsünde Kes komutu için bir işleyici adlandırılmış olabilir

[!code-cpp[NVC_MFCMessageHandling#4](codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

Kesme komutu uygulamalarda yaygın olarak uygulandığından, çerçeve **ID_EDIT_CUT** olarak kes komutu IÇIN komut kimliğini önceden tanımlar. Önceden tanımlanmış tüm komut kimliklerinin listesi için bkz. AFXRES. H dosyası. Daha fazla bilgi için bkz. [standart komutlar](standard-commands.md).

Ayrıca, kural, "My Button" etiketli bir düğmeden **BN_CLICKED** bildirim iletisi için bir işleyici önerir

[!code-cpp[NVC_MFCMessageHandling#5](codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

Uygulamaya özgü bir kullanıcı arabirimi nesnesine eşdeğer olduğundan, bu komutu bir **IDC_MY_BUTTON** kimliği atayabilirsiniz.

Her iki ileti kategorisi bağımsız değişken almaz ve değer döndürmez.

## <a name="see-also"></a>Ayrıca bkz.

[Ileti Işleyici Işlevlerini bildirme](declaring-message-handler-functions.md)
