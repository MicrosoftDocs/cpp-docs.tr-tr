---
description: 'Daha fazla bilgi edinin: sizeof Işleci'
title: sizeof İşleci
ms.date: 11/04/2016
f1_keywords:
- sizeof_cpp
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
ms.openlocfilehash: d4af55697a1466829e81f5eb220ffba72bf73f6a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116892"
---
# <a name="sizeof-operator"></a>sizeof İşleci

Türünün boyutuna göre işleneninin boyutunu verir **`char`** .

> [!NOTE]
> İşleci hakkında daha fazla bilgi için `sizeof ...` bkz. [üç nokta ve değişen sayıda bağımsız değişken şablonları](../cpp/ellipses-and-variadic-templates.md).

## <a name="syntax"></a>Syntax

```
sizeof unary-expression
sizeof  ( type-name )
```

## <a name="remarks"></a>Açıklamalar

**`sizeof`** İşlecin sonucu `size_t` , içerme dosyasında tanımlanan bir integral türü olan türüdür \<stddef.h> . Bu işleç, programlarınızda makineye bağımlı veri boyutları belirtmekten kaçınmanızı sağlar.

**`sizeof`** Öğesinin işleneni aşağıdakilerden biri olabilir:

- Bir tür adı. **`sizeof`** Bir tür adı ile kullanmak için, adın parantez içine alınması gerekir.

- Bir ifade. Bir ifadeyle kullanıldığında, **`sizeof`** parantez ile veya Ayraçsız olarak belirtilebilir. İfade değerlendirilmedi.

**`sizeof`** İşleci türündeki bir nesneye uygulandığında **`char`** , 1 verir. **`sizeof`** İşleci bir diziye uygulandığında, dizi tanımlayıcısının temsil ettiği işaretçinin boyutunda değil, bu dizideki toplam bayt sayısını verir. Dizi tanımlayıcısı tarafından temsil edilen işaretçinin boyutunu almak için, onu kullanan bir işleve parametre olarak geçirin **`sizeof`** . Örneğin:

## <a name="example"></a>Örnek

```cpp
#include <iostream>
using namespace std;

size_t getPtrSize( char *ptr )
{
   return sizeof( ptr );
}

int main()
{
   char szHello[] = "Hello, world!";

   cout  << "The size of a char is: "
         << sizeof( char )
         << "\nThe length of " << szHello << " is: "
         << sizeof szHello
         << "\nThe size of the pointer is "
         << getPtrSize( szHello ) << endl;
}
```

## <a name="sample-output"></a>Örnek Çıktı

```Output
The size of a char is: 1
The length of Hello, world! is: 14
The size of the pointer is 4
```

**`sizeof`** İşleci bir **`class`** , **`struct`** veya türüne uygulandığında, **`union`** sonuç bu türün bir nesnesindeki bayt sayısıdır ve üyeleri sözcük sınırları üzerinde hizalamak için herhangi bir doldurma eklenir. Sonuç, tek tek üyelerin depolama gereksinimleri eklenerek hesaplanan boyuta karşılık gelmez. [/ZP](../build/reference/zp-struct-member-alignment.md) derleyici seçeneği ve [Pack](../preprocessor/pack.md) pragma, Üyeler için hizalama sınırlarını etkiler.

**`sizeof`** İşleci boş bir sınıf için bile hiçbir şekilde 0 vermez.

**`sizeof`** İşleç aşağıdaki işlenenlerle kullanılamaz:

- Lerdir. (Ancak, **`sizeof`** işlev işaretçilerine uygulanabilir.)

- Bit alanları.

- Tanımsız sınıflar.

- Türü **`void`** .

- Dinamik olarak ayrılan diziler.

- Dış diziler.

- Tamamlanmamış türler.

- Parantez içinde tamamlanmamış türlerin adları.

**`sizeof`** İşleci bir başvuruya uygulandığında, sonuç **`sizeof`** nesnenin kendine uygulanmış gibi olur.

Boyutlandırılmış olmayan bir dizi bir yapının son öğesi ise, **`sizeof`** işleci dizi olmadan yapının boyutunu döndürür.

**`sizeof`** İşleci genellikle, bir dizideki öğelerin sayısını formun bir ifadesi kullanarak hesaplamak için kullanılır:

```cpp
sizeof array / sizeof array[0]
```

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
