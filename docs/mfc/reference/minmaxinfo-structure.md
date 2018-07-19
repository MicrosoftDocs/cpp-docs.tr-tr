---
title: MINMAXINFO yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MINMAXINFO
dev_langs:
- C++
helpviewer_keywords:
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf9a6e6a1397b9361df5372af09be8e61d997e62
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337820"
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
 *ptReserved*  
 İç kullanım için ayrılmıştır.  
  
 *ptMaxSize*  
 Tam ekran genişliği (point.x) ve ekranı kaplamış (point.y) pencerenin yüksekliğini belirtir.  
  
 *ptMaxPosition*  
 Kaplamış (point.x) sol tarafındaki konumunu ve ekranı kaplamış penceresinin (point.y) üst konumunu belirtir.  
  
 *ptMinTrackSize*  
 En düşük Genişlik (point.x) izleme ve izleme pencerenin yüksekliğini (point.y) en düşük belirtir.  
  
 *ptMaxTrackSize*  
 Maksimum genişliği (point.x) izleme ve pencerenin yüksekliğini (point.y) izleme üst sınırı belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

