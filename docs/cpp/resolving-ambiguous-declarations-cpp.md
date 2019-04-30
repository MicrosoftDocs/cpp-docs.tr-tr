---
title: Belirsiz bildirimleri çözümleme (C++)
ms.date: 11/04/2016
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
ms.openlocfilehash: 52e94f474d59505298cb4f78a477cedd21b90aad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403405"
---
# <a name="resolving-ambiguous-declarations-c"></a>Belirsiz bildirimleri çözümleme (C++)

Bir türden diğerine açık dönüştürmeler gerçekleştirmek için istenen tür adını belirterek atamalar kullanmanız gerekir. Bazı tür atamaları, sözdizimi belirsizliğine neden olur. Aşağıdaki işlev stili tür ataması belirsizdir:

```cpp
char *aName( String( s ) );
```

Bir işlev bildirimi veya işlev stili başlatıcı olarak türüne sahip bir nesne bildirimi olup, belirgin değil: Türü döndüren bir işlev bildirebilirsiniz `char *` türünde bir bağımsız değişken almayan `String`, veya nesnesini bildirip `aName` ve değeriyle başlatma `s` türündeki `String`.

Bir bildirim geçerli işlev bildirimi olarak kabul edilebilirse, bu şekilde ele alınır. Yalnızca bir işlev bildirimi olamazsa, yani bu durum sözdizimi olarak göre yanlışsa, işlev stili tür araması olup olmadığını belirlemek için bir deyim incelenir. Bu nedenle, derleyici deyimi bir işlevin bildirimi olarak değerlendirir ve `s` tanımlayıcısının etrafındaki parantezleri yoksayar. Öte yandan

```cpp
char *aName( (String)s );
```

and

```cpp
char *aName = String( s );
```

nesnelerin ve türünden kullanıcı tanımlı dönüştürme bildirimlerdir açıkça `String` türüne `char *` başlatma gerçekleştirmek için çağrılan `aName`.