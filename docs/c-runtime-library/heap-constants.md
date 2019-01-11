---
title: Yığın Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
helpviewer_keywords:
- _HEAPOK constants
- _HEAPEND constants
- HEAPBADBEGIN constants
- _HEAPBADNODE constants
- HEAPBADNODE constants
- HEAPBADPTR constants
- _HEAPEMPTY constants
- HEAPEND constants
- HEAPOK constants
- HEAPEMPTY constants
- _HEAPBADBEGIN constants
- _HEAPBADPTR constants
- heap constants
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
ms.openlocfilehash: b8783a5826376a65cb71444e2d64c61b6938eab8
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220224"
---
# <a name="heap-constants"></a>Yığın Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <malloc.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler yığının durumunu gösteren dönüş değeri verir.

|Sabit|Açıklama|
|--------------|-------------|
|`_HEAPBADBEGIN`|İlk üstbilgi bilgileri bulunamadı veya geçersiz.|
|`_HEAPBADNODE`|Bozuk düğümü bulundu veya yığın zarar görmüş.|
|`_HEAPBADPTR`|**_pentry** alanını **_heapınfo** yapısı geçerli bir işaretçiyi yığına içermiyor (`_heapwalk` yalnızca yordam).|
|`_HEAPEMPTY`|Yığın başlatılmadı.|
|`_HEAPEND`|Yığının sonuna başarıyla ulaşıldı (`_heapwalk` yalnızca yordam).|
|`_HEAPOK`|Yığın tutarlıdır (`_heapset` ve `_heapchk` yordamlar yalnızca). Kadar hiç hata; **_Heapınfo** yapısı sonraki giriş hakkında bilgiler içerir (`_heapwalk` yalnızca yordam).|

## <a name="see-also"></a>Ayrıca Bkz.

[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapset](../c-runtime-library/heapset.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
