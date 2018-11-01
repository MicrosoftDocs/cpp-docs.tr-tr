---
title: Derleyici Hatası C2672
ms.date: 10/24/2017
f1_keywords:
- C2672
helpviewer_keywords:
- C2672
ms.assetid: 7e86338a-2d4b-40fe-9dd2-ac6886f3f31a
ms.openlocfilehash: df0f656c9db23739ec62629088b9cc5f7950a92d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570449"
---
# <a name="compiler-error-c2672"></a>Derleyici Hatası C2672

> '*işlevi*': eşleşen aşırı yüklenmiş işlev bulunamadı

Derleyicinin, belirtilen işlev eşleşen bir aşırı yüklenmiş işlev bulunamadı. Parametreleri veya eşleşen hiçbir işlev eşleşen alır bağlamda gerekli erişilebilirlik sahip hiçbir işlev bulunamadı.

Belirli standart kitaplığı kapsayıcıları veya algoritmalar tarafından kullanıldığında, türlerinizi erişilebilir üyeler veya kapsayıcı ya da algoritma gereksinimlerini karşılayan arkadaş işlevleri sağlamanız gerekir. Örneğin, yineleyici türlerinizi türetilmesi `std::iterator<>`. Türü bir sol hem bir sağ taraf işleneni olarak kabul karşılaştırma işlemleri veya diğer işleçlerin kapsayıcı öğe türleri kullanımını gerektirebilir. Sağ işleneninin türü bir üye olmayan işlev uygulaması işlecinin gerektirebilir gibi türünü kullanın.

## <a name="example"></a>Örnek

Visual Studio 2017 önce derleyici sürümleri, bazı şablon bağlamlarında nitelenmiş adlar denetimi erişim gerçekleştirmedi. Bu, burada değiştirme adının inaccessibility nedeniyle başarısız olması bekleniyor, beklenen SFINAE davranışı etkileyebilir. Bu büyük olasılıkla bir kilitlenme veya yanlış yanlış İşleç aşırı yüklemesini çağırmak derleyici nedeniyle çalışma zamanında beklenmeyen davranışlara neden olmuş. Visual Studio 2017'de, bir derleyici hatası oluşturulur.

Bu örnek, Visual Studio 2015'te derler ancak Visual Studio 2017'de bir hata oluşturur. Bu sorunu gidermek için nereden değerlendirilir şablon parametresi üyesinin erişilebilir olun.

```cpp
#include <type_traits>

template <class T> class S {
// public:    // Uncomment this line to fix
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x)
{
    return (x == 0);
}

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```