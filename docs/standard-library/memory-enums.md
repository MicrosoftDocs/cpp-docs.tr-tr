---
title: '&lt;bellek&gt; sabit listeleri'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 5c5f87905b772ef277a72ef11defef8cb1001661
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412845"
---
# <a name="ltmemorygt-enums"></a>&lt;bellek&gt; sabit listeleri

||
|-|
|[pointer_safety](#pointer_safety)|

## <a name="pointer_safety"></a>  pointer_safety numaralandırması

Olası değerler tarafından döndürülen sabit `get_pointer_safety`.

sınıf pointer_safety {gevşek, tercih edilen, katı};

### <a name="remarks"></a>Açıklamalar

Kapsamlı **enum** tarafından döndürülen değerleri tanımlar `get_pointer_safety()`:

`relaxed` --olmayan güvenli bir şekilde türetilen işaretçileri (açıkça bildirilen veya ayrılmış nesnelerine işaretçiler) kabul edilir bu güvenli bir şekilde türetilen olarak aynı.

`preferred` --önceden olduğu gibi ancak olmayan güvenli bir şekilde türetilen işaretçileri değil başvurusu.

`strict` --olmayan güvenli bir şekilde türetilen işaretçileri kabul bu güvenli bir şekilde türetilen değerinden farklı.

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)<br/>
