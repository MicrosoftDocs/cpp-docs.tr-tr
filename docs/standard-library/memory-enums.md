---
title: '&lt;bellek&gt; sabit listeleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 9b9ea485bb66292c3c0509036c22dd161a694dd3
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961428"
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
