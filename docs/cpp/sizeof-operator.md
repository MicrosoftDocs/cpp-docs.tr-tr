---
title: sizeof İşleci
ms.date: 11/04/2016
f1_keywords:
- sizeof_cpp
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
ms.openlocfilehash: 8789bb5e0e363458edffa7207ea1e138aae4d284
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365577"
---
# <a name="sizeof-operator"></a>sizeof İşleci

Tip **char**boyutuna göre operand boyutunu verir.

> [!NOTE]
> `sizeof ...` Operatör hakkında daha fazla bilgi için [Elipsler ve Variadic Şablonlar'a](../cpp/ellipses-and-variadic-templates.md)bakın.

## <a name="syntax"></a>Sözdizimi

```
sizeof unary-expression
sizeof  ( type-name )
```

## <a name="remarks"></a>Açıklamalar

Işlecinin **boyutlarının** `size_t`sonucu, stddef.h> dosyada \<tanımlanan integral bir türdir. Bu işleç, programlarınızda makineye bağlı veri boyutları belirtmekten kaçınmanızı sağlar.

Operand **boyutlar** için aşağıdakilerden biri olabilir:

- Bir tür adı. Bir tür adı ile **boyutları** kullanmak için, adı parantez içinde eklenmelidir.

- Bir deyim. Bir ifade ile kullanıldığında, parantez li veya parantezsiz **boyutlar** belirtilebilir. İfade değerlendirilmez.

**Işlecinin boyutları** **char**türündeki bir nesneye uygulandığında, 1 verir. İşleç **boyutu** bir diziye uygulandığında, dizi tanımlayıcısı tarafından temsil edilen işaretçinin boyutunu değil, bu dizideki toplam bayt sayısını verir. Dizi tanımlayıcısı tarafından temsil edilen işaretçinin boyutunu elde etmek için, **boyutlar**kullanan bir işleve parametre olarak geçirin. Örneğin:

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

İşleç **boyutları** bir **sınıfa**, yapı veya **struct** **birleşim** türüne uygulandığında, sonuç, bu tür bir nesnedeki bayt sayısı ve üyeleri sözcük sınırlarına hizalamak için eklenen dolgu sayısıdır. Sonuç, tek tek üyelerin depolama gereksinimlerini ekleyerek hesaplanan boyuta karşılık gelmez. [/Zp](../build/reference/zp-struct-member-alignment.md) derleyici seçeneği ve [paket](../preprocessor/pack.md) pragma üyeleri için hizalama sınırlarını etkiler.

İşleticinin **boyutları** boş bir sınıf için bile asla 0 verir.

İşleticinin **boyutları** aşağıdaki operandlarla kullanılamaz:

- Işlev. (Ancak, **boyutlar** işlevlere işaretçilere uygulanabilir.)

- Bit alanları.

- Tanımlanmamış sınıflar.

- Tür **geçersiz**.

- Dinamik olarak ayrılmış diziler.

- Dış diziler.

- Eksik türleri.

- Eksik türlerin parantez adı.

Bir başvuruya işleç **boyutları** uygulandığında, sonuç nesnenin kendisine uygulanmış gibi **olur.**

Boyutsuz bir dizi bir yapının son öğesi ise, işleç **boyutları** dizi olmadan yapının boyutunu döndürür.

**İşleçboyutu** genellikle formun bir ifadesini kullanarak bir dizideki öğe sayısını hesaplamak için kullanılır:

```cpp
sizeof array / sizeof array[0]
```

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
