---
title: Artırma ve Azaltma İşleci Aşırı Yüklemesi (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
ms.openlocfilehash: 8d64f0af994f88d0f4ecd3a5921de4a16b8bdaaa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178295"
---
# <a name="increment-and-decrement-operator-overloading-c"></a>Artırma ve Azaltma İşleci Aşırı Yüklemesi (C++)

Artırma ve azaltma işleçleri, her birinin iki çeşidi olduğu için özel bir kategorinin kapsamına girer:

- Artırma öncesi ve artırma sonrası

- Azaltma öncesi ve azaltma sonrası

Aşırı yüklenmiş işleç işlevleri yazdığınızda, bu işleçlerin önek ve sonek sürümleri için ayrı sürümler uygulamak yararlı olabilir. İki arasında ayrım yapmak için aşağıdaki kural gözlemlenmiştir: işlecin önek formu, diğer birli işleçle tamamen aynı şekilde bildirilmiştir; sonek formu **int**türünde ek bir bağımsız değişken kabul eder.

> [!NOTE]
>  Artırma veya azaltma işlecinin sonek biçimi için aşırı yüklenmiş bir işleç belirtirken, ek bağımsız değişken **int**türünde olmalıdır; başka herhangi bir türün belirtilmesi bir hata oluşturur.

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

Artırma veya azaltma işlecinin sonek biçimini gösteren **int** türünde bağımsız değişken, bağımsız değişkenleri geçirmek için yaygın olarak kullanılmaz. Genellikle 0 değerini içerir. Ancak, aşağıdaki şekilde de kullanılabilir:

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

Yukarıdaki kodda gösterildiği gibi, bu değerleri geçirmek için artırma veya azaltma işleçlerine yönelik açık çağrıdan başka sözdizimi yoktur. Bu işlevselliği uygulamak için daha basit bir yol, toplama/atama işlecinin ( **+=** ) aşırı yüklenmesine yönelik bir yoldur.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)
