---
title: "Derleyici Hatası C2672 | Microsoft Docs"
ms.date: 10/24/2017
ms.technology:
- cpp-tools
ms.topic: error-reference
f1_keywords:
- C2672
dev_langs:
- C++
helpviewer_keywords:
- C2672
ms.assetid: 7e86338a-2d4b-40fe-9dd2-ac6886f3f31a
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52663aed470aff254d07cba6a65f484269d8703d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2672"></a>Derleyici Hatası C2672

> '*işlevi*': eşleşme bulundu işlevi aşırı yüklenmiş

Derleyici belirtilen işlev eşleşen bir aşırı yüklenmiş işlevi bulunamadı. İşlev parametreleri veya eşleşen bir işlev eşleme alır gereken erişilebilirlik bağlamda sahip bulundu.

Belirli standart kitaplığı kapsayıcıları veya algoritmaları tarafından kullanıldığında, türlerinizi erişilebilir üyeleri veya kapsayıcı veya algoritması gereksinimlerini arkadaş işlevleri sağlamanız gerekir. Örneğin, yineleyici türlerini türetmek `std::iterator<>`. Türü bir sol hem sağ işleneni olarak kabul karşılaştırma işlemleri veya diğer işleçler kapsayıcı öğe türleri üzerinde kullanımını gerektirebilir. Sağ işleneni işlecinin uygulama türü bir üye olmayan işlevi gerektirebilir türünü kullanın.

## <a name="example"></a>Örnek

Visual Studio 2017 önce derleyici sürümler bazı şablon bağlamlarında nitelenmiş adlar denetimi erişim gerçekleştirmedi. Bu, beklenen SFINAE davranışı değiştirme bir ad inaccessibility nedeniyle başarısız olmasına beklenirken etkileyebilir. Bu olası kilitlenme veya yanlış işleci yanlış yüklemesini çağırma derleyici nedeniyle çalışma zamanında beklenmeyen davranışlara neden olmuş. Visual Studio 2017 ' bir derleyici hatası oluştu.

Bu örnek, Visual Studio 2015'te derler ancak Visual Studio 2017 bir hata oluşturur. Bu sorunu gidermek için burada değerlendirilir şablon parametresi üye erişilebilir yapın.

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