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
ms.openlocfilehash: 75a3db6c6beb18afe2303b464fcab290b2e132fc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338216"
---
# <a name="paintstruct-structure"></a>PAINTSTRUCT Yapısı
`PAINTSTRUCT` Yapısı pencerenin istemci alanını boyamak için kullanılan bilgileri içerir.  
  
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
 Boyama için kullanılacak görünen bağlamı tanımlar.  
  
 *fErase*  
 Arka plan çizilmesini gerekip gerekmediğini belirtir. Bu uygulamanın arka plan yeniden çizmeniz gerekir 0. Uygulamanın bir arkaplan Fırçası bir Windows pencere sınıfı oluşturduysanız, arka plan çizmek için sorumlu olduğu (açıklamasına bakın `hbrBackground` üyesi [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Windows SDK'sındaki yapısı).  
  
 *rcPaint*  
 Sol üst belirtir ve doğru boyama istendiği dikdörtgenin köşelerini düşürün.  
  
 *fRestore*  
 Ayrılmış üye. Ayrıca, Windows tarafından dahili olarak kullanılır.  
  
 *fIncUpdate*  
 Ayrılmış üye. Ayrıca, Windows tarafından dahili olarak kullanılır.  
  
 *rgbReserved [16]*  
 Ayrılmış üye. Windows tarafından dahili olarak kullanılan bellek ayrılmış bir blok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

