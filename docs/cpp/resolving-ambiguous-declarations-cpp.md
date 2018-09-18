---
title: Belirsiz bildirimleri (C++) çözümleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1e55d5afc3cc95dbfd61bead30cdb2d686f7f30
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066650"
---
# <a name="resolving-ambiguous-declarations-c"></a>Belirsiz bildirimleri çözümleme (C++)

Bir türden diğerine açık dönüştürmeler gerçekleştirmek için istenen tür adını belirterek atamalar kullanmanız gerekir. Bazı tür atamaları, sözdizimi belirsizliğine neden olur. Aşağıdaki işlev stili tür ataması belirsizdir:

```cpp
char *aName( String( s ) );
```

Belirsiz bir işlev bildirimi veya işlev stili başlatıcı olarak türüne sahip bir nesne bildirimi olup: türü döndüren bir işlev bildirebilirsiniz `char *` türünde bir bağımsız değişken almayan `String`, veya ' % s'nesne bildirebilirsiniz`aName` ve değeriyle başlatma `s` türündeki `String`.

Bir bildirim geçerli işlev bildirimi olarak kabul edilebilirse, bu şekilde ele alınır. Yalnızca bir işlev bildirimi olamazsa, yani bu durum sözdizimi olarak göre yanlışsa, işlev stili tür araması olup olmadığını belirlemek için bir deyim incelenir. Bu nedenle, derleyici deyimi bir işlevin bildirimi olarak değerlendirir ve `s` tanımlayıcısının etrafındaki parantezleri yoksayar. Öte yandan

```cpp
char *aName( (String)s );
```

and

```cpp
char *aName = String( s );
```

nesnelerin ve türünden kullanıcı tanımlı dönüştürme bildirimlerdir açıkça `String` türüne `char *` başlatma gerçekleştirmek için çağrılan `aName`.