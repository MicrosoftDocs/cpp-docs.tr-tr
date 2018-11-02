---
title: PAINTSTRUCT Yapısı
ms.date: 11/04/2016
f1_keywords:
- PAINTSTRUCT
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
ms.openlocfilehash: b5179a1bcba4a654ff235885ec2d0516e801fbb7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677129"
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

*hdc*<br/>
Boyama için kullanılacak görünen bağlamı tanımlar.

*fErase*<br/>
Arka plan çizilmesini gerekip gerekmediğini belirtir. Bu uygulamanın arka plan yeniden çizmeniz gerekir 0. Uygulamanın bir arkaplan Fırçası bir Windows pencere sınıfı oluşturduysanız, arka plan çizmek için sorumlu olduğu (açıklamasına bakın `hbrBackground` üyesi [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) Windows SDK'sındaki yapısı).

*rcPaint*<br/>
Sol üst belirtir ve doğru boyama istendiği dikdörtgenin köşelerini düşürün.

*fRestore*<br/>
Ayrılmış üye. Ayrıca, Windows tarafından dahili olarak kullanılır.

*fIncUpdate*<br/>
Ayrılmış üye. Ayrıca, Windows tarafından dahili olarak kullanılır.

*rgbReserved [16]*<br/>
Ayrılmış üye. Windows tarafından dahili olarak kullanılan bellek ayrılmış bir blok.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winuser.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

