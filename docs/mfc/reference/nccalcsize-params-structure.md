---
title: "Nccalcsıze_params yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: NCCALCSIZE_PARAMS
dev_langs: C++
helpviewer_keywords: NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76a0a16ff0a2c90c6dd6060badc2c79dde1af231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nccalcsizeparams-structure"></a>NCCALCSIZE_PARAMS Yapısı
`NCCALCSIZE_PARAMS` Yapısı işlenirken bir uygulama kullanan bilgiler içermektedir `WM_NCCALCSIZE` ileti boyutu, konumu ve geçerli bir pencere istemci alanını içeriğini hesaplamak için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *rgrc*  
 Dikdörtgenler dizisini belirtir. İlk taşınan veya yeniden boyutlandırılan bir pencere yeni koordinatlarını içerir. Taşınan veya yeniden boyutlandırılan önce ikinci penceresi koordinatlarını içerir. Taşınan veya yeniden boyutlandırılan önce üçüncü bir pencere istemci alanını koordinatlarını içerir. Pencerenin alt pencere ise, ana pencereyi istemci alanına göre koordinatlar belirlenir. Pencerenin üst düzey bir pencere ise, koordinatlar ekran göre belirlenir.  
  
 *lppos*  
 İşaret eden bir [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) taşınan veya yeniden boyutlandırılan pencereye neden işlemde belirtilen boyut ve konum değerleri içeren yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)

