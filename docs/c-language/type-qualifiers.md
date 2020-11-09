---
title: Tür Niteleyicileri
description: Microsoft Visual C derleyicisi 'nda kullanılan C dili için tür niteleyicileri açıklar
ms.date: 11/6/2020
helpviewer_keywords:
- volatile keyword [C], type qualifier
- type qualifiers
- volatile keyword [C]
- qualifiers for types
- const keyword [C]
- memory, access using volatile
- volatile keyword [C], type specifier
ms.assetid: bb4c6744-1dd7-40a8-b4eb-f5585be30908
ms.openlocfilehash: dd36aeb5d142eebbd6e4a339fe6c18925a6fd45a
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381616"
---
# <a name="type-qualifiers"></a>Tür Niteleyicileri

Tür niteleyicileri bir tanımlayıcıya iki özelliklerden birini verir. **`const`** Tür niteleyicisi, değiştirilemeyen bir nesne bildirir. **`volatile`** Tür niteleyicisi, değeri, benzer bir şekilde yürütülen iş parçacığı gibi, göründüğü programın denetimi dışında bir şey tarafından meşru bir şekilde değiştirilebilen bir öğe bildirir.

Tür niteleyicileri,, **`const`** **`restrict`** , ve **`volatile`** , bir bildirimde yalnızca bir kez bulunabilir. Tür niteleyicileri herhangi bir tür belirticisiyle görünebilir; Ancak, birden çok öğe bildiriminde ilk virgülden sonra yer alamaz. Örneğin, aşağıdaki bildirimler geçerlidir:

```c
typedef volatile int VI;
const int ci;
```

Bu bildirimler geçerli değildir:

```c
typedef int *i, volatile *vi;
float f, const cf;
```

Tür niteleyicileri yalnızca tanımlayıcılardaki l-Values olarak erişim için geçerlidir. L-Values ve ifadeler hakkında bilgi için bkz. [l-Value ve R-Value ifadeleri](../c-language/l-value-and-r-value-expressions.md) .

## <a name="syntax"></a>Syntax

*`type-qualifier`* :\
&emsp;**`const`**\
&emsp;**`restrict`**\
&emsp;**`volatile`**

## <a name="const-and-volatile"></a>`const` ve `volatile`

Aşağıdakiler geçerlidir **`const`** ve **`volatile`** bildirimlerdir:

```c
int const *p_ci;      // Pointer to constant int
int const (*p_ci);   // Pointer to constant int
int *const cp_i;     // Constant pointer to int
int (*const cp_i);   // Constant pointer to int
int volatile vint;     // Volatile integer
```

Bir dizi türünün belirtimi tür niteleyicileri içeriyorsa, öğesi dizi türü değil, nitelenir. İşlev türü belirtimi niteleyiciler içeriyorsa, davranış tanımsızdır. **`volatile`** ve **`const`** nesnenin değer aralığını veya aritmetik özelliklerini etkilemez.

- **`const`** Anahtar sözcüğü herhangi bir temel veya toplama türünü ya da herhangi bir türdeki bir nesneyi veya bir işaretçiyi değiştirmek için kullanılabilir **`typedef`** . Bir öğe yalnızca **`const`** tür niteleyicisi ile bildirilirse, türü **const int** olarak alınır. Bir **`const`** değişken, depolama alanının salt tanımlı bir bölgesine başlatılabilir veya yerleştirilebilir. **`const`** Anahtar sözcüğü, **`const`** işlevin işaretçiyi herhangi bir şekilde değiştirmesinin gerekli olmadığı için işaretçilerin bildirilmesi için yararlıdır.

- Derleyici, programda herhangi bir noktada bir **`volatile`** değişkene, değerini kullanan veya değiştiren bilinmeyen bir işlem tarafından erişilebileceği varsayılır. Komut satırında belirtilen iyileştirmelere bakılmaksızın, bir değişkene yapılan her atamaya veya başvuruya yönelik kodun **`volatile`** hiçbir etkisi olmasa bile oluşturulması gerekir.

**`volatile`** Tek başına kullanılırsa **`int`** varsayılır. **`volatile`** Tür belirleyicisi özel bellek konumlarına güvenilir erişim sağlamak için kullanılabilir. **`volatile`** Aynı anda programları veya bellek eşlemeli g/ç denetim kayıtları gibi özel donanımları kullanarak, sinyal işleyicileri tarafından erişilebilen veya değiştirilen veri nesneleriyle birlikte kullanın. Bir değişkeni **`volatile`** ömrü boyunca bildirebilir veya tek bir başvuruyu olacak şekilde dönüştürebilirsiniz **`volatile`** .

- Bir öğe her ikisi de olabilir **`const`** ve **`volatile`** Bu durumda, öğe kendi programı tarafından meşru bir şekilde değiştirilemez ancak bazı zaman uyumsuz işlemler tarafından değiştirilebilir.
 
## `restrict`

**`restrict`** C99 içinde tanıtılan tür niteleyicisi, işaretçi bildirimlerine uygulanabilir. İşaretçiyi, işaret ettiği şeyi uygun değil, nitelendirir.

**`restrict`** , geçerli kapsamdaki başka bir işaretçinin aynı bellek konumunu başvurduğu derleyicinin en iyi duruma getirme ipucisidir. Diğer bir deyişle, işaretçinin ömrü boyunca nesneye erişmek için yalnızca işaretçi veya ondan türetilmiş bir değer (işaretçi + 1 gibi) kullanılır. Bu, derleyicinin daha iyileştirilmiş kod üretmesine yardımcı olur. C++ eşdeğeri bir mekanizmaya sahiptir, [`__restrict`](../cpp/extension-restrict.md)

**`restrict`** Siz ve derleyici arasında bir anlaşma olduğunu aklınızda bulundurun. İle işaretlenmiş bir işaretçiye diğer ad yaparsanız **`restrict`** , sonuç tanımsızdır.

Şunu kullanan bir örnek aşağıdadır **`restrict`** :

```c
void test(int* restrict first, int* restrict second, int* val)
{
    *first += *val;
    *second += *val;
}

int main()
{
    int i = 1, j = 2, k = 3;
    test(&i, &j, &k);

    return 0;
}

// Marking union members restrict tells the compiler that
// only z.x or z.y will be accessed in any scope, which allows
// the compiler to optimize access to the members.
union z 
{
    int* restrict x;
    double* restrict y;
};
```

## <a name="see-also"></a>Ayrıca bkz.

[`/std` (Dil standart sürümünü belirt)](../build/reference/std-specify-language-standard-version.md)\
[Bildirimler ve türler](../c-language/declarations-and-types.md)
