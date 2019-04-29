---
title: Tür Niteleyicileri
ms.date: 11/04/2016
helpviewer_keywords:
- volatile keyword [C], type qualifier
- type qualifiers
- volatile keyword [C]
- qualifiers for types
- const keyword [C]
- memory, access using volatile
- volatile keyword [C], type specifier
ms.assetid: bb4c6744-1dd7-40a8-b4eb-f5585be30908
ms.openlocfilehash: a5cb7ab3de8938b77dc95be3ee442f71d3b18b42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344804"
---
# <a name="type-qualifiers"></a>Tür Niteleyicileri

Tür niteleyicileri iki özelliklerden biri için bir tanımlayıcı sağlar. **Const** tür niteleyicisi değiştirilemez olarak bir nesne bildirir. `volatile` Tür niteleyicisi değeri de avustralya'dan arama değiştirilebilir kontrolü programın göründüğü, eşzamanlı olarak çalışan bir iş parçacığı gibi bir şey tarafından bir öğe bildirir.

İki tür niteleyicileri, **const** ve `volatile`, bir bildirim içinde yalnızca bir kez görünebilir. Tür niteleyicileri, herhangi bir tür tanımlayıcısı ile görünebilir; Ancak, bunlar birden çok öğe bildirimindeki ilk virgülden sonra yer alamaz. Örneğin, aşağıdaki bildirimleri yasal şunlardır:

```
typedef volatile int VI;
const int ci;
```

Bu bildirimler geçerli değildir:

```
typedef int *i, volatile *vi;
float f, const cf;
```

Tür niteleyicileri, yalnızca tanımlayıcıları ifadelerinde l-değerler olarak erişirken ilgilidir. Bkz: [L-değeri ve r değeri ifadeleri](../c-language/l-value-and-r-value-expressions.md) l-değeri ve ifadeleri hakkında daha fazla bilgi için.

## <a name="syntax"></a>Sözdizimi

*tür niteleyicisi*: **constvolatile**

Aşağıdaki yasal **const** ve `volatile` bildirimleri:

```
int const *p_ci;       /* Pointer to constant int */
int const (*p_ci);     /* Pointer to constant int */
int *const cp_i;       /* Constant pointer to int */
int (*const cp_i);     /* Constant pointer to int */
int volatile vint;     /* Volatile integer        */
```

Bir dizi türü belirtimi tür niteleyicileri içeriyorsa, öğenin nitelenmiş, dizi türü değil. İşlev türü belirtimi niteleyicileri içeriyorsa, tanımsız bir davranıştır. Ne `volatile` ya da **const** değerleri aralığı veya aritmetik nesnesinin özelliklerini etkiler.

Bu listeyi nasıl kullanılacağını açıklar **const** ve `volatile`.

- **Const** anahtar sözcüğü, herhangi bir temel ya da toplama türü veya herhangi bir türde bir nesneye bir işaretçi değiştirmek için kullanılabilir veya bir `typedef`. Bir öğe ile yalnızca bildirilmişse **const** tür niteleyicisi türü olmasını alınır **const int**. A **const** değişken başlatılabilir veya bir depolama salt okunur bölgede yerleştirilebilir. **Const** anahtar sözcüğü, işaretçileri bildirmek için kullanışlıdır **const** bu işlev işaretçi herhangi bir şekilde değiştirmemeniz gerekir çünkü.

- Derleyici, programda herhangi bir noktada varsayar bir `volatile` değişkenin değerini değiştirir veya kullanan bilinmeyen bir işlem tarafından erişilebilir. Bu nedenle, komutunda belirtilen iyileştirmelere bakılmaksızın satır, her atama için kod veya, başvuru bir `volatile` değişkeni hiçbir etkiye sahip olma görünse bile oluşturulmalıdır.

   Varsa `volatile` tek başına, kullanılan `int` varsayılır. `volatile` Tür tanımlayıcısı, güvenilir özel bellek konumlarına erişim sağlamak için kullanılabilir. Kullanım `volatile` g/ç Denetimi erişilen veya sinyal işleyiciler tarafından değiştirilmiş olabilir veri nesneleri ile eşzamanlı olarak yürütülen programlara veya bellek eşlemeli gibi özel bir donanım kaydeder. Bir değişken olarak bildirebilirsiniz `volatile` olacak şekilde tek bir başvuru veya yaşam çevirebilirsiniz için `volatile`.

- Bir öğe olmalı **const** ve `volatile`, bu durumda öğe kendi program tarafından yasal olarak değiştirilemedi, ancak bazı zaman uyumsuz bir işlem tarafından değiştirilmiş.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)
