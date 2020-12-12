---
description: 'Daha fazla bilgi edinin: yığın sabitleri'
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
ms.openlocfilehash: da90be1855f9a4714bc2d441651ac721ede84c1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120701"
---
# <a name="heap-constants"></a>Yığın Sabitleri

## <a name="syntax"></a>Syntax

```
#include <malloc.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler, yığın durumunu gösteren dönüş değerini verir.

|Sabit|Anlamı|
|--------------|-------------|
|`_HEAPBADBEGIN`|İlk üstbilgi bilgileri bulunamadı veya geçersiz.|
|`_HEAPBADNODE`|Hatalı düğüm bulundu veya yığın hasarlı.|
|`_HEAPBADPTR`|**_HEAPINFO** yapısının **_pentry** alanı yığında geçerli işaretçi içermiyor ( `_heapwalk` yalnızca yordam).|
|`_HEAPEMPTY`|Yığın başlatılmamış.|
|`_HEAPEND`|Yığın sonuna başarıyla erişildi ( `_heapwalk` yalnızca yordam).|
|`_HEAPOK`|Yığın tutarlı ( `_heapset` ve `_heapchk` yalnızca yordamlar). Şu ana kadar hata yok; **_HEAPINFO** yapısı sonraki giriş hakkında bilgiler içerir ( `_heapwalk` yalnızca yordam).|

## <a name="see-also"></a>Ayrıca bkz.

[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapset](../c-runtime-library/heapset.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
