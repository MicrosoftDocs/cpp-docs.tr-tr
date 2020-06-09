---
title: Tarih ve Saat Seçici Denetimlerinde Bildirim İletilerini İşleme
ms.date: 11/04/2016
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
ms.openlocfilehash: 3c568d231cc02b2529a4d97ab7faed51c1737b19
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620999"
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>Tarih ve Saat Seçici Denetimlerinde Bildirim İletilerini İşleme

Kullanıcılar tarih ve saat seçici denetimiyle etkileşecek şekilde, denetim (), `CDateTimeCtrl` ana penceresine (genellikle bir görünüm veya iletişim nesnesi) bildirim iletileri gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, Kullanıcı katıştırılmış ay Takvim denetimini göstermek için tarih ve saat seçicisini açtığında DTN_DROPDOWN bildirimi gönderilir.

Uygulamak istediğiniz iletilerin üst sınıfına bildirim işleyicileri eklemek için [sınıf Sihirbazı](reference/mfc-class-wizard.md) ' nı kullanın.

Aşağıdaki listede tarih ve saat seçici denetimi tarafından gönderilen çeşitli bildirimler açıklanmaktadır.

- DTN_DROPDOWN, üst öğeye gömülü ay Takvim denetiminin görüntülenmek üzere olduğunu bildirir. Bu bildirim yalnızca DTS_UPDOWN stili ayarlanmamışsa gönderilir. Bu bildirim hakkında daha fazla bilgi için bkz. [katıştırılmış ay Takvim denetimine erişme](accessing-the-embedded-month-calendar-control.md).

- DTN_CLOSEUP, üst öğeye gömülü ay Takvim denetiminin kapatılmak üzere olduğunu bildirir. Bu bildirim yalnızca DTS_UPDOWN stili ayarlanmamışsa gönderilir.

- DTN_DATETIMECHANGE, üst öğeye denetimde bir değişikliğin oluştuğunu bildirir.

- DTN_FORMAT, üst öğeye, metnin bir geri çağırma alanında gösterilmesi gerektiğini bildirir. Bu bildirim ve geri çağırma alanları hakkında daha fazla bilgi için bkz. [bir tarih ve saat seçici denetiminde geri çağırma alanları kullanma](using-callback-fields-in-a-date-and-time-picker-control.md).

- DTN_FORMATQUERY, bir geri çağırma alanında görüntülenecek olan dizenin izin verilen en büyük boyutunu sağlamak için üst öğeyi Ister. Bu bildirimin işlenmesi, denetimin ekran içindeki titreşimi azaltmak için her zaman çıktıyı düzgün şekilde görüntülemesine olanak tanır. Bu bildirim hakkında daha fazla bilgi için bkz. [Tarih ve saat seçici denetiminde geri çağırma alanları kullanma](using-callback-fields-in-a-date-and-time-picker-control.md).

- DTN_USERSTRING, üst öğeye kullanıcının tarih ve saat seçici denetiminin içeriğini düzenlemesini tamamladığını bildirir. Bu bildirim yalnızca DTS_APPCANPARSE stili ayarlandığında gönderilir.

- DTN_WMKEYDOWN, Kullanıcı bir geri çağırma alanına yazdığında üst öğeye bildirir. Tarih ve saat seçici denetiminde geri çağırma olmayan alanlar için desteklenen klavye yanıtını öykünmek için bu bildirimi işleyin. Bu bildirim hakkında daha fazla bilgi için bkz. Windows SDK [BIR DTP denetimindeki geri çağırma alanlarını destekleme](/windows/win32/Controls/date-and-time-picker-controls) .

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](using-cdatetimectrl.md)<br/>
[Denetimler](controls-mfc.md)
