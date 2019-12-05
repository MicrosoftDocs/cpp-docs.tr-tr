---
title: Derleyici Uyarısı C4868
ms.date: 10/26/2017
f1_keywords:
- C4868
helpviewer_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
ms.openlocfilehash: c1d49eb61a5c7c47fa83dacb39ed50f42e0fb147
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810485"
---
# <a name="compiler-warning-level-4-c4868"></a>Derleyici Uyarısı (düzey 4) C4868

> '_File_(*Line_Number*) ' derleyicisi, örgü Başlatıcı listesinde soldan sağa değerlendirme sırasını zorlamaz

Bir örgü Başlatıcı listesinin öğeleri soldan sağa sırada değerlendirilir. Derleyicinin bu sırayı garanti edemediği iki durum vardır: ilki, bazı öğeler değere göre geçirilir; İkincisi `/clr` ile derlerken, bazı öğeler nesnelerin alanları veya dizi öğeleridir. Derleyici soldan sağa değerlendirmeyi garanti edemediği zaman, uyarı C4868 yayar.

Bu uyarı, Visual Studio 2015 güncelleştirme 2 için yapılan derleyici uygunluk işinin bir sonucu olarak oluşturulabilir. Visual Studio 2015 güncelleştirme 2 ' den önce derlenen kod artık C4868 oluşturabilir.

Bu uyarı varsayılan olarak kapalıdır. Bu uyarıyı etkinleştirmek için `/Wall` kullanın.

Bu uyarıyı çözmek için ilk olarak, öğe değerlendirmesi sıra bağımlı yan etkileri oluşturabilecek gibi, başlatıcı listesi öğelerinin sol-sağ değerlendirmesinin gerekip gerekmediğini göz önünde bulundurun. Birçok durumda, öğelerin değerlendirildiği sıranın bir observable etkisi yoktur.

Değerlendirme sırası soldan sağa doğru olmalıdır, bunun yerine öğeleri `const` başvuruya göre geçirmek mümkün olup olmadığını göz önünde bulundurun. Bu gibi bir değişiklik, aşağıdaki kod örneğindeki uyarıyı ortadan kaldırır.

## <a name="example"></a>Örnek

Bu örnek C4868 oluşturur ve bunu çözmek için bir yol gösterir:

```cpp
// C4868.cpp
// compile with: /c /Wall
#include <cstdio>

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x): x(x) {}

    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)
    {
        printf("Constructing %d\n", h.x);
    }
};

class TripWarning4868
{
public:
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}

    // This variation will not trigger the warning:
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}
};

int main()
{
    HasCopyConstructor a{1};
    HasCopyConstructor b{2};

    // the warning will indicate the below line, the usage of the braced initializer list.
    TripWarning4868 warningOnThisLine{a, b};
};
```