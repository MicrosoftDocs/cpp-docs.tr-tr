---
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
ms.openlocfilehash: cc89cbfde0a1eba5dc736b40c178d4a4fde37a4d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625766"
---
# <a name="handlers-for-commands-and-control-notifications"></a>Komutlar ve Denetim Bildirimleri için İşleyiciler

Komutlar veya denetim bildirim iletileri için varsayılan işleyici yok. Bu nedenle, yalnızca işleyicileri bu ileti kategorileriyle adlandırma kuralına göre bağladınız. Komut veya denetim bildirimini bir işleyiciye eşlediğinizde, [sınıf Sihirbazı](reference/mfc-class-wizard.md) komut kimliğine veya denetim bildirim koduna göre bir ad önerir. Önerilen adı kabul edebilir, değiştirebilir veya değiştirebilirsiniz.

Kural, işleyicileri temsil ettikleri Kullanıcı arabirimi nesnesi için her iki kategoride de ad atamanızı önerir. Bu nedenle, düzenleme menüsünde Kes komutu için bir işleyici adlandırılmış olabilir

[!code-cpp[NVC_MFCMessageHandling#4](codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

Kesme komutu uygulamalarda yaygın olarak uygulandığından, çerçeve **ID_EDIT_CUT**olarak kes komutu IÇIN komut kimliğini önceden tanımlar. Önceden tanımlanmış tüm komut kimliklerinin listesi için bkz. AFXRES dosyası. Olsun. Daha fazla bilgi için bkz. [standart komutlar](standard-commands.md).

Ayrıca, kural, "My Button" etiketli bir düğmeden **BN_CLICKED** bildirim iletisi için bir işleyici önerir

[!code-cpp[NVC_MFCMessageHandling#5](codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

Uygulamaya özgü bir kullanıcı arabirimi nesnesine eşdeğer olduğundan, bu komutu bir **IDC_MY_BUTTON** kimliği atayabilirsiniz.

Her iki ileti kategorisi bağımsız değişken almaz ve değer döndürmez.

## <a name="see-also"></a>Ayrıca bkz.

[İleti İşleyici İşlevlerini Bildirme](declaring-message-handler-functions.md)
