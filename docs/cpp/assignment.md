---
title: Atama
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
ms.openlocfilehash: 1e6d715011cfaab7e250e23a9a31bb3f0c83f36a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184345"
---
# <a name="assignment"></a>Atama

Atama işleci (**=**), NET olarak söylemek gerekirse, ikili bir işleçtir. Aşağıdaki istisnalar herhangi diğer ikili işlecine bildiriminden aynıdır:

- Statik olmayan üye işlevi olmalıdır. Hayır **işleç =** değiştiricilere işlevi olarak bildirilebilir.
- Türetilmiş sınıflar tarafından alınmadı.
- Varsayılan **işleç =** işlevi oluşturulabilir sınıf türleri için derleyici tarafından yoksa.

Aşağıdaki örnek, bir atama işleci bildirmek verilmektedir:

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

Sağlanan bağımsız değişken ifadesinin sağ tarafı ' dir. İşleci atama işlemi tamamlandıktan sonra sol tarafındaki değerini döndüren bir atama işleci davranışı korumak için nesneyi döndürür. Bu Atamalar, aşağıdaki gibi zincirleme sağlar:

```cpp
pt1 = pt2 = pt3;
```

Kopya atama işleci, kopya Oluşturucu ile karıştırılmamalıdır sağlamaktır. İkinci yeni bir nesne oluşturma sırasında var olan bir çağrılır:

```cpp
// Copy constructor is called--not overloaded copy assignment operator!
Point pt3 = pt1;

// The previous initialization is similar to the following:
Point pt4(pt1); // Copy constructor call.
```

> [!NOTE]
> İzlemeniz önerilir [üç kural](https://en.wikipedia.org/wiki/Rule_of_three_(C%2B%2B_programming)) kopya atama işlecine tanımlayan bir sınıf kopya oluşturucusunu da açıkça tanımlamanız gerekir, yok edici ve C ++ 11 ile başlayarak oluşturucusunu ve taşıma atama taşıma işleci.

## <a name="see-also"></a>Ayrıca bkz.

- [İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)
- [Kopya Oluşturucuları ve Kopya Atama İşleçleri (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md)