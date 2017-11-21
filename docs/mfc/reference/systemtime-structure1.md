---
title: SYSTEMTIME Structure1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SYSTEMTIME
dev_langs: C++
helpviewer_keywords: SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 17bf546d6de5008f8c846a9735d406394f1db856
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="systemtime-structure1"></a>SYSTEMTIME Structure1
`SYSTEMTIME` Bir tarih ve saat ay, gün, yıl, hafta içi günü, saat, dakika, saniye ve milisaniye için tek tek üyeleri kullanarak yapısını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct _SYSTEMTIME {  
    WORD wYear;  
    WORD wMonth;  
    WORD wDayOfWeek;  
    WORD wDay;  
    WORD wHour;  
    WORD wMinute;  
    WORD wSecond;  
    WORD wMilliseconds;  
} SYSTEMTIME;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *wYear*  
 Geçerli yıl.  
  
 *wMonth*  
 Geçerli ay; Ocak 1'dir.  
  
 *wDayOfWeek*  
 Haftanın gününü; Pazar 0, Pazartesi 1 ve benzeri.  
  
 *wDay*  
 Geçerli ayın.  
  
 *wHour*  
 Geçerli saat.  
  
 *wMinute*  
 Geçerli dakikada.  
  
 *wSecond*  
 Geçerli saniye.  
  
 *wMilliseconds*  
 Geçerli milisaniye.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winbase.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

