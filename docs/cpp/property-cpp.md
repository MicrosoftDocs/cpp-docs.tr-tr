---
title: property (C++)
ms.date: 11/04/2016
f1_keywords:
- property_cpp
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
ms.openlocfilehash: 03f71739698fd20a01fd72567ce5b9babc176327
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179308"
---
# <a name="property-c"></a>property (C++)

**Microsoft 'a özgü**

Bu öznitelik, bir sınıf veya yapı tanımında statik olmayan "sanal veri üyelerine" uygulanabilir. Derleyici, bu "sanal veri üyeleri" ni, başvurularını işlev çağrılarına değiştirerek veri üyeleri olarak değerlendirir.

## <a name="syntax"></a>Sözdizimi

```
   __declspec( property( get=get_func_name ) ) declarator
   __declspec( property( put=put_func_name ) ) declarator
   __declspec( property( get=get_func_name, put=put_func_name ) ) declarator
```

## <a name="remarks"></a>Açıklamalar

Derleyici, bir üye seçim işlecinin (" **.** " veya " **->** ") sağında Bu öznitelikle belirtilen bir veri üyesini gördüğünde, böyle bir ifadenin l değeri veya r değeri olmasına bağlı olarak işlemi bir `get` veya `put` işlevine dönüştürür. "`+=`" gibi daha karmaşık bağlamlarda, hem `get` hem de `put`yaparak bir yeniden yazma işlemi gerçekleştirilir.

Bu öznitelik, bir sınıf veya yapı tanımında boş bir dizinin bildiriminde de kullanılabilir. Örneğin:

```cpp
__declspec(property(get=GetX, put=PutX)) int x[];
```

Yukarıdaki ifade `x[]`, bir veya daha fazla dizi diziniyle kullanılabileceğini gösterir. Bu durumda, `i=p->x[a][b]` `i=p->GetX(a, b)`açılır ve `p->x[a][b] = i` açılır `p->PutX(a, b, i);`

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
