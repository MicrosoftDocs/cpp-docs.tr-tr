---
title: "Bir tarih ve saat seçici özel biçim dizeleri kullanma Denetim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bfaad06571a8648db24497c46d55cb2eb1ce2157
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>Tarih ve Saat Seçici Denetiminde Özel Biçim Dizeleri Kullanma
Varsayılan olarak, geçerli tarih ve saati görüntülemek için üç türleri (için benzersiz bir stil karşılık gelen her biçim) biçiminde tarih ve Saat Seçici denetimleri sağlar:  
  
-   **DTS_LONGDATEFORMAT** uzun biçiminde, "Çarşamba, Ocak 3 2000" gibi bir çıktı üretir tarihi görüntüler.  
  
-   **DTS_SHORTDATEFORMAT** "3/1/00" gibi bir çıktı üretir kısa biçimindeki tarihi görüntüler.  
  
-   **DTS_TIMEFORMAT** "5:31:42 PM" gibi bir çıktı üretir uzun biçiminde saati görüntüler.  
  
 Ancak, özel bir biçim dizesi kullanarak tarih veya saat görünümünü özelleştirebilirsiniz. Bu özel bir dize, varolan biçimi karakterleri, nonformat karakter veya her ikisinin birleşimini yapılır. Özel bir dize oluşturulduktan sonra çağırmaya [CDateTimeCtrl::SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat) , özel dizeye geçiliyor. Tarih ve Saat Seçici denetimini sonra özel biçim dizesini kullanarak geçerli değeri görüntüler.  
  
 Aşağıdaki örnek kod (burada `m_dtPicker` olan `CDateTimeCtrl` nesnesi) olası bir çözüm gösterilmektedir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 Özel biçim dizeleri yanı sıra tarih ve Saat Seçici desteği de denetimleri [geri arama alanları](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDateTimeCtrl kullanma](../mfc/using-cdatetimectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

