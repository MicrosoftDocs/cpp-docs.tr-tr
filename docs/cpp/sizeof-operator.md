---
title: sizeof işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- sizeof_cpp
dev_langs:
- C++
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6445fb834982cd13348c9e94def4b75fe31c02e9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058827"
---
# <a name="sizeof-operator"></a>sizeof İşleci

İşlenenin türü bağlı boyutu verir **char**.

> [!NOTE]
>  Hakkında bilgi için `sizeof ...` işleci bkz [üç nokta ve Variadic şablonları](../cpp/ellipses-and-variadic-templates.md).

## <a name="syntax"></a>Sözdizimi

```
sizeof unary-expression
sizeof  ( type-name )
```

## <a name="remarks"></a>Açıklamalar

Sonucu **sizeof** işleci türüdür `size_t`, içerme dosyasında tanımlı bir integral türü \<stddef.h >. Bu işleç, programlarınızda makine bağımlı veri boyutları belirtmekten kaçının olanak tanır.

İşleneni **sizeof** aşağıdakilerden biri olabilir:

- Tür adı. Kullanılacak **sizeof** bir tür adıyla adı parantez içine alınmalıdır.

- Bir ifade. Bir ifade ile kullanıldığında **sizeof** ile veya parantezler olmadan belirtilebilir. İfade değerlendirilmez.

Zaman **sizeof** işleci türünde bir nesneye uygulanan **char**, 1 verir. Zaman **sizeof** işleci, bir diziye uygulandığında, bu dizide dizi tanımlayıcısı tarafından temsil edilen işaretçinin boyutu bayt sayısı verir. Dizi tanımlayıcısı tarafından temsil edilen işaretçinin boyutu elde etmek için bir parametre olarak kullanan bir işlevine geçirebileceğimiz **sizeof**. Örneğin:

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

Zaman **sizeof** işleci uygulanır bir **sınıfı**, **yapı**, veya **birleşim** sonuç türüdür, bir nesnenin bayt sayısı türü, artı sözcük sınırlarından üyelerini hizalamak için eklenen tüm doldurma. Sonuç tek tek üyelerin depolama gereksinimlerini toplayarak hesaplanan boyuta karşılık gelmiyor. [/ZP](../build/reference/zp-struct-member-alignment.md) derleyici seçeneği ve [paketi](../preprocessor/pack.md) pragması hizalama sınırları üyelerini etkiler.

**Sizeof** işleci, 0, boş bir sınıf için bile hiçbir zaman verir.

**Sizeof** işleci aşağıdaki işlenenleri ile birlikte kullanılamaz:

- İşlevler. (Ancak **sizeof** işaretçileri işlevlere uygulanabilir.)

- Bit alanları.

- Tanımlanmamış sınıflar.

- Türü **void**.

- Dinamik olarak ayrılan dizi.

- Dış diziler.

- Eksik türler.

- Eksik türleri parantez içine alınmış adları.

Zaman **sizeof** işleci bir başvuru uygulandığında, sonuç gibi **sizeof** nesnesine uygulanır.

Boyutsuz bir dizi bir yapının son öğesi ise **sizeof** işleci dizi olmadan yapının boyutunu döndürür.

**Sizeof** işleci genellikle bir ifade formu kullanarak bir dizideki öğelerin sayısını hesaplamak için kullanılır:

```cpp
sizeof array / sizeof array[0]
```

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)