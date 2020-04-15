---
title: Artırma ve Azaltma İşleci Aşırı Yüklemesi (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
ms.openlocfilehash: 40ae12130fdced9fd958c3b8316fa3b718ca9b5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374125"
---
# <a name="increment-and-decrement-operator-overloading-c"></a>Artırma ve Azaltma İşleci Aşırı Yüklemesi (C++)

Artırma ve azaltma işleçleri, her birinin iki çeşidi olduğu için özel bir kategorinin kapsamına girer:

- Artırma öncesi ve artırma sonrası

- Azaltma öncesi ve azaltma sonrası

Aşırı yüklenmiş işleç işlevleri yazdığınızda, bu işleçlerin önek ve sonek sürümleri için ayrı sürümler uygulamak yararlı olabilir. İkisini birbirinden ayırmak için aşağıdaki kurala uyulur: İşleticinin önek formu diğer tekerişlez işleçle aynı şekilde beyan edilir; postfix formu türü **int**ek bir bağımsız değişkeni kabul eder.

> [!NOTE]
> Artış veya decrement işlecinin postfix formu için aşırı yüklü bir işleci belirtirken, ek bağımsız değişken tür **int**olmalıdır; başka bir tür belirterek bir hata oluşturur.

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

Artış veya decrement işlecinin postfix formunu gösteren tür **int** bağımsız değişkeni bağımsız değişkeni bağımsız değişkenleri geçmek için yaygın olarak kullanılmaz. Genellikle 0 değerini içerir. Ancak, aşağıdaki şekilde de kullanılabilir:

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

Yukarıdaki kodda gösterildiği gibi, bu değerleri geçirmek için artırma veya azaltma işleçlerine yönelik açık çağrıdan başka sözdizimi yoktur. Bu işlevselliği uygulamanın daha kolay bir yolu, ekleme/atama işlecinin aşırı yüklenmesidir (**+=**).

## <a name="see-also"></a>Ayrıca bkz.

[Operatör Aşırı Yükleme](../cpp/operator-overloading.md)
