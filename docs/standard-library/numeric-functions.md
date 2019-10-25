---
title: '&lt;sayısal&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- numeric/std::accumulate
- numeric/std::adjacent_difference
- numeric/std::inner_product
- numeric/std::iota
- numeric/std::partial_sum
ms.assetid: a4b0449a-c80c-4a1d-8d9f-d7fcd0058f8b
helpviewer_keywords:
- std::accumulate [C++]
- std::adjacent_difference [C++]
- std::exclusive_scan [C++]
- std::gcd [C++]
- std::inclusive_scan [C++]
- std::inner_product [C++]
- std::iota [C++]
- std::lcm [C++]
- std::partial_sum [C++]
- std::reduce [C++]
- std::transform_exclusive_scan [C++]
- std::transform_inclusive_scan [C++]
- std::transform_reduce [C++]
ms.openlocfilehash: ab1e2942cbcfe568dd4c280c059fe0768493794c
ms.sourcegitcommit: 4b0928a1a497648d0d327579c8262f25ed20d02e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72889965"
---
# <a name="ltnumericgt-functions"></a>&lt;sayısal&gt; işlevleri

## <a name="accumulate"></a>accumulate

Ardışık kısmi toplamları hesaplayarak, belirli bir aralıktaki tüm öğelerin toplamını, bazı başlangıç değerleri de dahil olmak üzere, belirli bir ikili işlemi, toplamın dışında bir şekilde kullanarak hesaplar.

```cpp
template <class InputIterator, class Type>
Type accumulate(InputIterator first, InputIterator last, Type val);

template <class InputIterator, class Type, class BinaryOperation>
Type accumulate(
    InputIterator first,
    InputIterator last,
    Type val,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Parametreler

*ilk* \
Belirtilen bir ikili işleme göre toplanacak veya birleştirilecek aralıktaki ilk öğeyi ele almak için bir giriş Yineleyici.

*son* \
Yinelenen birikmeye dahil edilen son öğenin ötesinde bir konum olan belirtilen bir ikili işleme göre toplanacak veya birleştirilecek aralıktaki son öğeyi ele alan bir giriş Yineleyici.

*val* \
Her bir öğenin belirtilen bir ikili işleme göre eklendiği veya birleştirileceği bir başlangıç değeri.

*binary_op*\
Belirtilen aralıktaki her öğeye ve önceki uygulamalarının sonucuna uygulanacak olan ikili işlem.

### <a name="return-value"></a>Dönüş Değeri

İlk şablon işlevi için belirtilen aralıktaki *Val* ve tüm öğelerin toplamı, ya da ikinci şablon işlevi için, Sum işlemi yerine, belirtilen ikili işlemi uygulamanın sonucu, (*partialresult, \*Iter)* ), yani *PartialResult* işlemin önceki uygulamalarının sonucudur ve `Iter` aralıktaki bir öğeyi işaret eden bir yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk değer, Aralık boş olduğunda iyi tanımlanmış bir sonuç olacağını Yöntem, bu durumda *Val* değeri döndürülür. İkili işlemin ilişkilendirilebilir veya iletişim olması gerekmez. Sonuç ilk değer *Val* olarak başlatılır ve *sonuç* olarak = `binary_op` (*sonuç*, <strong>\*</strong>`Iter`) Aralık aracılığıyla tekrarlayarak hesaplanır; burada `Iter`, art arda işaret eden bir yineleyici olur Aralık içindeki öğe. Aralığın geçerli olması ve karmaşıklığın, aralığın boyutuyla doğrusal olması gerekir. Yineleme sırasında kapanış sağlamak için ikili işlecin dönüş türü **türüne** dönüştürülebilir olmalıdır.

### <a name="example"></a>Örnek

```cpp
// numeric_accum.cpp
// compile with: /EHsc
#include <vector>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2(20);
   vector <int>::iterator iter1, iter2;

   int i;
   for (i = 1; i < 21; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   // The first member function for the accumulated sum
   int total;
   total = accumulate(v1.begin(), v1.end(), 0);

   cout << "The sum of the integers from 1 to 20 is: "
        << total << "." << endl;

   // Constructing a vector of partial sums
   int j = 0, partotal;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      partotal = accumulate(v1.begin(), iter1 + 1, 0);
      v2[j] = partotal;
      j++;
   }

   cout << "The vector of partial sums is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function for the accumulated product
   vector <int> v3, v4(10);
   vector <int>::iterator iter3, iter4;

   int s;
   for (s = 1; s < 11; s++)
   {
      v3.push_back(s);
   }

   cout << "The original vector v3 is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl;

   int ptotal;
   ptotal = accumulate(v3.begin(), v3.end(), 1, multiplies<int>());

   cout << "The product of the integers from 1 to 10 is: "
        << ptotal << "." << endl;

   // Constructing a vector of partial products
   int k = 0, ppartotal;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++) {
      ppartotal = accumulate(v3.begin(), iter3 + 1, 1, multiplies<int>());
      v4[k] = ppartotal;
      k++;
   }

   cout << "The vector of partial products is:\n ( " ;
   for (iter4 = v4.begin(); iter4 != v4.end(); iter4++)
      cout << *iter4 << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The sum of the integers from 1 to 20 is: 210.
The vector of partial sums is:
( 1 3 6 10 15 21 28 36 45 55 66 78 91 105 120 136 153 171 190 210 ).

The original vector v3 is:
( 1 2 3 4 5 6 7 8 9 10 ).
The product of the integers from 1 to 10 is: 3628800.
The vector of partial products is:
( 1 2 6 24 120 720 5040 40320 362880 3628800 ).
```

## <a name="adjacent_difference"></a>adjacent_difference

Her bir öğe arasındaki art arda gelen farkları ve bir giriş aralığındaki kendi öncellerini hesaplar ve bir hedef aralığında sonuçların çıktısını alır veya fark işleminin başka bir belirtilen bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.

```cpp
template <class InputIterator, class OutIterator>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIterator, class BinaryOperation>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);

template <class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 adjacent_difference(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result);

template <class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2,
class BinaryOperation>
ForwardIterator2 adjacent_difference(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Parametreler

*ilk* \
Öğeleri karşılık gelen öncelleriyle fark kaydı yapılacak olan giriş aralığındaki ilk öğeyi ele alan veya değer çiftinin başka bir belirtilen ikili işlemde çalıştırılacağı bir giriş yineleyici.

*son* \
Öğeleri karşılık gelen öncelleriyle fark kaydı yapılacak olan giriş aralığındaki son öğeyi ele alan veya değer çiftinin başka bir belirtilen ikili işlemde çalıştırılacağı bir giriş yineleyici.

*sonuç*\
Fark dizilerinin veya belirtilen işlemin sonuçlarının depolanacağı hedef aralıktaki ilk öğeyi ele alan çıkış yineleyici.

*binary_op*\
Fark kayıt yordamındaki çıkarma işleminin yerini alan genelleştirilmiş işlemde uygulanacak olan ikili işlem.

### <a name="return-value"></a>Dönüş Değeri

Hedef aralığın sonunu adresleyen çıkış yineleyicisi: `result` + (`last` - `first`).

### <a name="remarks"></a>Açıklamalar

Çıkış Yineleyici *sonucunun* , *ilk*olarak giriş yineleyicisi ile aynı Yineleyici olmasına izin verilir, böylece `adjacent_difference` değerleri yerinde hesaplanabilir.

1, 2, 3 *, bir giriş aralığında bir değer dizisi*için, ilk şablon işlevi ardışık `partial_difference` değerlerini *bir*1 *, 2-* *a*1, a3- *a* *2,* hedef aralığında depolar.

1, 2, 3 *, bir giriş aralığında bir değer dizisi*için, ikinci şablon işlevi `partial_difference` art arda *1, 2*`binary_op` *bir* *1,* *3 `binary_op`* 2 *' dir*. aralığı.

Uygulanan işlem sırası belirtildiğinden, ikili işlem `binary_op` ilişkilendirilebilir veya iletişim olması gerekmez.

### <a name="example"></a>Örnek

```cpp
// numeric_adj_diff.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend, LIterend2;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t * t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the adjacent_differences of
   // elements in a list output to a vector
   VIterend = adjacent_difference ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "Output vector containing adjacent_differences is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the adjacent products of the elements in a list
   VIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the adjacent products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of adjacent_differences in place
   LIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "In place output adjacent_differences in list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend2 ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="exclusive_scan"></a>exclusive_scan

```cpp
template<class InputIterator, class OutputIterator, class T>
OutputIterator exclusive_scan(InputIterator first, InputIterator last,
OutputIterator result,
T init);
template<class InputIterator, class OutputIterator, class T, class BinaryOperation>
OutputIterator exclusive_scan(InputIterator first, InputIterator last,
OutputIterator result,
T init, BinaryOperation binary_op);
template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class T>
ForwardIterator2 exclusive_scan(ExecutionPolicy&& exec, 
ForwardIterator1 first, ForwardIterator1 last,
ForwardIterator2 result,
T init);
template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class T,
class BinaryOperation>
ForwardIterator2 exclusive_scan(ExecutionPolicy&& exec, 
ForwardIterator1 first, ForwardIterator1 last,
ForwardIterator2 result,
T init, BinaryOperation binary_op);
```

## <a name="gcd"></a>GCD

```cpp
template <class M, class N>
constexpr common_type_t<M,N> gcd(M m, N n);
```

## <a name="inclusive_scan"></a>inclusive_scan

```cpp
template<class InputIterator, class OutputIterator>
OutputIterator inclusive_scan(InputIterator first, InputIterator last,
OutputIterator result);
template<class InputIterator, class OutputIterator, class BinaryOperation>
OutputIterator inclusive_scan(InputIterator first, InputIterator last,
OutputIterator result,
BinaryOperation binary_op);
template<class InputIterator, class OutputIterator, class BinaryOperation, class T>
OutputIterator inclusive_scan(InputIterator first, InputIterator last,
OutputIterator result,
BinaryOperation binary_op, T init);
template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 inclusive_scan(ExecutionPolicy&& exec, 
ForwardIterator1 first, ForwardIterator1 last,
ForwardIterator2 result);
template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2,
class BinaryOperation>
ForwardIterator2 inclusive_scan(ExecutionPolicy&& exec, 
ForwardIterator1 first, ForwardIterator1 last,
ForwardIterator2 result,
BinaryOperation binary_op);
template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2,
class BinaryOperation, class T>
ForwardIterator2 inclusive_scan(ExecutionPolicy&& exec, 
ForwardIterator1 first, ForwardIterator1 last,
ForwardIterator2 result,
BinaryOperation binary_op, T init);
```

## <a name="inner_product"></a>inner_product

İki aralıktaki öğe odaklı ürünün toplamını hesaplar ve belirtilen bir başlangıç değerine ekler ya da Sum ve ürün ikili işlemlerinin diğer belirtilen ikili işlemlerle değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.

```cpp
template <class InputIterator1, class InputIterator2, class Type>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             val);

template <class InputIterator1, class InputIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             val,
    BinaryOperation1  binary_op1,
    BinaryOperation2  binary_op2);
```

### <a name="parameters"></a>Parametreler

*first1* \
İlk aralıktaki ilk öğeyi, ikinci aralıktaki iç ürünü veya Genelleştirilmiş iç ürünü ele almak için bir giriş Yineleyici.

*last1* \
İkinci aralıktaki iç ürün veya Genelleştirilmiş iç ürün olan ilk aralıktaki son öğeyi ele alarak bir giriş yineleyicisi hesaplanmalıdır.

*first2* \
İkinci aralıktaki ilk öğeyi, ilk aralıktaki iç ürünü veya Genelleştirilmiş iç ürünü ele almak için bir giriş Yineleyici.

*val* \
Aralık arasındaki iç ürünün veya Genelleştirilmiş iç ürünün ekleneceği başlangıç değeri.

*binary_op1*\
İç ürünün Genelleştirme içindeki öğe odaklı ürünlere uygulanan toplamın iç ürün işleminin yerine geçen ikili işlem.

*binary_op2*\
İç ürünün genelleştirilme işleminde çarpma işleminin iç ürün öğe temelinde yerine geçen ikili işlem.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, öğe temelinde ürünlerin toplamını döndürür ve belirtilen başlangıç değerine ekler. Bu nedenle, ı ve *b* *i değer aralıkları*için şunu döndürür:

`val` + (*1 \** *b*1) + (*bir*2 \* *b*2) +... + (*a*n \* *b*n)

*değer* , `val` + (*a*ı \* *b*i) ile yinelemeli olarak değiştiriliyor.

İkinci üye işlevi şunu döndürür:

`val` *binary_op1* (*a*1 *binary_op2* *b*1) *binary_op1* (*bir*2 *binary_op2* *b*2) *binary_op1* ... *binary_op1* (*a*n *binary_op2* *b*n)

*değer* `val` *binary_op1* (*a*i *binary_op2* *b*i) ile yinelemeli olarak değiştiriliyor.

### <a name="remarks"></a>Açıklamalar

İlk değer, Aralık boş olduğunda iyi tanımlanmış bir sonuç olmasını sağlar ve bu durumda *Val* değeri döndürülür. İkili işlemlerin ilişkilendirilebilir veya iletişim olması gerekmez. Aralığın geçerli olması ve karmaşıklığın, aralığın boyutuyla doğrusal olması gerekir. Yineleme sırasında kapanış sağlamak için ikili işlecin dönüş türü **türüne** dönüştürülebilir olmalıdır.

### <a name="example"></a>Örnek

```cpp
// numeric_inner_prod.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main()
{
   using namespace std;

   vector <int> v1, v2(7), v3(7);
   vector <int>::iterator iter1, iter2, iter3;

   int i;
   for (i = 1; i <= 7; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   list <int> l1, l2(7);
   list <int>::iterator lIter1, lIter2;

   int t;
   for (t = 1; t <= 7; t++)
   {
      l1.push_back(t);
   }

   cout << "The original list l1 is:\n ( " ;
   for (lIter1 = l1.begin(); lIter1 != l1.end(); lIter1++)
      cout << *lIter1 << " ";
   cout << ")." << endl;

   // The first member function for the inner product
   int inprod;
   inprod = inner_product(v1.begin(), v1.end(), l1.begin(), 0);

   cout << "The inner_product of the vector v1 and the list l1 is: "
        << inprod << "." << endl;

   // Constructing a vector of partial inner_products between v1 & l1
   int j = 0, parinprod;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++) {
      parinprod = inner_product(v1.begin(), iter1 + 1, l1.begin(), 0);
      v2[j] = parinprod;
      j++;
   }

   cout << "Vector of partial inner_products between v1 & l1 is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function used to compute
   // the product of the element-wise sums
   int inprod2;
   inprod2 = inner_product (v1.begin(), v1.end(),
      l1.begin(), 1, multiplies<int>(), plus<int>());

   cout << "The sum of the element-wise products of v1 and l1 is: "
        << inprod2 << "." << endl;

   // Constructing a vector of partial sums of element-wise products
   int k = 0, parinprod2;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      parinprod2 =
         inner_product(v1.begin(), iter1 + 1, l1.begin(), 1,
         multiplies<int>(), plus<int>());
      v3[k] = parinprod2;
      k++;
   }

   cout << "Vector of partial sums of element-wise products is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl << endl;
}
```

## <a name="iota"></a>harfi

İlk öğeden başlayarak ve Aralık `[first,  last)`öğelerin her birinde bu değerin (` value++`) birbirini izleyen artışlarıyla doldurarak başlangıç değerini depolar.

```cpp
template <class ForwardIterator, class Type>
void iota(ForwardIterator first, ForwardIterator last, Type value);
```

### <a name="parameters"></a>Parametreler

*ilk* \
Doldurulacak aralıktaki ilk öğeyi ele alan bir giriş Yineleyici.

*son* \
Doldurulacak aralıktaki son öğeyi ele alan bir giriş Yineleyici.

*değer* \
İlk öğede depolanacak başlangıç değeri ve sonraki öğeler için yoğun olarak artış.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir tamsayılar [listesini](../standard-library/list.md) doldurarak ve sonra [random_shuffle](../standard-library/algorithm-functions.md#random_shuffle) işlevinin kullanılabilmesi için bir `list` [vektör](../standard-library/vector.md) doldurarak `iota` işlevi için bazı kullanımları gösterir.

```cpp
// compile by using: cl /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <numeric>
#include <list>
#include <vector>
#include <iostream>

using namespace std;

int main(void)
{
    list <int> intList(10);
    vector <list<int>::iterator> intVec(intList.size());

    // Fill the list
    iota(intList.begin(), intList.end(), 0);

    // Fill the vector with the list so we can shuffle it
    iota(intVec.begin(), intVec.end(), intList.begin());

    random_shuffle(intVec.begin(), intVec.end());

    // Output results
    cout << "Contents of the integer list: " << endl;
    for (auto i: intList) {
        cout << i << ' ';
    }
    cout << endl << endl;

    cout << "Contents of the integer list, shuffled by using a vector: " << endl;
    for (auto i: intVec) {
        cout << *i << ' ';
    }
    cout << endl;
}
```

## <a name="lcm"></a>LCM

```cpp
template <class M, class N>
constexpr common_type_t<M,N> lcm(M m, N n);
```

## <a name="partial_sum"></a>partial_sum

İlk öğeden *i*. öğe aracılığıyla bir giriş aralığındaki bir dizi toplamı hesaplar ve bir hedef aralığın *i*. öğesinde her bir toplamın sonucunu depolar ya da toplam işlemin olduğu genelleştirilmiş bir yordamın sonucunu hesaplar belirtilen başka bir ikili işlem tarafından değiştirilmiş.

```cpp
template <class InputIterator, class OutIt>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIt, class Fn2>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Parametreler

*ilk* \
Belirtilen bir ikili işleme göre kısmen toplanan veya birleştirilen aralıktaki ilk öğeyi ele alan giriş yineleyici.

*son* \
Yineleyen birikime dahil son öğenin ötesinde konumlanmış belirtilen bir ikili işleme göre kısmen toplanan veya birleştirilen aralıktaki son öğeyi ele alan giriş yineleyici.

*sonuç*\
Kısmı toplamların dizilerinin veya belirtilen işlemin sonuçlarının depolanacağı hedef aralıktaki ilk öğeyi ele alan çıkış yineleyici.

*binary_op*\
Kısmi toplam yordamındaki toplama işleminin yerini alan genelleştirilmiş işlemde uygulanacak olan ikili işlem.

### <a name="return-value"></a>Dönüş Değeri

Hedef aralığın sonunu ele alarak çıkış yineleyici: `result` + (`last` - `first`),

### <a name="remarks"></a>Açıklamalar

Çıkış Yineleyici *sonucunun* , *ilk*olarak giriş yineleyicisi ile aynı Yineleyici olmasına izin verilir, böylece kısmi toplamların yerine hesaplanabilir.

1, *2, 3, bir*giriş *aralığında bir*değerdizisi için, ilk şablon işlevi, *ı*. öğesinin ((((*a*1 + *a*2) + *a*3) tarafından verildiği hedef aralıktaki ardışık kısmi toplamları depolari).

1 *, 2,* 3 *, bir giriş aralığında bir değer dizisi*için, ikinci şablon işlevi, "a `binary_op` *(((1 `binary_op`* *a*2)3) *bir*ı).

İşlem sırası geçerli olduğundan, *Binary_Op* ikili işleminin ilişkilendirilebilir veya iletişim olması gerekmez.

### <a name="example"></a>Örnek

```cpp
// numeric_partial_sum.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the partial sums of
   // elements in a list output to a vector
   VIterend = partial_sum ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "The output vector containing the partial sums is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the partial product of the elements in a list
   VIterend2 = partial_sum ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the partial products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of partial sums in place
   LIterend = partial_sum ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "The in place output partial_sum list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="reduce"></a>azal

```cpp
template<class InputIterator>
typename iterator_traits<InputIterator>::value_type
reduce(InputIterator first, InputIterator last);
template<class InputIterator, class T>
T reduce(InputIterator first, InputIterator last, T init);
template<class InputIterator, class T, class BinaryOperation>
T reduce(InputIterator first, InputIterator last, T init,
BinaryOperation binary_op);
template<class ExecutionPolicy, class ForwardIterator>
typename iterator_traits<ForwardIterator>::value_type
reduce(ExecutionPolicy&& exec, 
ForwardIterator first, ForwardIterator last);
template<class ExecutionPolicy, class ForwardIterator, class T>
T reduce(ExecutionPolicy&& exec, 
ForwardIterator first, ForwardIterator last, T init);
template<class ExecutionPolicy, class ForwardIterator, class T, class BinaryOperation>
T reduce(ExecutionPolicy&& exec, 
ForwardIterator first, ForwardIterator last, T init,
BinaryOperation binary_op);
```

## <a name="transform_exclusive_scan"></a>transform_exclusive_scan

```cpp
template<class InputIterator, class OutputIterator, class T,
class BinaryOperation, class UnaryOperation>
OutputIterator transform_exclusive_scan(InputIterator first, InputIterator last,
OutputIterator result,
T init,
BinaryOperation binary_op,
UnaryOperation unary_op);
template<class ExecutionPolicy,
class ForwardIterator1, class ForwardIterator2, class T,
class BinaryOperation, class UnaryOperation>
ForwardIterator2 transform_exclusive_scan(ExecutionPolicy&& exec, 
ForwardIterator1 first, ForwardIterator1 last,
ForwardIterator2 result,
T init,
BinaryOperation binary_op,
UnaryOperation unary_op);
```

## <a name="transform_inclusive_scan"></a>transform_inclusive_scan

```cpp
template<class InputIterator, class OutputIterator,
class BinaryOperation, class UnaryOperation>
OutputIterator transform_inclusive_scan(InputIterator first, InputIterator last,
OutputIterator result,
BinaryOperation binary_op,
UnaryOperation unary_op);
template<class InputIterator, class OutputIterator,
class BinaryOperation, class UnaryOperation, class T>
OutputIterator transform_inclusive_scan(InputIterator first, InputIterator last,
OutputIterator result,
BinaryOperation binary_op,
UnaryOperation unary_op,
T init);
template<class ExecutionPolicy,
class ForwardIterator1, class ForwardIterator2,
class BinaryOperation, class UnaryOperation>
ForwardIterator2 transform_inclusive_scan(ExecutionPolicy&& exec, 
ForwardIterator1 first, ForwardIterator1 last,
ForwardIterator2 result,
BinaryOperation binary_op,
UnaryOperation unary_op);
template<class ExecutionPolicy,
class ForwardIterator1, class ForwardIterator2,
class BinaryOperation, class UnaryOperation, class T>
ForwardIterator2 transform_inclusive_scan(ExecutionPolicy&& exec, 
ForwardIterator1 first, ForwardIterator1 last,
ForwardIterator2 result,
BinaryOperation binary_op,
UnaryOperation unary_op,
T init);
```

## <a name="transform_reduce"></a>transform_reduce

```cpp
template<class InputIterator1, class InputIterator2, class T>
T transform_reduce(InputIterator1 first1, InputIterator1 last1,
InputIterator2 first2,
T init);
template<class InputIterator1, class InputIterator2, class T,
class BinaryOperation1, class BinaryOperation2>
T transform_reduce(InputIterator1 first1, InputIterator1 last1,
InputIterator2 first2,
T init,
BinaryOperation1 binary_op1,
BinaryOperation2 binary_op2);
template<class InputIterator, class T,
class BinaryOperation, class UnaryOperation>
T transform_reduce(InputIterator first, InputIterator last,
T init,
BinaryOperation binary_op, UnaryOperation unary_op);
template<class ExecutionPolicy,
class ForwardIterator1, class ForwardIterator2, class T>
T transform_reduce(ExecutionPolicy&& exec, 
ForwardIterator1 first1, ForwardIterator1 last1,
ForwardIterator2 first2,
T init);
template<class ExecutionPolicy,
class ForwardIterator1, class ForwardIterator2, class T,
class BinaryOperation1, class BinaryOperation2>
T transform_reduce(ExecutionPolicy&& exec, 
ForwardIterator1 first1, ForwardIterator1 last1,
ForwardIterator2 first2,
T init,
BinaryOperation1 binary_op1,
BinaryOperation2 binary_op2);
template<class ExecutionPolicy,
class ForwardIterator, class T,
class BinaryOperation, class UnaryOperation>
T transform_reduce(ExecutionPolicy&& exec, 
ForwardIterator first, ForwardIterator last,
T init,
BinaryOperation binary_op, UnaryOperation unary_op);
```
