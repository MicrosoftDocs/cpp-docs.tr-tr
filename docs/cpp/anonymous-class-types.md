---
title: Anonim Sınıf Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
ms.openlocfilehash: e227f48588c3c4f59c0d0bd28ab16178de159b58
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032089"
---
# <a name="anonymous-class-types"></a>Anonim Sınıf Türleri

Sınıflar anonim olabilir - yani, bir *tanımlayıcı*olmadan ilan edilebilir. Bu, bir sınıf adını aşağıdaki gibi **bir typedef** adı ile değiştirdiğinizde yararlıdır:

```cpp
typedef struct
{
    unsigned x;
    unsigned y;
} POINT;
```

> [!NOTE]
> Önceki örnekte gösterilen anonim sınıfların kullanımı, varolan C koduyla uyumluluğu korumak için yararlıdır. Bazı C kodlarında, **adsız** yapılarla birlikte typedef kullanımı yaygındır.

Anonim sınıflar, bir sınıf üyesine yapılan bir başvurunun aşağıdaki gibi ayrı bir sınıfta bulunmuyormuş gibi görünmesini istediğinizde de yararlıdır:

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

Yukarıdaki kodda, `iValue` nesne üye seçim işleci (**.**) kullanılarak aşağıdaki gibi erişilebilir:

```cpp
int i = ptv.iValue;
```

Anonim sınıflar belirli kısıtlamalara tabidir. (Anonim sendikalar hakkında daha fazla bilgi için [bkz.](../cpp/unions.md) Anonim sınıflar:

- Bir yapıcı veya yıkıcı olamaz.

- Işlevlere bağımsız değişken olarak geçirilemez (elips kullanılarak tür denetimi yenilmedikçe).

- İşlevlerden iade değerleri olarak döndürülemez.

## <a name="anonymous-structs"></a>Anonim structs

**Microsoft'a Özgü**

Microsoft C uzantısı, bir ad vermeden başka bir yapı içinde bir yapı değişkenini bildirmenize olanak tanır. Bu iç içe yapılara anonim yapılar denir. C++ anonim yapılara izin vermez.

Anonim bir yapının üyelerine, içerdiği yapıdaki üye gibi erişebilirsiniz.

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

**END Microsoft Özel**
