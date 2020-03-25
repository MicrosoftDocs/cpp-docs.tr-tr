---
title: sizeof İşleci
ms.date: 11/04/2016
f1_keywords:
- sizeof_cpp
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
ms.openlocfilehash: bc1165cf1df3933575013906d1b24673467f0b36
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178723"
---
# <a name="sizeof-operator"></a>sizeof İşleci

**Karakter**türü boyutuna göre işleneninin boyutunu verir.

> [!NOTE]
>  `sizeof ...` işleci hakkında daha fazla bilgi için bkz. [üç nokta ve değişken sayıda bağımsız değişken şablonları](../cpp/ellipses-and-variadic-templates.md).

## <a name="syntax"></a>Sözdizimi

```
sizeof unary-expression
sizeof  ( type-name )
```

## <a name="remarks"></a>Açıklamalar

**Sizeof** işlecinin sonucu, içerme dosyasında \<stddef. h > tanımlanan bir integral türü `size_t`türüdür. Bu işleç, programlarınızda makineye bağımlı veri boyutları belirtmekten kaçınmanızı sağlar.

**Sizeof** işleneni aşağıdakilerden biri olabilir:

- Bir tür adı. Bir tür adıyla **sizeof** kullanmak için, adın parantez içine alınması gerekir.

- Bir ifade. Bir ifadeyle kullanıldığında, **sizeof** parantez ile veya Ayraçsız olarak belirtilebilir. İfade değerlendirilmedi.

**Sizeof** işleci **char**türünde bir nesneye uygulandığında, 1 verir. Bir diziye **sizeof** işleci uygulandığında, dizi tanımlayıcısı tarafından temsil edilen işaretçinin boyutu değil, bu dizideki toplam bayt sayısını verir. Dizi tanımlayıcısı tarafından temsil edilen işaretçinin boyutunu almak için, bunu **sizeof**kullanan bir işleve parametre olarak geçirin. Örneğin:

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

**Sizeof** işleci bir **sınıfa**, **yapıya**veya **birleşim** türüne uygulandığında, sonuç bu türdeki bir nesnedeki bayt sayısıdır ve bir sözcük sınırlarındaki üyeleri hizalamak için herhangi bir doldurma eklenir. Sonuç, tek tek üyelerin depolama gereksinimleri eklenerek hesaplanan boyuta karşılık gelmez. [/ZP](../build/reference/zp-struct-member-alignment.md) derleyici seçeneği ve [Pack](../preprocessor/pack.md) pragma, Üyeler için hizalama sınırlarını etkiler.

**Sizeof** işleci boş bir sınıf için bile hiçbir şekilde 0 vermez.

**Sizeof** işleci aşağıdaki işlenenlerle birlikte kullanılamaz:

- Lerdir. (Ancak, **sizeof** işlevlere yönelik işaretçilere uygulanabilir.)

- Bit alanları.

- Tanımsız sınıflar.

- Tür **void**.

- Dinamik olarak ayrılan diziler.

- Dış diziler.

- Tamamlanmamış türler.

- Parantez içinde tamamlanmamış türlerin adları.

Bir başvuruya **sizeof** işleci uygulandığında, nesne, **sizeof** nesnesinin kendisi için uygulanmışsa aynı olur.

Boyutlandırılmış olmayan bir dizi bir yapının son öğesi ise, **sizeof** işleci dizi olmadan yapının boyutunu döndürür.

**Sizeof** işleci, genellikle bir dizideki öğelerin sayısını formun bir ifadesi kullanarak hesaplamak için kullanılır:

```cpp
sizeof array / sizeof array[0]
```

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
