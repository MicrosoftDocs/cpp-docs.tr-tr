---
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
ms.openlocfilehash: 5309042e9f26875e0cf5c2024cc74910fef21148
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295727"
---
# <a name="seedseq-class"></a>seed_seq Sınıfı

Rastgele sayı altyapısı için rastgele bir tohum sağlayabilirsiniz işaretsiz tamsayı değerleri bir vektör depolar.

## <a name="syntax"></a>Sözdizimi

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

Çekirdek dizisinin öğelerinin türü. Bir 32-bit işaretsiz tamsayı türü.

## <a name="constructors"></a>Oluşturucular

```cpp
seed_seq();
```

Varsayılan Oluşturucu boş bir iç sıra olmasını başlatır.

```cpp
template<class T>
seed_seq(initializer_list<T> initlist);
```

Kullanan `initlist` iç sırasını ayarlamak için.
`T` bir tamsayı türü olmalıdır.

```cpp
template<class InputIterator>
seed_seq(InputIterator begin, InputIterator end);
```

Sağlanan giriş yineleyici aralıktaki tüm öğeleri kullanılarak iç dizisini başlatır.
`iterator_traits<InputIterator>::value_type` bir tamsayı türü olmalıdır.

## <a name="members"></a>Üyeler

### <a name="generating-functions"></a>İşlev oluşturma

```cpp
template<class RandomAccessIterator>
void generate(RandomAccessIterator begin,
          RandomAccessIterator end);
```

Bir iç algoritmaya kullanarak sağlanan dizisinin doldurur. Bu algoritma, iç dizisiyle etkilenen `seed_seq` başlatıldı.
Hiçbir şey yapmaz, `begin == end`.

### <a name="property-functions"></a>Özellik İşlevleri

```cpp
size_t size() const;
```

İçindeki öğelerin sayısını döndürür `seed_seq`.

```cpp
template<class OutputIterator>
void param(OutputIterator dest) const;
```

Çıkış yineleyici iç sıra kopyalar `dest`.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, üç oluşturucular sınayan ve oluşan bir çıktı üretir `seed_seq` örneklerini bir diziye atandığında. Kullanan bir örnek için `seed_seq` rastgele sayı üreticisinin ile bkz [ \<rastgele >](../standard-library/random.md).

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

Bu sınıfın üye işlevleri, özel durum oluşturması beklenmiyor.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
