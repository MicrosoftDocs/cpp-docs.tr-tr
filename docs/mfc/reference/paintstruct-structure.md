---
title: "PAINTSTRUCT yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PAINTSTRUCT
dev_langs: C++
helpviewer_keywords: PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 67be684e04a2ff8d97c58f625f1be39834813b70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="paintstruct-structure"></a>PAINTSTRUCT Yapısı
`PAINTSTRUCT` Yapısı penceresinin istemci alanını boyamak için kullanılan bilgileri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagPAINTSTRUCT {  
    HDC hdc;  
    BOOL fErase;  
    RECT rcPaint;  
    BOOL fRestore;  
    BOOL fIncUpdate;  
    BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *hdc*  
 Boyama için kullanılacak görüntüleme bağlamı tanımlar.  
  
 *fErase*  
 Arka plan çizilmesi gerekip gerekmediğini belirtir. Bu uygulama arka yeniden boyutlandırmaya yoksa 0. Uygulama bir Windows pencere sınıfı bir arka plan Fırçası oluşturulursa, arka plan çizim için sorumludur (açıklamasına bakın **hbrBackground** üyesi [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) yapısı Windows SDK).  
  
 *rcPaint*  
 Boyama istenen dikdörtgen sağ köşelerinde alt ve sol üst belirtir.  
  
 *fRestore*  
 Ayrılmış üyesi. Ayrıca, Windows tarafından dahili olarak kullanılır.  
  
 *fIncUpdate*  
 Ayrılmış üyesi. Ayrıca, Windows tarafından dahili olarak kullanılır.  
  
 *rgbReserved [16]*  
 Ayrılmış üyesi. Ayrılmış bir Windows tarafından dahili olarak kullanılan bellek bloğu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

