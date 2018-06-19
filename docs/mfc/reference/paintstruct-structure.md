---
title: PAINTSTRUCT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bfeddfd1ebf0c5c2247b27a0c69a8a6ef33e7766
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370444"
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

