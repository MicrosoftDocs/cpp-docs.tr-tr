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
ms.openlocfilehash: 729e9f65fd1054b8381f45b81e5276846145ebc1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87198729"
---
# <a name="type-qualifiers"></a>Tür Niteleyicileri

Tür niteleyicileri bir tanımlayıcıya iki özelliklerden birini verir. **`const`** Tür niteleyicisi, değiştirilemeyen bir nesne bildirir. **`volatile`** Tür niteleyicisi, değeri, benzer bir şekilde yürütülen iş parçacığı gibi, göründüğü programın denetimi dışında bir şey tarafından meşru bir şekilde değiştirilebilen bir öğe bildirir.

İki tür niteleyicisi ve, **`const`** **`volatile`** bir bildirimde yalnızca bir kez bulunabilir. Tür niteleyicileri herhangi bir tür belirticisiyle görünebilir; Ancak, birden çok öğe bildiriminde ilk virgülden sonra yer alamaz. Örneğin, aşağıdaki bildirimler geçerlidir:

```
typedef volatile int VI;
const int ci;
```

Bu bildirimler geçerli değildir:

```
typedef int *i, volatile *vi;
float f, const cf;
```

Tür niteleyicileri yalnızca tanımlayıcılardaki l-Values olarak erişim için geçerlidir. L-Values ve ifadeler hakkında bilgi için bkz. [l-Value ve R-Value ifadeleri](../c-language/l-value-and-r-value-expressions.md) .

## <a name="syntax"></a>Sözdizimi

*tür niteleyicisi*: **constvolatile**

Aşağıdakiler geçerlidir **`const`** ve **`volatile`** bildirimlerdir:

```
int const *p_ci;       /* Pointer to constant int */
int const (*p_ci);     /* Pointer to constant int */
int *const cp_i;       /* Constant pointer to int */
int (*const cp_i);     /* Constant pointer to int */
int volatile vint;     /* Volatile integer        */
```

Bir dizi türünün belirtimi tür niteleyicileri içeriyorsa, öğesi dizi türü değil, nitelenir. İşlev türü belirtimi niteleyiciler içeriyorsa, davranış tanımsızdır. **`volatile`** **`const`** Nesnenin değer aralığını veya aritmetik özelliklerini ne veya bundan etkilenmez.

Bu liste, ve ' nin nasıl kullanılacağını açıklar **`const`** **`volatile`** .

- **`const`** Anahtar sözcüğü herhangi bir temel veya toplama türünü ya da herhangi bir türdeki bir nesneyi veya bir işaretçiyi değiştirmek için kullanılabilir **`typedef`** . Bir öğe yalnızca **`const`** tür niteleyicisi ile bildirilirse, türü **const int**olarak alınır. Bir **`const`** değişken, depolama alanının salt tanımlı bir bölgesine başlatılabilir veya yerleştirilebilir. **`const`** Anahtar sözcüğü, **`const`** işlevin işaretçiyi herhangi bir şekilde değiştirmesinin gerekli olmadığı için işaretçilerin bildirilmesi için yararlıdır.

- Derleyici, programda herhangi bir noktada bir **`volatile`** değişkene, değerini kullanan veya değiştiren bilinmeyen bir işlem tarafından erişilebileceği varsayılır. Bu nedenle, komut satırında belirtilen iyileştirmelere bakılmaksızın, bir değişkene yapılan her atamaya veya başvuruya yönelik kodun **`volatile`** hiçbir etkisi olmasa bile oluşturulması gerekir.

   **`volatile`** Tek başına kullanılırsa **`int`** varsayılır. **`volatile`** Tür belirleyicisi özel bellek konumlarına güvenilir erişim sağlamak için kullanılabilir. **`volatile`** Aynı anda programları veya bellek eşlemeli g/ç denetim kayıtları gibi özel donanımları kullanarak, sinyal işleyicileri tarafından erişilebilen veya değiştirilen veri nesneleriyle birlikte kullanın. Bir değişkeni **`volatile`** ömrü boyunca bildirebilir veya tek bir başvuruyu olacak şekilde dönüştürebilirsiniz **`volatile`** .

- Bir öğe hem hem de **`const`** olabilir **`volatile`** , bu durumda öğe kendi programı tarafından meşru bir şekilde değiştirilemez ancak bazı zaman uyumsuz işlemler tarafından değiştirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)
