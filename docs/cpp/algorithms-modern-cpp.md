---
title: Algoritmalar (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 872644533a0fab73768392efa2c5cd016b6bb980
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095663"
---
# <a name="algorithms-modern-c"></a>Algoritmalar (Modern C++)

Modern C++ programlama için algoritmaları kullandığınız olan öneririz [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md). Önemli bazı örnekler şunlardır:

- **for_each**, varsayılan algoritmasıdır geçişi. (Ayrıca **dönüştürme** için değil, yerinde semantiği.)

- **find_if**, varsayılan arama algoritması olduğu.

- **Sıralama**, **lower_bound**, sıralama ve arama algoritmaları diğer varsayılan.

Karşılaştırıcı yazmak için katı kullanın **<** ve *adlandırılmış lambdalar* zaman şunları yapabilirsiniz.

```cpp
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );
```

## <a name="loops"></a>Döngüler

Mümkün olduğunda, aralık tabanlı kullanın **için** döngüler veya algoritma çağrılarını ya da her ikisi de el ile yazılmış döngüler yerine. **kopyalama**, **dönüştürme**, **count_if**, **remove_if**, ve bunların amacı açıktır olduğundan, bunlar gibi diğerleri döngülerden daha iyidir ve hatasız kodlar yazmayı kolaylaştırmak. Ayrıca, birçok C++ Standart Kitaplığı algoritması daha verimli hale uygulama iyileştirmelerine sahiptir.

Bunun gibi eski C++ yerine:

```cpp
for ( auto i = strings.begin(); i != strings.end(); ++i ) {
    /* ... */
}

auto i = v.begin();

for ( ; i != v.end(); ++i ) {
    if (*i > x && *i < y) break;
}
```

Modern C++ şu şekilde kullanın:

```cpp
for_each( begin(strings), end(strings), [](string& s) {
  // ...
} );

auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; } );
```

### <a name="range-based-for-loops"></a>Aralık tabanlı for döngüleri

Aralık tabanlı **için** döngü olan bir C ++ 11 dil özelliğidir, C++ Standart Kitaplığı algoritması. Ancak, döngüler hakkındaki bu tartışmada ilgiyi gerektirir. Aralık tabanlı **için** döngüler'ın bir uzantısı olan **için** anahtar sözcüğü ve bir değer aralığı boyunca üzerinde yineleme yapan döngüler yazmak için kullanışlı ve etkili bir yol sağlar. C++ Standart Kitaplığı kapsayıcıları, dizeleri ve diziler için aralık tabanlı **için** döngüleri. Bu yineleme sözdizimini kullanıcı tanımlı türüne yönelik etkinleştirmek için aşağıdaki desteği ekleyin:

- A `begin` yapının başlangıcına bir yineleyici döndüren bir yöntemi ve bir `end` yapının sonuna bir yineleyici döndüren yöntemi.

- Bu yöntemler için yineleyicide destek: **işleci**<strong>\*</strong>, **işleç! =**, ve **operator ++** (önek sürüm).

Bu yöntemler, üye veya tek başına çalışan işlevler olabilir.

## <a name="random-numbers"></a>Rastgele sayılar

SIR değildir, eski CRT `rand()` en length C++ topluluğu içinde açıklanan pek çok fabrikadan işlevi vardır. Modern C++'da, bu eksiklikleri ile uğraşmak zorunda değildir — ne de kendi birörnek dağıtılmış rastgele sayı üreticisinin stok zorunda — hızla ve kolayca bunları oluşturmaya yönelik araçlar C++ Standart kitaplığında kullanılabilir olmadığından gösterildiği[ \<rastgele >](../standard-library/random.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
