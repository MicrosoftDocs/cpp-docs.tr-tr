---
description: 'Daha fazla bilgi edinin: anonim sınıf türleri'
title: Anonim Sınıf Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
ms.openlocfilehash: 91cc86602e4f9ead4d9da272e9cca4299be18e5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288229"
---
# <a name="anonymous-class-types"></a>Anonim Sınıf Türleri

Sınıflar anonim olabilir — diğer bir deyişle, bir *tanımlayıcı* olmadan bildirilebilecek. Bu, aşağıdaki gibi bir sınıf adını bir adla değiştirdiğiniz zaman yararlıdır **`typedef`** :

```cpp
typedef struct
{
    unsigned x;
    unsigned y;
} POINT;
```

> [!NOTE]
> Önceki örnekte gösterilen anonim sınıfların kullanımı, var olan C koduyla uyumluluğu korumak için yararlıdır. Bazı C kodunda, **`typedef`** anonim yapılarla birlikte kullanılması yaygındır.

Anonim sınıflar Ayrıca, bir sınıf üyesine başvurusunun, aşağıdaki gibi ayrı bir sınıfta yer olmamasına rağmen görünmesini istediğinizde de yararlı olur:

```cpp
struct PTValue
{
    POINT ptLoc;
    union
    {
        int  iValue;
        long lValue;
    };
};

PTValue ptv;
```

Önceki kodda, `iValue` nesne üye seçme işleci (**.**) kullanılarak şu şekilde erişilebilir:

```cpp
int i = ptv.iValue;
```

Anonim sınıflar belirli kısıtlamalara tabidir. (Anonim birleşimler hakkında daha fazla bilgi için bkz. [birleşimler](../cpp/unions.md).) Anonim sınıflar:

- Bir oluşturucuya veya yıkıcıya sahip olamaz.

- İşlevlere bağımsız değişken olarak geçirilemez (tür denetimi üç nokta kullanılarak ertelenememişse).

- İşlevlerden dönüş değeri olarak döndürülemez.

## <a name="anonymous-structs"></a>Anonim yapılar

**Microsoft'a Özgü**

Microsoft C uzantısı, bir yapı değişkenini bir ad vermeden başka bir yapı içinde bildirmenize olanak tanır. Bu iç içe yapılar anonim yapılar olarak adlandırılır. C++ anonim yapılara izin vermez.

Anonim yapının üyelerine, kendisini kapsayan yapıda Üyeler gibi erişebilirsiniz.

```cpp
// anonymous_structures.c
#include <stdio.h>

struct phone
{
    int  areacode;
    long number;
};

struct person
{
    char   name[30];
    char   gender;
    int    age;
    int    weight;
    struct phone;    // Anonymous structure; no name needed
} Jim;

int main()
{
    Jim.number = 1234567;
    printf_s("%d\n", Jim.number);
}
//Output: 1234567
```

**SON Microsoft 'a özgü**
