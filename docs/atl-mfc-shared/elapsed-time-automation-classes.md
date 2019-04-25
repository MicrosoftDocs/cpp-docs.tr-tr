---
title: 'Geçen süre: Otomasyon sınıfları'
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
ms.openlocfilehash: d6a77d57a88166354fcb222c0da09690426108e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235801"
---
# <a name="elapsed-time-automation-classes"></a>Geçen süre: Otomasyon sınıfları

Bu yordamda, iki arasındaki farkı hesaplamak gösterilmiştir `CTime` nesneleri ve get bir `CTimeSpan` sonucu.

## <a name="to-calculate-elapsed-time"></a>Geçen süreyi hesaplamak için

1. İki `COleDateTime` nesneleri.

1. Biri `COleDateTime` geçerli zamanın nesneleri.

1. Zaman alan bir görev gerçekleştirir.

1. Diğer ayarlamak `COleDateTime` geçerli saati için nesne.

1. İki zaman arasındaki farkı yararlanın.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Tarih ve saat: Otomasyon desteği](../atl-mfc-shared/date-and-time-automation-support.md)
