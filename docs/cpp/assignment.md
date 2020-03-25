---
title: Atama
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
ms.openlocfilehash: f1697a8de3dff6c46de01db6bbff5447c03b6282
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190709"
---
# <a name="assignment"></a>Atama

Atama işleci ( **=** ), tam olarak bir ikili işleçtir. Bildirimi, aşağıdaki özel durumlarla, diğer herhangi bir ikili işleçle aynıdır:

- Bu, statik olmayan bir üye işlevi olmalıdır. Hiçbir **işleç =** üye olmayan bir işlev olarak bildirilemez.
- Türetilmiş sınıflar tarafından devralınmaz.
- Bir varsayılan **operator =** işlevi, hiçbiri yoksa sınıf türleri için derleyici tarafından oluşturulabilir.

Aşağıdaki örnek, bir atama işlecinin nasıl bildirileceğini göstermektedir:

```cpp
class Point
{
public:
    int _x, _y;

    // Right side of copy assignment is the argument.
    Point& operator=(const Point&);
};

// Define copy assignment operator.
Point& Point::operator=(const Point& otherPoint)
{
    _x = otherPoint._x;
    _y = otherPoint._y;

    // Assignment operator returns left side of assignment.
    return *this;
}

int main()
{
    Point pt1, pt2;
    pt1 = pt2;
}
```

Sağlanan bağımsız değişken ifadenin sağ tarafındadır. İşleci, atama işlemi tamamlandıktan sonra sol taraftaki değeri döndüren atama işlecinin davranışını korumak için nesnesini döndürür. Bu, aşağıdaki gibi atamaların zincirlemesini sağlar:

```cpp
pt1 = pt2 = pt3;
```

Kopya atama işleci, kopya Oluşturucusu ile karıştırılmamalıdır. İkincisi, var olan bir nesneden yeni bir nesne oluşturma sırasında çağrılır:

```cpp
// Copy constructor is called--not overloaded copy assignment operator!
Point pt3 = pt1;

// The previous initialization is similar to the following:
Point pt4(pt1); // Copy constructor call.
```

> [!NOTE]
> Bir kopya atama işleci tanımlayan bir sınıfın, kopya oluşturucuyu, yıkıcıyı ve C++ 11 ' den başlayarak, oluşturucuyu taşıma ve taşıma atama işlecinden de açıkça tanımlanacağını belirten [üç kural](https://en.wikipedia.org/wiki/Rule_of_three_(C%2B%2B_programming)) izlemeniz önerilir.

## <a name="see-also"></a>Ayrıca bkz.

- [İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)
- [Kopya Oluşturucuları ve Kopya Atama İşleçleri (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md)
