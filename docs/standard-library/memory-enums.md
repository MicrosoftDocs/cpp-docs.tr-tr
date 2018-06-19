---
title: '&lt;bellek&gt; numaralandırmaları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 4d33cf941341f26c88f3a73c5a3d9ac0326db545
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859273"
---
# <a name="ltmemorygt-enums"></a>&lt;bellek&gt; numaralandırmaları

||
|-|
|[pointer_safety](#pointer_safety)|

## <a name="pointer_safety"></a>  pointer_safety numaralandırması

Olası değerler tarafından döndürülen numaralandırma `get_pointer_safety`.

sınıf pointer_safety {gevşek, tercih edilen, katı};

### <a name="remarks"></a>Açıklamalar

Kapsamlı `enum` tarafından döndürülen değerleri tanımlar `get_pointer_safety()`:

`relaxed` --güvenli bir biçimde türetilmiş işaretçileri (açıkça bildirilen veya ayrılmış nesnelerine işaretçiler) kabul edilir aynı Bu güvenle türetilmiş.

`preferred` --eskisi, ancak güvenli bir biçimde türetilmiş işaretçileri değil başvuru yapıldı.

`strict` --güvenli bir biçimde türetilmiş işaretçileri kabul Bu güvenle türetilmiş farklı bir biçimde.

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)<br/>
