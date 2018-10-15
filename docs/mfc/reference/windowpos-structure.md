---
title: WINDOWPOS yapısı | Microsoft Docs
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
ms.openlocfilehash: 36e640187a87f3776a67a072e2fe77c141ed23f0
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334461"
---
# <a name="windowpos-structure"></a>WINDOWPOS Yapısı

`WINDOWPOS` Yapısı boyutunu ve konumunu pencere hakkında bilgiler içerir.

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

*HWND*<br/>
Pencerenin tanımlar.

*hwndInsertAfter*<br/>
Bu pencere yerleştirildiği penceresini tanımlar.

*x*<br/>
Pencerenin sol kenarı konumunu belirtir.

*Y*<br/>
Pencerenin sağ kenarı konumunu belirtir.

*CX*<br/>
Pencere genişliğini piksel cinsinden belirtir.

*CY*<br/>
Pencere yüksekliğini piksel cinsinden belirtir.

*bayrakları*<br/>
Pencere yerleştirme seçeneklerini belirtir. Bu üye, aşağıdaki değerlerden biri olabilir:

- SWP_DRAWFRAME (pencere sınıfı açıklamasında tanımlanır) çerçeve penceresi etrafında bir çizer. Pencerenin WM_NCCALCSIZE ileti alır.

- SWP_FRAMECHANGED gönderir bir WM_NCCALCSIZE iletisi penceresine bile pencerenin boyutu değil değiştiriliyor. Bu bayrak belirtilmezse, yalnızca pencerenin boyutu değiştirilirken WM_NCCALCSIZE gönderilir.

- SWP_HIDEWINDOW penceresini gizler.

- SWP_NOACTIVATE mu penceresini etkinleştir değil.

- Tüm istemci alanını içeriğini SWP_NOCOPYBITS atar. Bu bayrak belirtilmezse istemci alanını geçerli içeriğini kaydedilir ve pencere boyutu veya yeniden konumlandırıldığında sonra istemci alanına kopyalanır.

- Geçerli konumun SWP_NOMOVE korunur (yoksayar `x` ve `y` üyeleri).

- SWP_NOOWNERZORDER mu Z düzeninde sahibi pencerenin konumunu değiştir değil.

- Geçerli boyut SWP_NOSIZE korunur (yoksayar `cx` ve `cy` üyeleri).

- SWP_NOREDRAW mu değişiklikleri Çiz değil.

- SWP_NOREPOSITION SWP_NOOWNERZORDER aynıdır.

- SWP_NOSENDCHANGING penceresi WM_WINDOWPOSCHANGING iletiyi almasını engeller.

- Geçerli sıralama SWP_NOZORDER korunur (yoksayar `hwndInsertAfter` üyesi).

- SWP_SHOWWINDOW penceresinde görüntülenir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winuser.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

