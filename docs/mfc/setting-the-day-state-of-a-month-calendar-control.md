---
title: Takvim denetiminin bir ayın gün durumunu ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MCN_GETDAYSTATE
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 611397a329e177689a7bd8386963ea1c29ce9e5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>Aylık Takvim Denetiminin Gün Durumunu Ayarlama
Aylık takvim denetiminin özniteliklerini de denetiminin gün durumunu her ayın için başvuru bilgileri depolamak yeteneğidir. Bu bilgiler, şu anda görüntülenen ayı için belirli tarihleri vurgulamak için kullanılır.  
  
> [!NOTE]
>  `CMonthCalCtrl` Nesnenin **MCS_DAYSTATE** gün durumu bilgilerini görüntülemek için stili.  
  
 Gün durumu bilgilerini 32-bit veri türünde ifade **MONTHDAYSTATE**. Her bit bir **MONTHDAYSTATE** bit alanı (1 ile 31 arasında) bir aydaki gün durumunu temsil eder. Bir bit açıksa, karşılık gelen gün görüntülenen içinde kalın; Aksi takdirde hiçbir Vurgu ile görüntülenir.  
  
 Aylık takvim denetiminin gün durumunu ayarlama için iki yöntem vardır: açıkça çağrısıyla [CMonthCalCtrl::SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) veya işleme **MCN_GETDAYSTATE** bildirim iletisi.  
  
## <a name="handling-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE bildirimi ileti işleme  
 **MCN_GETDAYSTATE** iletisi görünür ay içindeki gün nasıl görüntüleneceğini belirlemek için denetim tarafından gönderilir.  
  
> [!NOTE]
>  Denetim önceki ve sonraki ay görünür ay açısından önbelleğe aldığı için yeni bir ayın seçilen her zaman bu bildirim alırsınız.  
  
 Bu ileti düzgün bir şekilde işlemek için kaç gün durumu bilgilerini yükleniyor aylar için istenen, bir dizi başlatma belirlemeniz gerekir **MONTHDAYSTATE** uygun değerleri ve başlatma ilgili yapısı üye yapıları yeni bilgilerle. Gerekli adımları yönelik aşağıdaki yordam, sahibi olduğunuzu varsayar. bir `CMonthCalCtrl` adlı nesne `m_monthcal` ve bir dizi **MONTHDAYSTATE** nesneleri `mdState`.  
  
#### <a name="to-handle-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE bildirimi iletiyi işlemek için  
  
1.  Özellikler penceresini kullanarak eklemek için bir bildirim işleyici **MCN_GETDAYSTATE** için ileti `m_monthcal` nesne (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).  
  
2.  İşleyici gövdesinde aşağıdaki kodu ekleyin:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]  
  
     Örnek dönüştürür `pNMHDR` uygun türde işaretçisine sonra belirler kaç aya ait bilgileri istenen (`pDayState->cDayState`). Geçerli saklayıcısında her ay için (`pDayState->prgDayState[i]`) için sıfır ve ardından gerekli başlatılmış tarihlerini (Bu durumda, her ayın 15'inden) belirleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CMonthCalCtrl kullanma](../mfc/using-cmonthcalctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

