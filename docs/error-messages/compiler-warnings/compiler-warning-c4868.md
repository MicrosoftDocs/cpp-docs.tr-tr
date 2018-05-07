---
title: Derleyici Uyarısı C4868 | Microsoft Docs
ms.date: 10/26/2017
ms.topic: error-reference
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 922a1a8434da8449758b9d55ebe89ace2f262cd5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4868"></a>Derleyici Uyarısı (düzey 4) C4868

> '_dosya_(*line_number*)' derleyici zorla küme ayracı içine alınan Başlatıcı listesinde soldan sağa değerlendirme sırası

Bir küme ayracı içine alınan başlatıcı listesi soldan sağa sırada değerlendirilecek öğeleridir. Derleyici olduğu bu düzeni olmasını garanti etmek mümkün iki durum vardır: öğeleri değeriyle; geçirilen nesneleri bazıları ilk olduğunda ile derleme yapılırken saniyedir `/clr` ve bazı öğeler nesnelerin alanlar veya dizi öğeleridir. Derleyici soldan sağa değerlendirme garanti edemez olduğunda uyarı C4868 yayar.

Bu uyarı, Visual C++ 2015 güncelleştirme 2 için yapılmıştır derleyici uyumluluğu iş sonucu olarak oluşturulabilir. Visual C++ 2015 güncelleştirme 2 önce derlenmiş kod artık C4868 oluşmasına neden olabilir.

Varsayılan olarak bu uyarı kapalıdır. Kullanım `/Wall` bu uyarıyı etkinleştirmek için.

Bu uyarıyı çözmek için önce Başlatıcı liste öğelerini soldan sağa değerlendirmesi değerlendirme öğelerin sırasını bağımlı yan etkileri zaman üretebilir gibi gerekli olup olmadığını göz önünde bulundurun. Çoğu durumda, hangi öğelerin değerlendirilme sırasını observable bir etkisi yoktur.

Değerlendirme sırası soldan sağa olmalıdır, öğeleri geçirmek mümkün olup olmadığını değerlendirin `const` yerine başvuru. Bunun gibi bir değişiklik, aşağıdaki kod örneğinde uyarı ortadan kaldırır.

## <a name="example"></a>Örnek

Bu örnek C4868 oluşturur ve düzeltmek için bir yol gösterir:

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