---
title: Bir tarih ve saat seçici özel biçim dizeleri kullanma Denetim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9aeb6c02041a4ba90f9721f23a1397e17a4cdf81
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955764"
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>Tarih ve Saat Seçici Denetiminde Özel Biçim Dizeleri Kullanma
Varsayılan olarak, geçerli tarih ve saati görüntülemek için üç türleri (için benzersiz bir stil karşılık gelen her biçim) biçiminde tarih ve Saat Seçici denetimleri sağlar:  
  
-   **DTS_LONGDATEFORMAT** uzun biçiminde, "Çarşamba, Ocak 3 2000" gibi bir çıktı üretir tarihi görüntüler.  
  
-   **DTS_SHORTDATEFORMAT** "3/1/00" gibi bir çıktı üretir kısa biçimindeki tarihi görüntüler.  
  
-   **DTS_TIMEFORMAT** "5:31:42 PM" gibi bir çıktı üretir uzun biçiminde saati görüntüler.  
  
 Ancak, özel bir biçim dizesi kullanarak tarih veya saat görünümünü özelleştirebilirsiniz. Bu özel bir dize, varolan biçimi karakterleri, nonformat karakter veya her ikisinin birleşimini yapılır. Özel bir dize oluşturulduktan sonra çağırmaya [CDateTimeCtrl::SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat) , özel dizeye geçiliyor. Tarih ve Saat Seçici denetimini sonra özel biçim dizesini kullanarak geçerli değeri görüntüler.  
  
 Aşağıdaki örnek kod (burada *m_dtPicker* olan `CDateTimeCtrl` nesnesi) olası bir çözüm gösterilmektedir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 Özel biçim dizeleri yanı sıra tarih ve Saat Seçici desteği de denetimleri [geri arama alanları](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDateTimeCtrl kullanma](../mfc/using-cdatetimectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

