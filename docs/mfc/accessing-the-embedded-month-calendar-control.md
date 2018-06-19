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
ms.openlocfilehash: cfbc9ce7b99efc1f8d99f5735c16c252ff613c59
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332133"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>Katıştırılmış Aylık Takvim Denetimine Erişme
Katıştırılmış aylık takvim denetimi nesnesi erişilebilen `CDateTimeCtrl` çağrısıyla nesne [GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl) üye işlevi.  
  
> [!NOTE]
>  Katıştırılmış aylık takvim denetiminin yalnızca tarih ve Saat Seçici denetimini olmadığı zaman kullanılan **DTS_UPDOWN** stil kümesi.  
  
 Katıştırılmış denetime görüntülenmeden önce belirli öznitelikler değiştirmek istiyorsanız kullanışlıdır. Bunu gerçekleştirmek için tanıtıcı **DTN_DROPDOWN** bildirim, aylık takvim denetiminin almak (kullanarak [CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)) ve değişikliklerinizi yapın. Ne yazık ki, aylık takvim denetiminin kalıcı değildir.  
  
 Diğer bir deyişle, yeni aylık takvim denetiminin kullanıcı aylık takvim denetiminin görünümünü istediğinde, oluşturulan (önce **DTN_DROPDOWN** bildirim). Denetim yok (sonra **DTN_CLOSEUP** bildirim) kullanıcı tarafından kapatıldığında olduğunda. Başka bir deyişle, katıştırılmış denetime kapatıldığında, katıştırılmış denetime görüntülenmeden önce değiştirme öznitelikleri kaybolur.  
  
 Bu yordamı için bir işleyici kullanarak, aşağıdaki örnekte gösterilmiştir **DTN_DROPDOWN** bildirim. Aylık takvim denetiminin çağrısıyla arka plan rengini kodunu değiştirir [SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor), gri. Kod aşağıdaki gibidir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]  
  
 Katıştırılmış denetime kapatıldığında daha önce belirtildiği gibi aylık takvim denetiminin özelliklerini yapılan tüm değişiklikler, iki istisnalar kaybolur. Aylık takvim denetiminin renkleri ilk özel durum zaten açıklanmıştır. Ay takvim denetimi tarafından kullanılan yazı tipi ikinci istisnadır. Varsayılan yazı tipi için bir çağrı yaparak değiştirebileceğiniz [CDateTimeCtrl::SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont), var olan bir yazıtipi tanıtıcısı geçirme. Aşağıdaki örnekte (burada `m_dtPicker` tarih ve saat denetim nesnesidir) olası bir yöntemi gösterir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]  
  
 Yazı tipi, çağrısıyla değiştirilmişse `CDateTimeCtrl::SetMonthCalFont`, yeni yazı tipi depolanır ve bir ay Takvim olan görüntülenecek sonraki açışınızda kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDateTimeCtrl kullanma](../mfc/using-cdatetimectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

