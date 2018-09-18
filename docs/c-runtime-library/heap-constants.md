---
title: Yığın sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 791509a7c67f5fa47128fda97688c43e592724ed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115183"
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