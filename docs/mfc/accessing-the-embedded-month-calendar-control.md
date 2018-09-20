---
title: Katıştırılmış aylık takvim denetimine erişme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a92660223c84c5f53bc848e72b03316602180d36
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430299"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CDateTimeCtrl Kullanma](../mfc/using-cdatetimectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

