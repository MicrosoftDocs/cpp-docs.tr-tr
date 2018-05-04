---
title: 'Geçen süre: Otomasyon sınıfları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating in Automation
- Automation classes, elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1abf6274137ae67b159ad43612d24020a0d14e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="elapsed-time-automation-classes"></a>Geçen süre: Otomasyon sınıfları
Bu yordamda, iki arasındaki farkı hesaplamak gösterilmiştir `CTime` nesneleri ve get bir `CTimeSpan` sonucu.  
  
#### <a name="to-calculate-elapsed-time"></a>Geçen süre hesaplamak için  
  
1.  İki oluşturmak `COleDateTime` nesneleri.  
  
2.  Ayarlayın `COleDateTime` geçerli saati nesnelere.  
  
3.  Bazı zaman alıcı görevi gerçekleştirin.  
  
4.  Diğer ayarlamak `COleDateTime` geçerli saati nesnesine.  
  
5.  İki kez arasındaki farkı alın.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarih ve Saat: Otomasyon Desteği](../atl-mfc-shared/date-and-time-automation-support.md)

