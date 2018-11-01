---
title: 'Geçen zaman: Otomasyon sınıfları'
ms.date: 11/04/2016
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
ms.openlocfilehash: fbd01a4e7268456af342293d77ef74d372d2e639
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583917"
---
# <a name="elapsed-time-automation-classes"></a>Geçen zaman: Otomasyon sınıfları

Bu yordamda, iki arasındaki farkı hesaplamak gösterilmiştir `CTime` nesneleri ve get bir `CTimeSpan` sonucu.

## <a name="to-calculate-elapsed-time"></a>Geçen süreyi hesaplamak için

1. İki `COleDateTime` nesneleri.

1. Biri `COleDateTime` geçerli zamanın nesneleri.

1. Zaman alan bir görev gerçekleştirir.

1. Diğer ayarlamak `COleDateTime` geçerli saati için nesne.

1. İki zaman arasındaki farkı yararlanın.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Tarih ve Saat: Otomasyon Desteği](../atl-mfc-shared/date-and-time-automation-support.md)
