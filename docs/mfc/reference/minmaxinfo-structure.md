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
ms.openlocfilehash: 12161938f96e5044ae48f9eb5cf380fbc3840d3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369524"
---
# <a name="minmaxinfo-structure"></a>MINMAXINFO Yapısı
`MINMAXINFO` Yapısı bir pencere ekranı kaplamış boyutunu ve konumunu ve minimum ve maksimum izleme boyutuna hakkındaki bilgileri içerir.  
  
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
 Tam ekran genişliği (point.x) ve penceresinin ekranı kaplamış yüksekliğini (point.y) belirtir.  
  
 `ptMaxPosition`  
 Kaplamış (point.x) sol tarafındaki konumunu ve kaplamış (point.y) üst konumunu belirtir.  
  
 *ptMinTrackSize*  
 Genişlik (point.x) izleme en düşük ve yükseklik (point.y) penceresinin izleme en düşük belirtir.  
  
 *ptMaxTrackSize*  
 En büyük genişliği (point.x) izleme ve maksimum penceresinin (point.y) yüksekliğini izleme belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

