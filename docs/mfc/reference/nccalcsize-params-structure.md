---
title: NCCALCSIZE_PARAMS Yapısı
ms.date: 11/04/2016
f1_keywords:
- NCCALCSIZE_PARAMS
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
ms.openlocfilehash: 3dbe1fcdb941a94876dd95a0eed86d6f4a3e15c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443777"
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

*rgrc*<br/>
Dikdörtgenler dizisini belirtir. İlk yeni taşınan veya yeniden boyutlandırılan bir pencere içerir. Taşınan veya yeniden boyutlandırılan için önce ikinci pencere içerir. Taşınan veya yeniden boyutlandırılan önce üçüncü bir pencerenin istemci alanını içerir. Pencerenin alt penceredir ana penceresinin istemci alanına göre koordinatlar vardır. Pencerenin üst düzey bir pencere koordinatları kutusunun ekrana göreli tutulur.

*lppos*<br/>
İşaret eden bir [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) taşınan veya yeniden boyutlandırılan pencereye neden işleminde belirtilen boyut ve konum değerleri içeren yapısı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winuser.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)

