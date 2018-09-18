---
title: Anonim sınıf türleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f194bcae9710b68a0be6a0c4d25a9f47f3340064
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090184"
---
# <a name="anonymous-class-types"></a>Anonim Sınıf Türleri

Sınıflar, anonim olabilir — diğer bir deyişle, bunlar olmadan bildirilebilir bir *tanımlayıcı*. Bir sınıf adını değiştirmeniz gerektiğinde bu faydalıdır bir **typedef** adı olduğu aşağıdaki gibi:

```cpp
typedef struct
{
    unsigned x;
    unsigned y;
} POINT;
```

> [!NOTE]
>  Önceki örnekte gösterilen anonim sınıflar kullanımını, var olan C kodu ile koruma uyumluluğu için kullanışlıdır. Bazı C kodunda kullanımını **typedef** anonim yapılar ile birlikte yaygın olan.

Anonim sınıflar, ayrıca bir başvuru sınıfının üyesi değil içerdiği şekilde aşağıdaki gibi ayrı bir sınıf içinde görünür istediğinizde yararlıdır:

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

Önceki kodda, `iValue` nesne üye seçme işleci kullanılarak erişilebilir (**.**) gibi:

```cpp
int i = ptv.iValue;
```

Belirli kısıtlamalara anonim sınıflardır. (Anonim birleşimler hakkında daha fazla bilgi için bkz: [birleşimler](../cpp/unions.md).) Anonim sınıflar:

- Bir oluşturucu veya yıkıcıya sahip olamaz.

- (Tür denetimi üç nokta simgesini kullanarak engellenmediğinden olmadığı sürece) işlevleri için bağımsız değişken olarak geçirilemez.

- İşlevlerin dönüş değerleri olarak döndürülemez.

## <a name="anonymous-structs"></a>Anonim yapılar

### <a name="microsoft-specific"></a>Microsoft'a Özgü

Microsoft C uzantısı bir ad vererek olmadan başka bir yapı içinde bir yapısı değişkenini bildirmek sağlar. Anonim yapılar bu iç içe geçmiş yapılar çağrılır. C++ anonim yapılar izin vermez.

Üyeleri içeren yapısında değilmiş gibi anonim bir yapının üyelerine erişebilir.

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

**END Microsoft özgü**