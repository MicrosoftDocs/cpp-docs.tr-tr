---
title: FILETIME yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- FILETIME
dev_langs:
- C++
helpviewer_keywords:
- FILETIME structure [MFC]
ms.assetid: e09557e2-b6d7-4dd5-a5b9-6328bca88595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4377daa0b8a1420e4f1b5afe1f36fa0fd18d581d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384604"
---
# <a name="filetime-structure"></a>FILETIME Yapısı

`FILETIME` Yapısı, 1 Ocak 1601 bu yana 100 nano saniyelik aralıkların sayısını temsil eden 64-bit bir değer.

## <a name="syntax"></a>Sözdizimi

```
typedef struct _FILETIME {
    DWORD dwLowDateTime;   /* low 32 bits */
    DWORD dwHighDateTime;  /* high 32 bits */
} FILETIME, *PFILETIME, *LPFILETIME;
```

#### <a name="parameters"></a>Parametreler

*dwLowDateTime*<br/>
Düşük 32 bit dosya süreyi belirtir.

*dwHighDateTime*<br/>
Yüksek 32 bit dosya süreyi belirtir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** windef.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

