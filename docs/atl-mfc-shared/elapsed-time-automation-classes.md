---
title: 'Geçen zaman: Otomasyon sınıfları | Microsoft Docs'
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
ms.openlocfilehash: dcde08e8ffdb30f9ebf0ae7577bf836e84513a07
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751683"
---
# <a name="elapsed-time-automation-classes"></a>Geçen zaman: Otomasyon sınıfları

Bu yordamda, iki arasındaki farkı hesaplamak gösterilmiştir `CTime` nesneleri ve get bir `CTimeSpan` sonucu.

#### <a name="to-calculate-elapsed-time"></a>Geçen süreyi hesaplamak için

1. İki `COleDateTime` nesneleri.

2. Biri `COleDateTime` geçerli zamanın nesneleri.

3. Zaman alan bir görev gerçekleştirir.

4. Diğer ayarlamak `COleDateTime` geçerli saati için nesne.

5. İki zaman arasındaki farkı yararlanın.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Tarih ve Saat: Otomasyon Desteği](../atl-mfc-shared/date-and-time-automation-support.md)

