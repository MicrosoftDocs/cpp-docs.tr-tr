---
description: 'Daha fazla bilgi edinin: Özellik (C++)'
title: property (C++)
ms.date: 11/04/2016
f1_keywords:
- property_cpp
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
ms.openlocfilehash: ed996ecadd16837af1e28b71bbedd9b4e3c1abaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299169"
---
# <a name="property-c"></a>property (C++)

**Microsoft'a Özgü**

Bu öznitelik, bir sınıf veya yapı tanımında statik olmayan "sanal veri üyelerine" uygulanabilir. Derleyici, bu "sanal veri üyeleri" ni, başvurularını işlev çağrılarına değiştirerek veri üyeleri olarak değerlendirir.

## <a name="syntax"></a>Syntax

```
   __declspec( property( get=get_func_name ) ) declarator
   __declspec( property( put=put_func_name ) ) declarator
   __declspec( property( get=get_func_name, put=put_func_name ) ) declarator
```

## <a name="remarks"></a>Açıklamalar

Derleyici, üye seçme işlecinin ("**.**" veya "") sağında Bu öznitelikle belirtilen bir veri üyesi gördüğünde, **->** `get` `put` böyle bir ifadenin l değeri mi yoksa r değeri mi olduğuna bağlı olarak, işlemi or işlevine dönüştürür. "" Gibi daha karmaşık bağlamlarda `+=` , hem hem de yaparak bir yeniden yazma işlemi gerçekleştirilir `get` `put` .

Bu öznitelik, bir sınıf veya yapı tanımında boş bir dizinin bildiriminde de kullanılabilir. Örneğin:

```cpp
__declspec(property(get=GetX, put=PutX)) int x[];
```

Yukarıdaki ifade, `x[]` bir veya daha fazla dizi dizini ile kullanılabileceğini gösterir. Bu durumda, kapatılacak ve şu şekilde kapatılacak `i=p->x[a][b]` `i=p->GetX(a, b)` `p->x[a][b] = i``p->PutX(a, b, i);`

**SON Microsoft 'a özgü**

## <a name="example"></a>Örnek

```cpp
// declspec_property.cpp
struct S {
   int i;
   void putprop(int j) {
      i = j;
   }

   int getprop() {
      return i;
   }

   __declspec(property(get = getprop, put = putprop)) int the_prop;
};

int main() {
   S s;
   s.the_prop = 5;
   return s.the_prop;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
