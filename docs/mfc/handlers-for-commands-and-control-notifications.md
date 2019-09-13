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
ms.openlocfilehash: 43b6a517b680a5f6ff092337fbf3d90dd0115dd7
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907980"
---
# <a name="handlers-for-commands-and-control-notifications"></a>Komutlar ve Denetim Bildirimleri için İşleyiciler

Komutlar veya denetim bildirim iletileri için varsayılan işleyici yok. Bu nedenle, yalnızca işleyicileri bu ileti kategorileriyle adlandırma kuralına göre bağladınız. Komut veya denetim bildirimini bir işleyiciye eşlediğinizde, [sınıf Sihirbazı](reference/mfc-class-wizard.md) komut kimliğine veya denetim bildirim koduna göre bir ad önerir. Önerilen adı kabul edebilir, değiştirebilir veya değiştirebilirsiniz.

Kural, işleyicileri temsil ettikleri Kullanıcı arabirimi nesnesi için her iki kategoride de ad atamanızı önerir. Bu nedenle, düzenleme menüsünde Kes komutu için bir işleyici adlandırılmış olabilir

[!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

Kesme komutu uygulamalarda yaygın olarak uygulandığından, çerçeve **ID_EDIT_CUT**olarak kes komutu IÇIN komut kimliğini önceden tanımlar. Önceden tanımlanmış tüm komut kimliklerinin listesi için bkz. AFXRES dosyası. Olsun. Daha fazla bilgi için bkz. [standart komutlar](../mfc/standard-commands.md).

Ayrıca, kural "My Button" etiketli bir düğmeden **BN_CLICKED** bildirim iletisi için bir işleyici önerir

[!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

Uygulamaya özgü bir kullanıcı arabirimi nesnesine eşdeğer olduğundan, bu komutu bir ID **IDC_MY_BUTTON** atayabilirsiniz.

Her iki ileti kategorisi bağımsız değişken almaz ve değer döndürmez.

## <a name="see-also"></a>Ayrıca bkz.

[İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
