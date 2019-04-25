---
title: C++ Standart kitaplığındaki işlev nesneleri
ms.date: 03/15/2019
helpviewer_keywords:
- functors
- C++ Standard Library, functors
- C++ Standard Library, function objects
- function objects
ms.assetid: 85f8a735-2c7b-4f10-9c4d-95c666ec4192
ms.openlocfilehash: 310d846285612ad94ec9d66672fcb996557b07e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159372"
---
# <a name="function-objects-in-the-c-standard-library"></a>C++ Standart kitaplığındaki işlev nesneleri

A *işlev nesnesi*, veya *functor*, operator() uygulayan herhangi bir tür. Bu işleç olarak adlandırılır *çağrısı işleci* veya bazen *uygulama işleci*. C++ Standart Kitaplığı, öncelikli olarak sıralama ölçütü kapsayıcılar ve algoritmaları olarak işlev nesneleri kullanır.

İşlev nesneleri, düz bir işleve iki ana avantajları sağlar. İlk işlev nesnesi durumu içerebilmesidir. İkinci bir işlev nesnesi bir tür ve bu nedenle bir şablon parametresi kullanılabilir olduğunu.

## <a name="creating-a-function-object"></a>Bir işlev nesnesi oluşturma

Bir işlev nesnesi oluşturmak için bir tür oluşturmak ve operator(), aşağıdaki gibi uygulayın:

```cpp
class Functor
{
public:
    int operator()(int a, int b)
    {
        return a < b;
    }
};

int main()
{
    Functor f;
    int a = 5;
    int b = 7;
    int ans = f(a, b);
}
```

Son satırının `main` işlevi, işlev nesnesi çağırmanızı nasıl gösterir. Bu çağrı bir işlev, ancak onun gerçekten çağıran operator() Functor türü için bir çağrı şuna benzer. Bir işlev nesnesi ve bir işlev çağırma arasında bu benzerlik terimi işlev nesnesi nasıl çıktığını ' dir.

## <a name="function-objects-and-containers"></a>İşlev nesneleri ve kapsayıcıları

C++ Standart Kitaplığı içinde birden fazla işlev nesneleri içeren [ \<işlevsel >](../standard-library/functional.md) üst bilgi dosyası. Bir işlev nesneleri Bu kapsayıcılar için bir sıralama ölçütü olarak kullanılır. Örneğin, `set` kapsayıcısı gibi bildirilir:

```cpp
template <class Key,
    class Traits=less<Key>,
    class Allocator=allocator<Key>>
class set
```

İkinci şablon bağımsız değişkeni işlev nesnesidir `less`. Bu işlev nesnesi döndürür **true** ilk parametre küçükse değerinden ikinci parametre. Bazı kapsayıcıları öğeleri sıralama olduğundan, kapsayıcıyı iki öğeyi karşılaştıran bir yol gerekir. Karşılaştırma işlevi nesnesini kullanarak gerçekleştirilir. Kendi sıralama ölçütü kapsayıcılar için bir işlev nesnesi oluşturma ve bu kapsayıcı için şablon listesinde belirterek tanımlayabilirsiniz.

## <a name="function-objects-and-algorithms"></a>İşlev nesneleri ve algoritmaları

Başka bir işlev nesneleri algoritmaları kullanılır. Örneğin, `remove_if` algoritması gibi bildirilir:

```cpp
template <class ForwardIterator, class Predicate>
ForwardIterator remove_if(
    ForwardIterator first,
    ForwardIterator last,
    Predicate pred);
```

Son bağımsız değişkeninin `remove_if` bir Boole değeri döndüren bir işlev nesnesi (bir *koşul*). İşlev nesnesinin sonucu **true**, öğe yineleyiciler tarafından erişilen kapsayıcısından kaldırılır `first` ve `last`. Bildirilen işlev nesneleri dilediğinizi kullanabilirsiniz [ \<işlevsel >](../standard-library/functional.md) bağımsız değişkeni için üst bilgi `pred` veya kendi oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
