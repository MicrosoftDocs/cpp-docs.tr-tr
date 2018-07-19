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
ms.openlocfilehash: 095b66af9dab08e3d8fad040c43e2eaf8d2beb81
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335649"
---
# <a name="nccalcsizeparams-structure"></a>NCCALCSIZE_PARAMS Yapısı
`NCCALCSIZE_PARAMS` Yapısı uygulama WM_NCCALCSIZE iletisi işlenirken boyutunu, konumunu ve pencerenin istemci alanının geçerli içeriği hesaplamak için kullanabileceğiniz bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *rgrc*  
 Dikdörtgenler dizisini belirtir. İlk yeni taşınan veya yeniden boyutlandırılan bir pencere içerir. Taşınan veya yeniden boyutlandırılan için önce ikinci pencere içerir. Taşınan veya yeniden boyutlandırılan önce üçüncü bir pencerenin istemci alanını içerir. Pencerenin alt penceredir ana penceresinin istemci alanına göre koordinatlar vardır. Pencerenin üst düzey bir pencere koordinatları kutusunun ekrana göreli tutulur.  
  
 *lppos*  
 İşaret eden bir [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) taşınan veya yeniden boyutlandırılan pencereye neden işleminde belirtilen boyut ve konum değerleri içeren yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)

