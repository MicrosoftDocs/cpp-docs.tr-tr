---
title: Birincil ifadelerdeki tanımlayıcılar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- identifiers, designating objects
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53498d5a1402d1953df93ea0f2d7c723218174c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079043"
---
# <a name="identifiers-in-primary-expressions"></a>Birincil İfadelerdeki Tanımlayıcılar

Tanımlayıcılar tam sayı, sahip **float**, `enum`, `struct`, **birleşim**, işaretçi, dizi veya işlev türü. Birincil bir ifade (Bu durumda bu, bir l değeri'dir) bir nesne belirleme veya bir işlev (Bu durumda bu, bir işlev göstergesini'dir) olarak bildirilmiş sağlanan bir tanımlayıcıdır. Bkz: [L-değeri ve r değeri ifadeleri](../c-language/l-value-and-r-value-expressions.md) bir l-değeri tanımı.

Bir dizi tanımlayıcısına bir atama işleminin sol işleneni biçiminin olamaz ve bu nedenle değiştirilebilir bir l-değeri değil, bir dizi tanımlayıcısı tarafından temsil edilen işaretçi değeri bir değişken değil.

Bir işlev olarak bildirilen bir tanımlayıcı işlevi adresi değeri olduğu bir işaretçiyi temsil eder. Belirtilen türde bir değer döndüren bir işlev işaretçisi ele alır. Bu nedenle, işlev tanımlayıcıları l-değerler atama işlemlerinde olamaz. Daha fazla bilgi için [tanımlayıcıları](../c-language/c-identifiers.md).

## <a name="see-also"></a>Ayrıca Bkz.

[C Birincil İfadeler](../c-language/c-primary-expressions.md)