---
title: Aylık Takvim Denetiminin Gün Durumunu Ayarlama
ms.date: 11/04/2016
f1_keywords:
- MCN_GETDAYSTATE
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
ms.openlocfilehash: c75b560509738e071accdc3dba31dfdea35a14aa
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262371"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>Aylık Takvim Denetiminin Gün Durumunu Ayarlama

Aylık takvim denetiminin özniteliklerinden biri denetiminin gün durumunu ayın her günü için başvuru bilgilerini depolamak için olanağıdır. Bu bilgiler, şu anda görüntülenen ayı için belirli bir tarih vurgulamak için kullanılır.

> [!NOTE]
>  `CMonthCalCtrl` Nesne MCS_DAYSTATE stili gün durumu bilgilerini görüntülemek için sahip olması gerekir.

Gün durumu bilgilerini bir 32-bit veri türü olarak ifade edilir **MONTHDAYSTATE**. Her bit bir **MONTHDAYSTATE** bit alanı (1 ile 31 arasında) bir ayda bir gün durumunu temsil eder. Üzerinde bir bit ise, karşılık gelen günün görüntülenir, kalın; Aksi takdirde hiçbir Vurgu ile görüntülenir.

Aylık takvim denetiminin gün durumunu ayarlama için iki yöntem vardır: bir çağrı ile açıkça [CMonthCalCtrl::SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) veya MCN_GETDAYSTATE bildirimi ileti işleme.

## <a name="handling-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE bildirimi ileti işleme

MCN_GETDAYSTATE ileti gün görünür ay içinde nasıl görüntüleneceğini belirlemek için denetim tarafından gönderilir.

> [!NOTE]
>  Denetimin görünür ay açısından önceki ve sonraki ay ön belleğe aldığından yeni bir ay seçilen her zaman bu bildirim alırsınız.

Düzgün bir şekilde bu iletiyi işlemek için kaç gün durumu bilgileri okunuyor ay için istendi, bir dizi başlatma belirlemelisiniz **MONTHDAYSTATE** yapıları uygun değerler ve ilgili yapı üyesi başlatma Yeni bilgiler ile. Gerekli adımlarla ilgili ayrıntılara ilişkin aşağıdaki yordam, olduğunu varsayar bir `CMonthCalCtrl` çağrılan nesne *m_monthcal* ve bir dizi **MONTHDAYSTATE** nesneleri *mdState*.

#### <a name="to-handle-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE bildirimi iletisini işlemek için

1. Özellikler penceresini kullanarak MCN_GETDAYSTATE iletinin bildirim işleyici ekleme *m_monthcal* nesne (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

1. İşleyici gövdesine aşağıdaki kodu ekleyin:

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   Örnek *pNMHDR* uygun türe işaretçi ardından belirler bilgilerinin kaç ay istenen (`pDayState->cDayState`). Geçerli bit alanından mantıksal karşılaştırmaya her ay için (`pDayState->prgDayState[i]`) sıfır ve ardından gerekli başlatılır tarihleri (Bu durumda, her ayın 15'inden) ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[CMonthCalCtrl Kullanma](../mfc/using-cmonthcalctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
