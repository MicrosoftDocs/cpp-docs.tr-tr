---
title: Artırma ve azaltma işleci aşırı yüklemesi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1356860fa43cea322078550dd5a7d9de0fd9154c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037248"
---
# <a name="increment-and-decrement-operator-overloading-c"></a>Artırma ve Azaltma İşleci Aşırı Yüklemesi (C++)

Artırma ve azaltma işleçleri, her birinin iki çeşidi olduğu için özel bir kategorinin kapsamına girer:

- Artırma öncesi ve artırma sonrası

- Azaltma öncesi ve azaltma sonrası

Aşırı yüklenmiş işleç işlevleri yazdığınızda, bu işleçlerin önek ve sonek sürümleri için ayrı sürümler uygulamak yararlı olabilir. İki tür arasında ayrım yapmak için aşağıdaki kural uygulanır: işlecin önek biçimi herhangi diğer birli işleç; tam olarak aynı şekilde bildirilir. sonek biçimi ek bağımsız değişken türü kabul eden **int**.

> [!NOTE]
>  Artırma veya azaltma işlecinin sonek biçimi için aşırı yüklenmiş bir işleç belirtilirken, ek bağımsız değişken türü olmalıdır **int**; herhangi bir tür belirtilmesi bir hata oluşturur.

Aşağıdaki örnekte, `Point` sınıfı için önek ve sonek artırma ve azaltma işleçlerinin nasıl tanımlanacağı gösterilmektedir:

```cpp
// increment_and_decrement1.cpp
class Point
{
public:
   // Declare prefix and postfix increment operators.
   Point& operator++();       // Prefix increment operator.
   Point operator++(int);     // Postfix increment operator.

   // Declare prefix and postfix decrement operators.
   Point& operator--();       // Prefix decrement operator.
   Point operator--(int);     // Postfix decrement operator.

   // Define default constructor.
   Point() { _x = _y = 0; }

   // Define accessor functions.
   int x() { return _x; }
   int y() { return _y; }
private:
   int _x, _y;
};

// Define prefix increment operator.
Point& Point::operator++()
{
   _x++;
   _y++;
   return *this;
}

// Define postfix increment operator.
Point Point::operator++(int)
{
   Point temp = *this;
   ++*this;
   return temp;
}

// Define prefix decrement operator.
Point& Point::operator--()
{
   _x--;
   _y--;
   return *this;
}

// Define postfix decrement operator.
Point Point::operator--(int)
{
   Point temp = *this;
   --*this;
   return temp;
}
int main()
{
}
```

Aşağıdaki işlev başlıkları kullanılarak dosya kapsamında aynı işleçler tanımlanabilir (genel olarak):

```cpp
friend Point& operator++( Point& )      // Prefix increment
friend Point& operator++( Point&, int ) // Postfix increment
friend Point& operator--( Point& )      // Prefix decrement
friend Point& operator--( Point&, int ) // Postfix decrement
```

Bağımsız değişken türü **int** , artış sonek biçimi gösterir veya azaltma işlecinin genellikle bağımsız değişkenleri geçirmek için kullanılmaz. Genellikle 0 değerini içerir. Ancak, aşağıdaki şekilde de kullanılabilir:

```cpp
// increment_and_decrement2.cpp
class Int
{
public:
    Int &operator++( int n );
private:
    int _i;
};

Int& Int::operator++( int n )
{
    if( n != 0 )    // Handle case where an argument is passed.
        _i += n;
    else
        _i++;       // Handle case where no argument is passed.
    return *this;
}
int main()
{
   Int i;
   i.operator++( 25 ); // Increment by 25.
}
```

Yukarıdaki kodda gösterildiği gibi, bu değerleri geçirmek için artırma veya azaltma işleçlerine yönelik açık çağrıdan başka sözdizimi yoktur. Bu işlevselliği uygulamak için daha basit bir yolu toplama/atama işlecini aşırı yüklemektir (**+=**).

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)