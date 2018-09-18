---
title: özellik (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- property_cpp
dev_langs:
- C++
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7388fd180da4bd82b343d193f62c30ff1069342
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064938"
---
# <a name="property-c"></a>property (C++)

**Microsoft'a özgü**

Bu öznitelik, bir sınıf veya yapı tanımında statik olmayan için "sanal veri üyeleri" uygulanabilir. Derleyici, işlev çağrılarını başvurularını değiştirerek bu "sanal veri üyeleri" veri üyeleri olarak değerlendirir.

## <a name="syntax"></a>Sözdizimi

```
   __declspec( property( get=get_func_name ) ) declarator
   __declspec( property( put=put_func_name ) ) declarator
   __declspec( property( get=get_func_name, put=put_func_name ) ) declarator
```

## <a name="remarks"></a>Açıklamalar

Derleyici bu özniteliği ile bildirilen bir üye seçme işlecinin sağ tarafındaki bir veri üyesi gördüğünde ("**.**"veya"**->**"), işlemi dönüştürür bir `get` veya `put` işlevi, böyle bir ifade bir lvalue ya da bir r olmasına bağlı olarak. Daha fazla bağlam gibi karmaşık "`+=`", bir yeniden yazma hem de yaparak gerçekleştirilir `get` ve `put`.

Bu öznitelik, bir sınıf veya yapı tanımı boş bir dizi bildirimi içinde de kullanılabilir. Örneğin:

```cpp
__declspec(property(get=GetX, put=PutX)) int x[];
```

Yukarıdaki ifadeyi gösterir `x[]` bir veya daha fazla dizi dizinleri ile kullanılabilir. Bu durumda, `i=p->x[a][b]` içine açık `i=p->GetX(a, b)`, ve `p->x[a][b] = i` içinde kapatılacak `p->PutX(a, b, i);`

**END Microsoft özgü**

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