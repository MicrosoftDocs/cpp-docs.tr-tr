---
description: 'Hakkında daha fazla bilgi edinin: seed_seq sınıfı'
title: seed_seq Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::seed_seq
- random/std::seed_seq::result_type
- random/std::seed_seq::generate
- random/std::seed_seq::size
- random/std::seed_seq::param
helpviewer_keywords:
- std::seed_seq [C++]
- std::seed_seq [C++], result_type
- std::seed_seq [C++], generate
- std::seed_seq [C++], size
- std::seed_seq [C++], param
ms.assetid: cba114f7-9ac6-4f2f-b773-9c84805401d6
ms.openlocfilehash: c92bda66b37162bcaaf9c614185f2c31f29d22c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197042"
---
# <a name="seed_seq-class"></a>seed_seq Sınıfı

Rastgele sayı altyapısı için rastgele bir çekirdek sağlayabilecek işaretsiz tamsayı değerlerinin bir vektörünü depolar.

## <a name="syntax"></a>Syntax

```cpp
class seed_seq
   {
public:
   // types
   typedef unsigned int result_type;

   // constructors
   seed_seq();
   template <class T>
      seed_seq(initializer_list<T> initlist);
   template <class InputIterator>
      seed_seq(InputIterator begin, InputIterator end);

   // generating functions
   template <class RandomAccessIterator>
      void generate(RandomAccessIterator begin, RandomAccessIterator end);

   // property functions
   size_t size() const;
   template <class OutputIterator>
      void param(OutputIterator dest) const;

   // no copy functions
   seed_seq(const seed_seq&) = delete;
   void operator=(const seed_seq&) = delete;
   };
```

## <a name="types"></a>Türler

```cpp
typedef unsigned int result_type;
```

Çekirdek dizisinin öğelerinin türü. 32 bitlik işaretsiz bir tamsayı türü.

## <a name="constructors"></a>Oluşturucular

```cpp
seed_seq();
```

Varsayılan Oluşturucu, boş bir iç diziye sahip olacak şekilde başlatılır.

```cpp
template<class T>
seed_seq(initializer_list<T> initlist);
```

`initlist`İç diziyi ayarlamak için kullanır.
`T` bir tamsayı türü olmalıdır.

```cpp
template<class InputIterator>
seed_seq(InputIterator begin, InputIterator end);
```

Belirtilen giriş Yineleyici aralığındaki tüm öğeleri kullanarak iç diziyi başlatır.
`iterator_traits<InputIterator>::value_type` bir tamsayı türü olmalıdır.

## <a name="members"></a>Üyeler

### <a name="generating-functions"></a>Işlev oluşturma

```cpp
template<class RandomAccessIterator>
void generate(RandomAccessIterator begin,
          RandomAccessIterator end);
```

İç algoritma kullanarak, belirtilen dizinin öğelerini doldurur. Bu algoritma, başlatıldığı iç sıra tarafından etkilenir `seed_seq` .
İse hiçbir şey yapmaz `begin == end` .

### <a name="property-functions"></a>Özellik İşlevleri

```cpp
size_t size() const;
```

İçindeki öğelerin sayısını döndürür `seed_seq` .

```cpp
template<class OutputIterator>
void param(OutputIterator dest) const;
```

İç diziyi çıkış yineleyiciye kopyalar `dest` .

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, üç Oluşturucu alıştırmaları `seed_seq` sağlar ve bir diziye atandığında elde edilen örneklerden çıkış üretir. `seed_seq`Rastgele sayı Oluşturucu ile kullanan bir örnek için bkz [\<random>](../standard-library/random.md) ..

```cpp
#include <iostream>
#include <random>
#include <string>
#include <array>

using namespace std;

void test(const seed_seq& sseq) {
    cout << endl << "seed_seq::size(): " << sseq.size() << endl;

    cout << "seed_seq::param(): ";
    ostream_iterator<unsigned int> out(cout, " ");
    sseq.param(out);
    cout << endl;

    cout << "Generating a sequence of 5 elements into an array: " << endl;
    array<unsigned int, 5> seq;
    sseq.generate(seq.begin(), seq.end());
    for (unsigned x : seq) { cout << x << endl; }
}

int main()
{
    seed_seq seed1;
    test(seed1);

    seed_seq seed2 = { 1701, 1729, 1791 };
    test(seed2);

    string sstr = "A B C D"; // seed string
    seed_seq seed3(sstr.begin(), sstr.end());
    test(seed3);
}
```

```Output
seed_seq::size(): 0
seed_seq::param():
Generating a sequence of 5 elements into an array:
505382999
163489202
3932644188
763126080
73937346

seed_seq::size(): 3
seed_seq::param(): 1701 1729 1791
Generating a sequence of 5 elements into an array:
1730669648
1954224479
2809786021
1172893117
2393473414

seed_seq::size(): 7
seed_seq::param(): 65 32 66 32 67 32 68
Generating a sequence of 5 elements into an array:
3139879222
3775111734
1084804564
2485037668
1985355432
```

## <a name="remarks"></a>Açıklamalar

Bu sınıfın üye işlevleri özel durum oluşturmaz.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
