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

Tür niteleyicileri bir tanımlayıcıya iki özelliklerden birini verir. **Const** tür niteleyicisi, bir nesneyi değiştirilemeyecek şekilde bildirir. Tür `volatile` niteleyicisi, değeri, benzer bir şekilde yürütülen iş parçacığı gibi, göründüğü programın denetimi dışında bir şey tarafından meşru bir şekilde değiştirilebilen bir öğe bildirir.

İki tür niteleyicisi, **const** ve `volatile`, bir bildirimde yalnızca bir kez bulunabilir. Tür niteleyicileri herhangi bir tür belirticisiyle görünebilir; Ancak, birden çok öğe bildiriminde ilk virgülden sonra yer alamaz. Örneğin, aşağıdaki bildirimler geçerlidir:

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

Aşağıdakiler geçerli **const** ve `volatile` bildirimlerdir:

```
int const *p_ci;       /* Pointer to constant int */
int const (*p_ci);     /* Pointer to constant int */
int *const cp_i;       /* Constant pointer to int */
int (*const cp_i);     /* Constant pointer to int */
int volatile vint;     /* Volatile integer        */
```

Bir dizi türünün belirtimi tür niteleyicileri içeriyorsa, öğesi dizi türü değil, nitelenir. İşlev türü belirtimi niteleyiciler içeriyorsa, davranış tanımsızdır. Ne `volatile` ya da **const** , nesnenin değer aralığını veya aritmetik özelliklerini etkiler.

Bu liste **const** ve ' `volatile`nin nasıl kullanılacağını açıklar.

- **Const** anahtar sözcüğü herhangi bir temel veya toplama türünü ya da herhangi bir türdeki bir nesneyi veya bir `typedef`işaretçiyi değiştirmek için kullanılabilir. Bir öğe yalnızca **const** türü niteleyicisi ile bildirilirse, türü **const int**olarak alınır. **Const** değişkeni, depolama alanının salt tanımlı bir bölgesine başlatılabilir veya yerleştirilebilir. **Const** anahtar sözcüğü, işlevin işaretçiyi herhangi bir şekilde değiştirmesinin gerekli olmasından dolayı **const** öğesine işaretçiler bildirmek için yararlıdır.

- Derleyici, programda herhangi bir noktada bir `volatile` değişkene, değerini kullanan veya değiştiren bilinmeyen bir işlem tarafından erişilebileceği varsayılır. Bu nedenle, komut satırında belirtilen iyileştirmelere bakılmaksızın, bir `volatile` değişkene yapılan her atamaya veya başvuruya yönelik kodun hiçbir etkisi olmasa bile oluşturulması gerekir.

   `volatile` Tek başına `int` kullanılırsa varsayılır. `volatile` Tür belirleyicisi özel bellek konumlarına güvenilir erişim sağlamak için kullanılabilir. Aynı `volatile` anda programları veya bellek eşlemeli g/ç denetim kayıtları gibi özel donanımları kullanarak, sinyal işleyicileri tarafından erişilebilen veya değiştirilen veri nesneleriyle birlikte kullanın. Bir değişkeni `volatile` ömrü boyunca bildirebilir veya tek bir başvuruyu olacak `volatile`şekilde dönüştürebilirsiniz.

- Bir öğe hem **const** hem de olabilir `volatile`, bu durumda öğe kendi programı tarafından meşru bir şekilde değiştirilemez ancak bazı zaman uyumsuz işlemler tarafından değiştirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)
