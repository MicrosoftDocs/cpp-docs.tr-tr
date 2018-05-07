---
title: Nccalcsıze_params yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- NCCALCSIZE_PARAMS
dev_langs:
- C++
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07db612cb6dbde0dd762cf709ac6040bbd836c4b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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

