---
title: Derleyici hatası C2672
ms.date: 10/24/2017
f1_keywords:
- C2672
helpviewer_keywords:
- C2672
ms.assetid: 7e86338a-2d4b-40fe-9dd2-ac6886f3f31a
ms.openlocfilehash: 9f844b54285a7df69bfb4387a7afcc82dfef9252
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177137"
---
# <a name="compiler-error-c2672"></a>Derleyici hatası C2672

> '*Function*': eşleşen aşırı yüklenmiş işlev bulunamadı

Derleyici, belirtilen işlevle eşleşen aşırı yüklenmiş bir işlev bulamadı. Eşleşen parametrelere sahip hiçbir işlev bulunamadı veya hiçbir eşleşen işlev bağlamda gerekli erişilebilirliği yok.

Belirli standart kitaplık kapsayıcıları veya algoritmaları tarafından kullanıldığında, türleriniz, kapsayıcının veya algoritmanın gereksinimlerini karşılayan erişilebilir Üyeler veya arkadaş işlevleri sağlamalıdır. Örneğin, yineleyici türleriniz `std::iterator<>`türetmelidir. Kapsayıcı öğesi türlerinde karşılaştırma işlemleri veya diğer işleçlerin kullanımı, türün hem sol hem de sağ işlenen olarak değerlendirilmesini gerektirebilir. Türün bir sağ işlenen olarak kullanılması, işlecin üye olmayan bir işlev olarak türünün uygulanmasını gerektirebilir.

## <a name="example"></a>Örnek

Visual Studio 2017 ' den önceki derleyici sürümleri, bazı şablon bağlamlarındaki nitelikli adlar üzerinde erişim denetimi gerçekleştirmedi. Bu, bir adın erişilebilirliği nedeniyle değiştirmenin başarısız olması beklenen SFıNAE davranışının kesintiye uğramasına neden olabilir. Derleyici, işlecin yanlış aşırı yüklemesini hatalı bir şekilde çağırdığından, bu durum, çalışma zamanında kilitlenme veya beklenmeyen davranışlara neden olmuş olabilir. Visual Studio 2017 ' de bir derleyici hatası tetiklenir.

Bu örnek, Visual Studio 2015 ' de derlenir ancak Visual Studio 2017 ' de bir hata oluşturur. Bu sorunu onarmak için, şablon parametresi üyesini değerlendirildiği yerde erişilebilir yapın.

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
