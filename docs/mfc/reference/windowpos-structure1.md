---
title: WINDOWPOS Structure1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure [MFC]
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4abd236998f37f0d719f41827d05a17fde56fde
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379300"
---
# <a name="windowpos-structure1"></a>WINDOWPOS Structure1
`WINDOWPOS` Yapısı boyutunu ve konumunu penceresinin hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagWINDOWPOS { /* wp */  
    HWND hwnd;  
    HWND hwndInsertAfter;  
    int x;  
    int y;  
    int cx;  
    int cy;  
    UINT flags;  
} WINDOWPOS;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *HWND*  
 Pencerenin tanımlar.  
  
 *hwndInsertAfter*  
 Bu pencere yerleştirildiği penceresi tanımlar.  
  
 *x*  
 Pencerenin sol kenarı konumunu belirtir.  
  
 *Y*  
 Pencerenin sağ köşesine konumunu belirtir.  
  
 `cx`  
 Pencere genişliğini piksel cinsinden belirtir.  
  
 `cy`  
 Pencere yüksekliğini piksel cinsinden belirtir.  
  
 `flags`  
 Pencere konumlandırma seçeneklerini belirtir. Bu üye aşağıdaki değerlerden biri olabilir:  
  
- **SWP_DRAWFRAME** (pencere sınıfı açıklamasında tanımlanır) bir çerçeve pencere etrafında çizer. Pencerenin alan bir `WM_NCCALCSIZE` ileti.  
  
- **SWP_FRAMECHANGED** gönderir bir `WM_NCCALCSIZE` pencere boyutunu değil değiştiriliyor olsa bile penceresine iletisi. Bu bayrak belirtilmezse, `WM_NCCALCSIZE` yalnızca pencere boyutunu değiştirilirken gönderilir.  
  
- **SWP_HIDEWINDOW** penceresini gizler.  
  
- `SWP_NOACTIVATE` Pencerenin etkinleştirmez.  
  
- **SWP_NOCOPYBITS** istemci alanını tüm içeriğini atar. Bu bayrak belirtilmezse, istemci alanını geçerli içeriğini kaydedilir ve pencere boyutu ya da yeniden konumlandırılır sonra istemci alanına kopyalanır.  
  
- `SWP_NOMOVE` Geçerli konumu korur (yoksayar **x** ve **y** üyeleri).  
  
- **SWP_NOOWNERZORDER** sahibi pencerenin sıralamasında Z-değiştirmez.  
  
- `SWP_NOSIZE` Geçerli boyut korur (yoksayar **cx** ve **cy** üyeleri).  
  
- **SWP_NOREDRAW** değişiklikleri çizmez.  
  
- **SWP_NOREPOSITION** aynı **SWP_NOOWNERZORDER**.  
  
- **SWP_NOSENDCHANGING** gelen alma penceresinin engeller `WM_WINDOWPOSCHANGING` ileti.  
  
- `SWP_NOZORDER` Geçerli sıralama korur (yoksayar **hwndInsertAfter** üyesi).  
  
- **SWP_SHOWWINDOW** pencerede görüntülenir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

