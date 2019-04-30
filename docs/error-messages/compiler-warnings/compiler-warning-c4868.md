---
title: Derleyici Uyarısı C4868
ms.date: 10/26/2017
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
ms.openlocfilehash: d0bc8716e53e71c52f6a31036a95d0b4cefedd79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388715"
---
# <a name="compiler-warning-level-4-c4868"></a>Derleyici Uyarısı (düzey 4) C4868

> '_dosya_(*line_number*)' derleyici küme ayracıyla belirtilen Başlatıcı listesinde soldan sağa Değerlendirme sırasını zorla

Bir küme ayracıyla belirtilen Başlatıcı listesinde soldan sağa sırada değerlendirilecek öğeleridir. Derleyici olduğu bu düzeni olmasını garanti etmek mümkün iki durum vardır: ilk değere göre; geçirilen nesneleri öğelerin bazıları ise ile derlerken, ikincisi ise `/clr` ve bazı öğeleri alanlar nesne veya dizi öğeleri. Derleyici, soldan sağa değerlendirmesi garanti edemez zaman uyarısı C4868 yayar.

Bu uyarı, Visual C++ 2015 güncelleştirme 2 için yapılmış derleyici uyumluluğu iş sonucu olarak oluşturulabilir. Visual C++ 2015 güncelleştirme 2 önce derlenmiş kod, şimdi C4868 oluşturabilirsiniz.

Varsayılan olarak bu uyarıyı kapalıdır. Kullanım `/Wall` bu uyarıyı etkinleştirmek için.

Bu uyarıyı çözmek için önce başlatıcı listesi öğeleri soldan sağa değerlendirme sırası bağımlı yan etki değerlendirme öğelerinin ne zaman üretebilir gibi gerekli olup olmadığını göz önünde bulundurun. Çoğu durumda, öğeleri değerlendirilme sırasını gözlemlenebilir bir etkisi yok.

Soldan sağa Değerlendirme sırasını olması gerekiyorsa, öğeleri geçirmek mümkün olup olmadığını göz önünde bulundurun `const` yerine başvuru. Bunun gibi bir değişiklik, aşağıdaki kod örneği'nde uyarı ortadan kaldırır.

## <a name="example"></a>Örnek

Bu örnek, C4868 oluşturur ve bunu düzeltmek için bir yol gösterir:

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