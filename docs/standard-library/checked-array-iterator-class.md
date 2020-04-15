---
title: checked_array_iterator Sınıfı
ms.date: 03/27/2019
f1_keywords:
- iterator/checked_array_iterator
- iterator/stdext::checked_array_iterator::difference_type
- iterator/stdext::checked_array_iterator::pointer
- iterator/stdext::checked_array_iterator::reference
- iterator/stdext::checked_array_iterator::base
helpviewer_keywords:
- stdext::checked_array_iterator [C++], difference_type
- stdext::checked_array_iterator [C++], pointer
- stdext::checked_array_iterator [C++], reference
- stdext::checked_array_iterator [C++], base
ms.assetid: 7f07185e-d588-4ae3-9c4f-84ec4aa25a28
ms.openlocfilehash: f177a45e700ab15852cd9c6d947873d247cf3828
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363870"
---
# <a name="checked_array_iterator-class"></a>checked_array_iterator Sınıfı

Sınıf, `checked_array_iterator` bir diziyi veya işaretçiyi denetlenmiş bir yineleyiciye dönüştürmenize olanak tanır. Bu sınıfı, ham işaretçiler veya diziler için bir sarmalayıcı [(make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator) işlevini kullanarak) olarak denetim sağlamak ve bu uyarıları genel olarak susturmak yerine denetlenmemiş işaretçi uyarılarını yönetmek için hedeflenmiş bir yol olarak kullanın. Gerekirse, bu sınıfın işaretlenmemiş sürümünü kullanabilirsiniz, [unchecked_array_iterator.](../standard-library/unchecked-array-iterator-class.md)

> [!NOTE]
> Bu sınıf, C++ Standart Kitaplığı'nın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir. Örneğin, bu sınıfın kullanımını gerektirmeyen kodun nasıl yazılacağını gösteren bir örnek için, aşağıdaki ikinci örneğe bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class _Iterator>
class checked_array_iterator;
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf [stdext](../standard-library/stdext-namespace.md) ad alanında tanımlanır.

Denetlenen yineleyici özelliği hakkında daha fazla bilgi ve örnek kodu için [bkz.](../standard-library/checked-iterators.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek denetlenen bir dizi yineleyicisinin nasıl tanımlanacağını ve kullanılacağını göstermektedir.

Hedef kopyalanan öğeleri tutmak için yeterince büyük değilse, satırı değiştirdiyseniz duruma göre şöyle olur:

```cpp
copy(a, a + 5, checked_array_iterator<int*>(b, 5));
```

-

```cpp
copy(a, a + 5, checked_array_iterator<int*>(b, 4));
```

Bir çalışma zamanı hatası oluşur.

```cpp
// compile with: /EHsc /W4 /MTd
#include <algorithm>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[]={0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b, 5));

   cout << "(";
   for (int i = 0 ; i < 5 ; i++)
      cout << " " << b[i];
   cout << " )" << endl;

   // constructor example
   checked_array_iterator<int*> checked_out_iter(b, 5);
   copy(a, a + 5, checked_out_iter);

   cout << "(";
   for (int i = 0 ; i < 5 ; i++)
      cout << " " << b[i];
   cout << " )" << endl;
}
/* Output:
( 0 1 2 3 4 )
( 0 1 2 3 4 )
*/
```

## <a name="example"></a>Örnek

C++ Standart Kitaplık algoritmalarını kullanırken `checked_array_iterator` sınıfa ihtiyaç `vector` duyulmasını önlemek için dinamik olarak ayrılmış bir dizi yerine bir dizi kullanmayı düşünün. Aşağıdaki örnek bunun nasıl yapılacağını göstermektedir.

```cpp
// compile with: /EHsc /W4 /MTd

#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    std::vector<int> v(10);
    int *arr = new int[10];
    for (int i = 0; i < 10; ++i)
    {
        v[i] = i;
        arr[i] = i;
    }

    // std::copy(v.begin(), v.end(), arr); will result in
    // warning C4996. To avoid this warning while using int *,
    // use the Microsoft extension checked_array_iterator.
    std::copy(v.begin(), v.end(),
              stdext::checked_array_iterator<int *>(arr, 10));

    // Instead of using stdext::checked_array_iterator and int *,
    // consider using std::vector to encapsulate the array. This will
    // result in no warnings, and the code will be portable.
    std::vector<int> arr2(10);    // Similar to int *arr = new int[10];
    std::copy(v.begin(), v.end(), arr2.begin());

    for (int j = 0; j < arr2.size(); ++j)
    {
        cout << " " << arr2[j];
    }
    cout << endl;

    return 0;
}
/* Output:
0 1 2 3 4 5 6 7 8 9
*/
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Checked_array_iterator](#checked_array_iterator)|Varsayılan `checked_array_iterator` veya altta `checked_array_iterator` yatan bir yineleyiciden bir oluşturma.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Aynı kapsayıcıiçindeki elemanlara `checked_array_iterator`atıfta bulunan iki s arasındaki farkı sağlayan bir tür.|
|[pointer](#pointer)|Bir . tarafından adreslenen bir öğeiçin `checked_array_iterator`işaretçi sağlayan bir tür|
|[Başvuru](#reference)|Bir . tarafından adreslenen bir öğeye `checked_array_iterator`başvuru sağlayan bir tür|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[base](#base)|Altta yatan yineleyiciyi kurtarır. `checked_array_iterator`|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç==](#op_eq_eq)|Eşitlik `checked_array_iterator`için iki s test eder.|
|[işleç!=](#op_neq)|Eşitsizlik `checked_array_iterator`için iki s test eder.|
|[operatör<](#op_lt)|Operatörün `checked_array_iterator` sol tarafındakinin sağ taraftakinden `checked_array_iterator` daha az olup olmadığını test edin.|
|[operatör>](#op_gt)|Operatörün `checked_array_iterator` sol tarafındakinin sağ taraftakinden `checked_array_iterator` büyük olup olmadığını test edin.|
|[operatör<=](#op_lt_eq)|Operatörün `checked_array_iterator` sol tarafındaki nin sağ taraftakinden daha `checked_array_iterator` az veya eşit olup olmadığını test edin.|
|[operatör>=](#op_gt_eq)|İşleticinin sol tarafındaki nin sağ taraftakinden `checked_array_iterator` büyük veya eşit olup olmadığını `checked_array_iterator` test edin.|
|[işleç*](#op_star)|Bir `checked_array_iterator` adrese ele alan öğeyi döndürür.|
|[operatör->](#op_arrow)|Bir işaretçiyi ' tarafından `checked_array_iterator`adreslenen öğeye döndürür.|
|[işleç++](#op_add_add)|Bir sonraki `checked_array_iterator` öğeye artışlar.|
|[işleç-](#operator--)|Önceki öğeye `checked_array_iterator` doğru kararnameler.|
|[işleç+=](#op_add_eq)|Bir `checked_array_iterator`' ye belirli bir ofset ekler|
|[işleç+](#op_add)|Bir yineleyiciye bir ofset ekler `checked_array_iterator` ve yeni ofset konumunda eklenen öğeyi ele döndürür.|
|[işleç-=](#operator-_eq)|Belirli bir mahsup' `checked_array_iterator`dan bir mahsup eder.|
|[işleç-](#operator-)|Bir yineleyiciden bir mahsup verir ve eklenen `checked_array_iterator` öğeyi yeni ofset konumunda döndürür.|
|[operatör&#91;&#93;](#op_at)|Belirli sayıda pozisyon tarafından `checked_array_iterator` ele alınan öğeden bir eleman mahsup başvurusu verir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yineleyici>

**Ad alanı:** stdext

## <a name="checked_array_iteratorbase"></a><a name="base"></a>checked_array_iterator::taban

Altta yatan yineleyiciyi kurtarır. `checked_array_iterator`

```cpp
_Iterator base() const;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_base.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main() {
   using namespace std;

   int V1[10];

   for (int i = 0; i < 10 ; i++)
      V1[i] = i;

   int* bpos;

   stdext::checked_array_iterator<int*> rpos(V1, 10);
   rpos++;

   bpos = rpos.base ( );
   cout << "The iterator underlying rpos is bpos & it points to: "
        << *bpos << "." << endl;
}
/* Output:
The iterator underlying rpos is bpos & it points to: 1.
*/
```

## <a name="checked_array_iteratorchecked_array_iterator"></a><a name="checked_array_iterator"></a>checked_array_iterator:checked_array_iterator

Varsayılan `checked_array_iterator` veya altta `checked_array _iterator` yatan bir yineleyiciden bir oluşturma.

```cpp
checked_array_iterator();

checked_array_iterator(
    ITerator ptr,
    size_t size,
    size_t index = 0);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Dizi için bir işaretçi.

*Boyutu*\
Dizinin boyutu.

*Dizin*\
(İsteğe bağlı) Yinelemeyi başlatmaya yönelik dizideki bir öğe.  Varsayılan olarak, yineleyici dizideki ilk öğeye başolarak başlanır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_ctor.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   for (int i = 0 ; i < 5 ; i++)
      cout << b[i] << " ";
   cout << endl;

   checked_array_iterator<int*> checked_output_iterator(b,5);
   copy (a, a + 5, checked_output_iterator);
   for (int i = 0 ; i < 5 ; i++)
      cout << b[i] << " ";
   cout << endl;

   checked_array_iterator<int*> checked_output_iterator2(b,5,3);
   cout << *checked_output_iterator2 << endl;
}
/* Output:
0 1 2 3 4
0 1 2 3 4
3
*/
```

## <a name="checked_array_iteratordifference_type"></a><a name="difference_type"></a>checked_array_iterator::difference_type

Aynı kapsayıcıiçindeki elemanlara `checked_array_iterator`atıfta bulunan iki s arasındaki farkı sağlayan bir tür.

```cpp
typedef typename iterator_traits<_Iterator>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`checked_array_iterator` Fark türü, yineleyici farkı türüyle aynıdır.

Bkz. [checked_array_iterator::operatör[]](#op_at) kod örneği için.

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

## <a name="checked_array_iteratoroperator"></a><a name="op_eq_eq"></a>checked_array_iterator::operator==

Eşitlik `checked_array_iterator`için iki s test eder.

```cpp
bool operator==(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Eşitliği `checked_array_iterator` kontrol etmek için hangi karşı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_opeq.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);
   checked_array_iterator<int*> checked_output_iterator2(b,5);

   if (checked_output_iterator2 == checked_output_iterator)
      cout << "checked_array_iterators are equal" << endl;
   else
      cout << "checked_array_iterators are not equal" << endl;

   copy (a, a + 5, checked_output_iterator);
   checked_output_iterator++;

   if (checked_output_iterator2 == checked_output_iterator)
      cout << "checked_array_iterators are equal" << endl;
   else
      cout << "checked_array_iterators are not equal" << endl;
}
/* Output:
checked_array_iterators are equal
checked_array_iterators are not equal
*/
```

## <a name="checked_array_iteratoroperator"></a><a name="op_neq"></a>checked_array_iterator::operator!=

Eşitsizlik `checked_array_iterator`için iki s test eder.

```cpp
bool operator!=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Eşitsizliği `checked_array_iterator` kontrol etmek için hangi karşı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_opneq.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);
   checked_array_iterator<int*> checked_output_iterator2(b,5);

   if (checked_output_iterator2 != checked_output_iterator)
      cout << "checked_array_iterators are not equal" << endl;
   else
      cout << "checked_array_iterators are equal" << endl;

   copy (a, a + 5, checked_output_iterator);
   checked_output_iterator++;

   if (checked_output_iterator2 != checked_output_iterator)
      cout << "checked_array_iterators are not equal" << endl;
   else
      cout << "checked_array_iterators are equal" << endl;
}
/* Output:
checked_array_iterators are equal
checked_array_iterators are not equal
*/
```

## <a name="checked_array_iteratoroperatorlt"></a><a name="op_lt"></a>checked_array_iterator::operatör&lt;

Operatörün `checked_array_iterator` sol tarafındakinin sağ taraftakinden `checked_array_iterator` daha az olup olmadığını test edin.

```cpp
bool operator<(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Eşitsizliği `checked_array_iterator` kontrol etmek için hangi karşı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_oplt.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);
   checked_array_iterator<int*> checked_output_iterator2(b,5);

   if (checked_output_iterator2 < checked_output_iterator)
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;
   else
      cout << "checked_output_iterator2 is not less than checked_output_iterator" << endl;

   copy (a, a + 5, checked_output_iterator);
   checked_output_iterator++;

   if (checked_output_iterator2 < checked_output_iterator)
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;
   else
      cout << "checked_output_iterator2 is not less than checked_output_iterator" << endl;
}
/* Output:
checked_output_iterator2 is not less than checked_output_iterator
checked_output_iterator2 is less than checked_output_iterator
*/
```

## <a name="checked_array_iteratoroperatorgt"></a><a name="op_gt"></a>checked_array_iterator::operatör&gt;

Operatörün `checked_array_iterator` sol tarafındakinin sağ taraftakinden `checked_array_iterator` büyük olup olmadığını test edin.

```cpp
bool operator>(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Karşıkarşılaştırmak `checked_array_iterator` için.

### <a name="remarks"></a>Açıklamalar

Bkz. [checked_array_iterator::kod&lt; ](#op_lt) örneği için işleç.

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

## <a name="checked_array_iteratoroperatorlt"></a><a name="op_lt_eq"></a>checked_array_iterator::operatör&lt;=

Operatörün `checked_array_iterator` sol tarafındaki nin sağ taraftakinden daha `checked_array_iterator` az veya eşit olup olmadığını test edin.

```cpp
bool operator<=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Karşıkarşılaştırmak `checked_array_iterator` için.

### <a name="remarks"></a>Açıklamalar

Bkz. [checked_array_iterator::kod&gt; ](#op_gt_eq) örneği için işleç.

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

## <a name="checked_array_iteratoroperatorgt"></a><a name="op_gt_eq"></a>checked_array_iterator::operatör&gt;=

İşleticinin sol tarafındaki nin sağ taraftakinden `checked_array_iterator` büyük veya eşit olup olmadığını `checked_array_iterator` test edin.

```cpp
bool operator>=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Karşıkarşılaştırmak `checked_array_iterator` için.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_opgteq.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);
   checked_array_iterator<int*> checked_output_iterator2(b,5);

   if (checked_output_iterator2 >= checked_output_iterator)
      cout << "checked_output_iterator2 is greater than or equal to checked_output_iterator" << endl;
   else
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;

   copy (a, a + 5, checked_output_iterator);
   checked_output_iterator++;

   if (checked_output_iterator2 >= checked_output_iterator)
      cout << "checked_output_iterator2 is greater than or equal to checked_output_iterator" << endl;
   else
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;
}
/* Output:
checked_output_iterator2 is greater than or equal to checked_output_iterator
checked_output_iterator2 is less than checked_output_iterator
*/
```

## <a name="checked_array_iteratoroperator"></a><a name="op_star"></a>checked_array_iterator::operatör*

Bir `checked_array_iterator` adrese ele alan öğeyi döndürür.

```cpp
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından ele verilen öğenin `checked_array_iterator`değeri .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterator_pointer.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <utility>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   pair<int, int> c[1];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   for (int i = 0 ; i < 5 ; i++)
      cout << b[i] << endl;

    c[0].first = 10;
    c[0].second = 20;

   checked_array_iterator<int*> checked_output_iterator(b,5);
   checked_array_iterator<int*>::pointer p = &(*checked_output_iterator);
   checked_array_iterator<pair<int, int>*> chk_c(c, 1);
   checked_array_iterator<pair<int, int>*>::pointer p_c = &(*chk_c);

   cout << "b[0] = " << *p << endl;
   cout << "c[0].first = " << p_c->first << endl;
}
/* Output:
0
1
2
3
4
b[0] = 0
c[0].first = 10
*/
```

## <a name="checked_array_iteratoroperator-gt"></a><a name="op_arrow"></a>checked_array_iterator::operatör-&gt;

Bir işaretçiyi ' tarafından `checked_array_iterator`adreslenen öğeye döndürür.

```cpp
pointer operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

'nin adreslediği `checked_array_iterator`öğenin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bkz. [checked_array_iterator::pkod](#pointer) örneği için ointer.

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

## <a name="checked_array_iteratoroperator"></a><a name="op_add_add"></a>checked_array_iterator::operator++

Bir sonraki `checked_array_iterator` öğeye artışlar.

```cpp
checked_array_iterator& operator++();

checked_array_iterator<_Iterator> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk işleç preincremented `checked_array_iterator` döndürür ve ikinci, postincrement işleci, artışlı `checked_array_iterator`bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_op_plus_plus.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace stdext;
   using namespace std;
   int a[] = {6, 3, 77, 199, 222};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);

   cout << *checked_output_iterator << endl;
   ++checked_output_iterator;
   cout << *checked_output_iterator << endl;
   checked_output_iterator++;
   cout << *checked_output_iterator << endl;
}
/* Output:
6
3
77
*/
```

## <a name="checked_array_iteratoroperator--"></a><a name="operator--"></a>checked_array_iterator::operatör--

Önceki öğeye `checked_array_iterator` doğru kararnameler.

```cpp
checked_array_iterator<_Iterator>& operator--();

checked_array_iterator<_Iterator> operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk işleç predecremented `checked_array_iterator` döndürür ve ikinci, postdecrement işleci, kararnamenin `checked_array_iterator`bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_op_minus_minus.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace stdext;
   using namespace std;
   int a[] = {6, 3, 77, 199, 222};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);

   cout << *checked_output_iterator << endl;
   checked_output_iterator++;
   cout << *checked_output_iterator << endl;
   checked_output_iterator--;
   cout << *checked_output_iterator << endl;
}
/* Output:
6
3
6
*/
```

## <a name="checked_array_iteratoroperator"></a><a name="op_add_eq"></a>checked_array_iterator::operator+=

Bir `checked_array_iterator`' ye belirli bir ofset ekler

```cpp
checked_array_iterator<_Iterator>& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_off*\
Yinelemeyi artımlı ofset.

### <a name="return-value"></a>Dönüş Değeri

`checked_array_iterator`Tarafından ele verilen elemana bir başvuru.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_op_plus_eq.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace stdext;
   using namespace std;
   int a[] = {6, 3, 77, 199, 222};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);

   cout << *checked_output_iterator << endl;
   checked_output_iterator += 3;
   cout << *checked_output_iterator << endl;
}
/* Output:
6
199
*/
```

## <a name="checked_array_iteratoroperator"></a><a name="op_add"></a>checked_array_iterator::operatör+

Bir yineleyiciye bir ofset ekler `checked_array_iterator` ve yeni ofset konumunda eklenen öğeyi ele döndürür.

```cpp
checked_array_iterator<_Iterator> operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

*_off*\
Eklenecek `checked_array_iterator`mahsup.

### <a name="return-value"></a>Dönüş Değeri

Ofset öğesi `checked_array_iterator` ele alma.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_op_plus.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace stdext;
   using namespace std;
   int a[] = {6, 3, 77, 199, 222};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);

   cout << *checked_output_iterator << endl;
   checked_output_iterator = checked_output_iterator + 3;
   cout << *checked_output_iterator << endl;
}
/* Output:
6
199
*/
```

## <a name="checked_array_iteratoroperator-"></a><a name="operator-_eq"></a>checked_array_iterator::operator-=

Belirli bir mahsup' `checked_array_iterator`dan bir mahsup eder.

```cpp
checked_array_iterator<_Iterator>& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_off*\
Yinelemeyi artımlı ofset.

### <a name="return-value"></a>Dönüş Değeri

`checked_array_iterator`Tarafından ele verilen elemana bir başvuru.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_op_minus_eq.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace stdext;
   using namespace std;
   int a[] = {6, 3, 77, 199, 222};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);

   checked_output_iterator += 3;
   cout << *checked_output_iterator << endl;
   checked_output_iterator -= 2;
   cout << *checked_output_iterator << endl;
}
/* Output:
199
3
*/
```

## <a name="checked_array_iteratoroperator-"></a><a name="operator-"></a>checked_array_iterator::operatör-

Bir yineleyiciden bir mahsup verir ve eklenen `checked_array_iterator` öğeyi yeni ofset konumunda döndürür.

```cpp
checked_array_iterator<_Iterator> operator-(difference_type _Off) const;

difference_type operator-(const checked_array_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*_off*\
Mahsup' dan `checked_array_iterator`çıkarılacak.

### <a name="return-value"></a>Dönüş Değeri

Ofset öğesi `checked_array_iterator` ele alma.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

## <a name="checked_array_iteratoroperator"></a><a name="op_at"></a>checked_array_iterator::operatör[]

Belirli sayıda pozisyon tarafından `checked_array_iterator` ele alınan öğeden bir eleman mahsup başvurusu verir.

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

*_off*\
`checked_array_iterator` Adresten mahsup.

### <a name="return-value"></a>Dönüş Değeri

Öğe ofset için başvuru.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// checked_array_iterators_op_diff.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace std;
   int V1[10];

   for (int i = 0; i < 10 ; i++)
      V1[i] = i;

   // Declare a difference type for a parameter
   stdext::checked_array_iterator<int*>::difference_type diff = 2;

   stdext::checked_array_iterator<int*> VChkIter(V1, 10);

   stdext::checked_array_iterator<int*>::reference refrpos = VChkIter [diff];

   cout << refrpos + 1 << endl;
}
/* Output:
3
*/
```

## <a name="checked_array_iteratorpointer"></a><a name="pointer"></a>checked_array_iterator::pointer

Bir . tarafından adreslenen bir öğeiçin `checked_array_iterator`işaretçi sağlayan bir tür

```cpp
typedef typename iterator_traits<_Iterator>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Kod örneği için [checked_array_iterator::operator*](#op_star) adresine bakın.

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

## <a name="checked_array_iteratorreference"></a><a name="reference"></a>checked_array_iterator::başvuru

Bir . tarafından adreslenen bir öğeye `checked_array_iterator`başvuru sağlayan bir tür

```cpp
typedef typename iterator_traits<_Iterator>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Bkz. [checked_array_iterator::operatör[]](#op_at) kod örneği için.

Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
