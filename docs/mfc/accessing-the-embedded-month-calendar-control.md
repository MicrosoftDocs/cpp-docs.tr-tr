---
title: Katıştırılmış Aylık Takvim Denetimine Erişme
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
ms.openlocfilehash: dfe6fa220e19deebd86e7c8b7bd25dab60165f73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392927"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>Katıştırılmış Aylık Takvim Denetimine Erişme

Katıştırılmış aylık takvim denetimi nesnesi erişilebilir `CDateTimeCtrl` nesne çağrısıyla [GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl) üye işlevi.

> [!NOTE]
>  Katıştırılmış aylık takvim denetiminin tarih ve Saat Seçici denetimini yoksa yalnızca kullanılan **DTS_UPDOWN** stil kümesi.

Bu özellik, eklenen denetimin görüntülenmeden önce belirli öznitelikleri değiştirmek istiyorsanız kullanışlıdır. Bunu gerçekleştirmek için tanıtıcı **DTN_DROPDOWN** bildirim, aylık takvim denetiminin almak (kullanarak [CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)) ve değişikliklerinizi yapın. Ne yazık ki, aylık takvim denetiminin kalıcı değil.

Diğer bir deyişle, yeni aylık takvim denetiminin kullanıcı aylık takvim denetiminin görünümünü istediğinde, oluşturulan (önce **DTN_DROPDOWN** bildirim). Denetim yok (sonra **DTN_CLOSEUP** bildirim), kullanıcı tarafından kapatıldı. Başka bir deyişle, eklenen denetimin kapatıldığında işlenecek kodu yerleştirin, eklenen denetimin görüntülenmeden önce değişiklik herhangi bir özniteliği kaybolur.

Aşağıdaki örnek, bir işleyici için kullanarak, bu yordamı gösterir **DTN_DROPDOWN** bildirim. Kodu çağrısı, aylık takvim denetiminin arka plan rengini değiştirir [SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor), gri. Kod aşağıdaki gibidir:

[!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

Eklenen denetimin kapatıldı daha önce belirtildiği gibi aylık takvim denetiminin özelliklerini yapılan tüm değişiklikler, iki özel durum ile kaybolur. Aylık takvim denetiminin renklerini ilk özel durum zaten değindik. Ay takvim denetimi tarafından kullanılan yazı tipi ikinci istisnadır. Varsayılan yazı tipi için bir çağrı yaparak değiştirebilirsiniz [CDateTimeCtrl::SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont), var olan bir yazı tipi tanıtıcısını geçirmekten. Aşağıdaki örnek (burada `m_dtPicker` tarih ve saat denetimini nesnedir) bir olası yöntemi gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

Yazı tipi, çağrısıyla değiştirilmişse `CDateTimeCtrl::SetMonthCalFont`, yeni yazı tipi depolanır ve bir ay takvimi görüntülenecek olduğunda kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](../mfc/using-cdatetimectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
