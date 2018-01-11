---
title: "seed_seq sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::seed_seq
- random/std::seed_seq::result_type
- random/std::seed_seq::generate
- random/std::seed_seq::size
- random/std::seed_seq::param
dev_langs: C++
helpviewer_keywords:
- std::seed_seq [C++]
- std::seed_seq [C++], result_type
- std::seed_seq [C++], generate
- std::seed_seq [C++], size
- std::seed_seq [C++], param
ms.assetid: cba114f7-9ac6-4f2f-b773-9c84805401d6
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3eb5a5d383044e0e44a0913c06afa73c6fe2f0ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="seedseq-class"></a>seed_seq Sınıfı
Rastgele sayı altyapısı için rastgele çekirdek sağlayabilir imzasız tamsayı değerleri vektörü depolar.  
  
## <a name="syntax"></a>Sözdizimi  
```  
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
 `typedef unsigned int result_type;`   
Çekirdek dizisi öğelerin türü. Bir 32 bit işaretsiz tamsayıyı türü.  
  
## <a name="constructors"></a>Oluşturucular  
 `seed_seq();`   
Varsayılan Oluşturucu, boş bir iç sıra olmasını başlatır.  
  
 `template<class T>`   
 `seed_seq(initializer_list<T> initlist);`   
Kullanan `initlist` iç sırasını ayarlamak için.                   
`T`tamsayı türde olması gerekir.  
  
 `template<class InputIterator>`   
 `seed_seq(InputIterator begin, InputIterator end);`   
Sağlanan giriş yineleyici aralığında kullanan tüm öğeler iç dizisini başlatır.                  
`iterator_traits<InputIterator>::value_type`tamsayı türde olması gerekir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="generating-functions"></a>İşlevler oluşturma  
 `template<class RandomAccessIterator> void generate(RandomAccessIterator begin,          RandomAccessIterator end);`   
Bir iç algoritma kullanarak sağlanan sıradaki doldurur. Bu algoritma, iç dizisiyle etkilenen `seed_seq` başlatıldı.                          
Hiçbir şey yapmaz varsa `begin == end`.  
  
### <a name="property-functions"></a>Özellik İşlevleri  
 `size_t size() const;`   
Öğelerin sayısını döndürür `seed_seq`.  
  
 `template<class OutputIterator> void param(OutputIterator dest) const;`   
İç dizisi çıkış yineleyici kopyalar `dest`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde üç oluşturucular kullanır ve oluşan bir çıktı üretir `seed_seq` örnekleri bir dizi atandığında. Kullanan bir örnek `seed_seq` rastgele sayı üreticisinin ile bkz [ \<rastgele >](../standard-library/random.md).  
  
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
 Bu sınıfın üye işlevleri özel durumlar oluşturmayın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<rastgele >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<rastgele >](../standard-library/random.md)


