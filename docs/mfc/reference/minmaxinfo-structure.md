---
title: MINMAXINFO Yapısı
ms.date: 11/04/2016
f1_keywords:
- MINMAXINFO
helpviewer_keywords:
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
ms.openlocfilehash: 11f55b1756623626769e21c006543b6993607b08
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517851"
---
# <a name="minmaxinfo-structure"></a>MINMAXINFO Yapısı

`MINMAXINFO` Yapısı bir pencerenin tam ekran boyutu ve konumu ve izleme minimum ve maksimum boyutunu hakkındaki bilgileri içerir.

## <a name="syntax"></a>Sözdizimi

```
typedef struct tagMINMAXINFO {
    POINT ptReserved;
    POINT ptMaxSize;
    POINT ptMaxPosition;
    POINT ptMinTrackSize;
    POINT ptMaxTrackSize;
} MINMAXINFO;
```

#### <a name="parameters"></a>Parametreler

*ptReserved*<br/>
İç kullanım için ayrılmıştır.

*ptMaxSize*<br/>
Tam ekran genişliği (point.x) ve ekranı kaplamış (point.y) pencerenin yüksekliğini belirtir.

*ptMaxPosition*<br/>
Kaplamış (point.x) sol tarafındaki konumunu ve ekranı kaplamış penceresinin (point.y) üst konumunu belirtir.

*ptMinTrackSize*<br/>
En düşük Genişlik (point.x) izleme ve izleme pencerenin yüksekliğini (point.y) en düşük belirtir.

*ptMaxTrackSize*<br/>
Maksimum genişliği (point.x) izleme ve pencerenin yüksekliğini (point.y) izleme üst sınırı belirtir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winuser.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

