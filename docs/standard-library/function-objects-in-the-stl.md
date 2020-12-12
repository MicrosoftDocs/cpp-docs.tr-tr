---
description: Daha fazla bilgi için bkz. C++ standart kitaplığı 'ndaki Işlev nesneleri
title: C++ standart kitaplığındaki işlev nesneleri
ms.date: 03/15/2019
helpviewer_keywords:
- functors
- C++ Standard Library, functors
- C++ Standard Library, function objects
- function objects
ms.assetid: 85f8a735-2c7b-4f10-9c4d-95c666ec4192
ms.openlocfilehash: b87db43fbaabf1e9be18c56185ee190e3b2cbcac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324258"
---
# <a name="function-objects-in-the-c-standard-library"></a>C++ standart kitaplığındaki işlev nesneleri

Bir *işlev nesnesi* veya *functor*, işleç () uygulayan herhangi bir türdür. Bu işleç, *çağrı işleci* veya bazen *uygulama işleci* olarak adlandırılır. C++ standart kitaplığı, birincil olarak kapsayıcı ve algoritmalarda sıralama ölçütü olarak işlev nesnelerini kullanır.

İşlev nesneleri, düz bir işlev çağrısının üzerinde iki temel avantaj sağlar. Birincisi, bir işlev nesnesinin durum içerebildiği durumdur. İkincisi, bir işlev nesnesinin bir tür olması ve bu nedenle şablon parametresi olarak kullanılması olabilir.

## <a name="creating-a-function-object"></a>Işlev nesnesi oluşturma

Bir işlev nesnesi oluşturmak için, bir tür oluşturun ve işleç () uygulayın; örneğin:

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

İşlevin son satırı, `main` işlev nesnesini nasıl çağrılacağını gösterir. Bu çağrı bir işleve çağrı gibi görünür, ancak gerçekte functor türünde operator () öğesini çağırmış olur. İşlev nesnesi ve işlev çağırma arasındaki benzerlik, işlev nesnesinin terimi hakkında nasıl geldiği.

## <a name="function-objects-and-containers"></a>İşlev nesneleri ve kapsayıcılar

C++ standart kitaplığı, üstbilgi dosyasında çeşitli işlev nesneleri içerir [\<functional>](../standard-library/functional.md) . Bu işlev nesnelerinin bir kullanımı kapsayıcılar için sıralama ölçütünüz. Örneğin, `set` kapsayıcı şu şekilde bildirilmiştir:

```cpp
template <class Key,
    class Traits=less<Key>,
    class Allocator=allocator<Key>>
class set
```

İkinci şablon bağımsız değişkeni, Function nesnesidir `less` . Bu işlev nesnesi, **`true`** ilk parametrenin ikinci parametreden küçük olup olmadığını döndürür. Bazı kapsayıcılar öğelerini sıraladığı için kapsayıcının iki öğe karşılaştırması için bir yol gerekir. Karşılaştırma işlevi nesnesi kullanılarak yapılır. Bir işlev nesnesi oluşturup kapsayıcı için şablon listesinde belirterek, kapsayıcılar için kendi sıralama ölçütlerinizi tanımlayabilirsiniz.

## <a name="function-objects-and-algorithms"></a>İşlev nesneleri ve algoritmaları

İşlevsel nesnelerin başka bir kullanımı algoritmalarda bulunur. Örneğin, `remove_if` algoritma şu şekilde bildirilmiştir:

```cpp
template <class ForwardIterator, class Predicate>
ForwardIterator remove_if(
    ForwardIterator first,
    ForwardIterator last,
    Predicate pred);
```

Son bağımsız değişkeni, `remove_if` bir Boole değeri (bir *koşul*) döndüren bir işlev nesnesidir. İşlev nesnesinin sonucu ise **`true`** , öğesi yineleyiciler ve tarafından erişilmekte olan kapsayıcıdan kaldırılır `first` `last` . Bağımsız değişken için üst bilgide belirtilen işlev nesnelerinden herhangi birini kullanabilir [\<functional>](../standard-library/functional.md) `pred` veya kendi kendinizinkini oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
