---
title: Artırma ve Azaltma İşleci Aşırı Yüklemesi (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
ms.openlocfilehash: 10cda57b74a7da57f2d48b91854b5d37c8d181f1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186990"
---
# <a name="increment-and-decrement-operator-overloading-c"></a>Artırma ve Azaltma İşleci Aşırı Yüklemesi (C++)

Artırma ve azaltma işleçleri, her birinin iki çeşidi olduğu için özel bir kategorinin kapsamına girer:

- Artırma öncesi ve artırma sonrası

- Azaltma öncesi ve azaltma sonrası

Aşırı yüklenmiş işleç işlevleri yazdığınızda, bu işleçlerin önek ve sonek sürümleri için ayrı sürümler uygulamak yararlı olabilir. İki arasında ayrım yapmak için aşağıdaki kural gözlemlenmiştir: işlecin önek formu, diğer birli işleçle tamamen aynı şekilde bildirilmiştir; sonek formu, türünde ek bir bağımsız değişken kabul eder **`int`** .

> [!NOTE]
> Artırma veya azaltma işlecinin sonek biçimi için aşırı yüklenmiş bir operatör belirtirken, ek bağımsız değişken türünde olmalıdır **`int`** ; başka herhangi bir türün belirtilmesi bir hata oluşturur.

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

**`int`** Artırma veya azaltma işlecinin sonek biçimini gösteren türünün bağımsız değişkeni, bağımsız değişkenleri geçirmek için yaygın olarak kullanılmaz. Genellikle 0 değerini içerir. Ancak, aşağıdaki şekilde de kullanılabilir:

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

Yukarıdaki kodda gösterildiği gibi, bu değerleri geçirmek için artırma veya azaltma işleçlerine yönelik açık çağrıdan başka sözdizimi yoktur. Bu işlevi gerçekleştirmenin daha basit bir yolu, toplama/atama işlecinin () aşırı yüklenmesi kullanmaktır **+=** .

## <a name="see-also"></a>Ayrıca bkz.

[İşleç aşırı yüklemesi](../cpp/operator-overloading.md)
