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
ms.openlocfilehash: 467a94212d7b1e9d28a3229660b8a8619993b201
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684947"
---
# <a name="checked_array_iterator-class"></a>checked_array_iterator Sınıfı

`checked_array_iterator`Sınıfı, bir diziyi veya işaretçiyi denetlenen bir yineleyici haline dönüştürmenizi sağlar. Bu uyarıları genel olarak susturmak yerine bu sınıfı ham işaretçiler veya diziler için bir sarmalayıcı ( [make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator) işlevini kullanarak), Denetlenmemiş işaretçi uyarılarını denetlemek ve yönetmek için hedeflenmiş bir yol olarak kullanın. Gerekirse, bu sınıfın Denetlenmemiş sürümünü kullanabilirsiniz [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md).

> [!NOTE]
> Bu sınıf, C++ standart kitaplığı 'nın bir Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir. Örneğin, bu sınıfın kullanımını gerektirmeyen kodun nasıl yazılacağını gösteren bir örnek için, aşağıdaki ikinci örneğe bakın.

## <a name="syntax"></a>Syntax

```cpp
template <class _Iterator>
class checked_array_iterator;
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [stdext](../standard-library/stdext-namespace.md) ad alanında tanımlanır.

Denetlenen Yineleyici özelliği hakkında daha fazla bilgi ve örnek kod için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek denetlenen bir dizi yineleyicisinin nasıl tanımlanacağını ve kullanılacağını göstermektedir.

Hedef kopyalanan öğeleri tutmak için yeterince büyük değilse, satırı değiştirdiyseniz duruma göre şöyle olur:

```cpp
copy(a, a + 5, checked_array_iterator<int*>(b, 5));
```

şöyle değiştirin:

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

`checked_array_iterator`C++ Standart Kitaplığı algoritmaları kullanırken sınıfa yönelik gereksiniminizi önlemek için, `vector` dinamik olarak ayrılan dizi yerine bir kullanmayı düşünün. Aşağıdaki örnek bunun nasıl yapılacağını göstermektedir.

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

|Oluşturucu|Description|
|-|-|
|[checked_array_iterator](#checked_array_iterator)|`checked_array_iterator`Temel bir yineleyiciden varsayılan veya bir oluşturur `checked_array_iterator` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Description|
|-|-|
|[difference_type](#difference_type)|`checked_array_iterator`Aynı kapsayıcı içindeki öğelere başvuran iki s arasındaki farkı sağlayan bir tür.|
|[pointer](#pointer)|Tarafından bahsedilen bir öğeye işaretçi sağlayan bir tür `checked_array_iterator` .|
|[başvurunun](#reference)|Tarafından bahsedilen bir öğeye başvuru sağlayan bir tür `checked_array_iterator` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Description|
|-|-|
|[base](#base)|Temel yineleyiciyi öğesinden kurtarır `checked_array_iterator` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç = =](#op_eq_eq)|`checked_array_iterator`Eşitlik için iki s 'yi sınar.|
|[işleç! =](#op_neq)|`checked_array_iterator`Eşitsizlik için iki s testi yapın.|
|[işleç<](#op_lt)|`checked_array_iterator`İşlecin sol tarafındaki ' ın sağ taraftaki değerinden küçük olup olmadığını sınar `checked_array_iterator` .|
|[işleç>](#op_gt)|`checked_array_iterator`İşlecin sol tarafındaki ' ın sağ taraftan daha büyük olup olmadığını sınar `checked_array_iterator` .|
|[işleç<=](#op_lt_eq)|`checked_array_iterator`İşlecin sol tarafındaki işlecinin sağ tarafta küçük veya ona eşit olup olmadığını test eder `checked_array_iterator` .|
|[işleç>=](#op_gt_eq)|`checked_array_iterator`İşlecin sol tarafındaki işlecinin sağ taraftan daha büyük veya ona eşit olup olmadığını sınar `checked_array_iterator` .|
|[işlecinde](#op_star)|Adreslerin bulunduğu öğeyi döndürür `checked_array_iterator` .|
|[operator->](#op_arrow)|Tarafından belirtilen öğeye bir işaretçi döndürür `checked_array_iterator` .|
|[işleç + +](#op_add_add)|Öğesini bir `checked_array_iterator` sonraki öğeye artırır.|
|[işleç--](#operator--)|`checked_array_iterator`Önceki öğeye kadar azaltır.|
|[işleç + =](#op_add_eq)|Öğesine belirtilen bir sapmayı ekler `checked_array_iterator` .|
|[işleç +](#op_add)|Bir yineleyici için bir konum ekler ve yeni bir konum konumundaki `checked_array_iterator` Eklenen öğeyi yeni adreslemeyi döndürür.|
|[işleç-=](#operator-_eq)|Belirtilen bir sapmayı azaltır `checked_array_iterator` .|
|[işlecinde](#operator-)|Bir yineleyiciden bir sapmayı azaltır ve yeni bir `checked_array_iterator` konum konumundaki ekli öğenin yeni adreslemesini döndürür.|
|[işleç&#91;&#93;](#op_at)|Belirtilen sayıda konum tarafından bahsedilen öğeden bir öğe kaydırmasına yönelik bir başvuru döndürür `checked_array_iterator` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** stdext

## <a name="checked_array_iteratorbase"></a><a name="base"></a> checked_array_iterator:: Base

Temel yineleyiciyi öğesinden kurtarır `checked_array_iterator` .

```cpp
_Iterator base() const;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratorchecked_array_iterator"></a><a name="checked_array_iterator"></a> checked_array_iterator:: checked_array_iterator

`checked_array_iterator`Temel bir yineleyiciden varsayılan veya bir oluşturur `checked_array _iterator` .

```cpp
checked_array_iterator();

checked_array_iterator(
    ITerator ptr,
    size_t size,
    size_t index = 0);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Dizi işaretçisi.

*boyutla*\
Dizinin boyutu.

*indeks*\
Seçim Yineleyiciyi başlatmak için dizideki bir öğe.  Varsayılan olarak, Yineleyici dizideki ilk öğe için başlatılır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratordifference_type"></a><a name="difference_type"></a> checked_array_iterator::d ifference_type

`checked_array_iterator`Aynı kapsayıcı içindeki öğelere başvuran iki s arasındaki farkı sağlayan bir tür.

```cpp
typedef typename iterator_traits<_Iterator>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`checked_array_iterator`Fark türü yineleyici fark türüyle aynıdır.

Kod örneği için bkz. [checked_array_iterator:: operator []](#op_at) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratoroperator"></a><a name="op_eq_eq"></a> checked_array_iterator:: operator = =

`checked_array_iterator`Eşitlik için iki s 'yi sınar.

```cpp
bool operator==(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator`Eşitlik için denetlenecek.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratoroperator"></a><a name="op_neq"></a> checked_array_iterator:: operator! =

`checked_array_iterator`Eşitsizlik için iki s testi yapın.

```cpp
bool operator!=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator`Eşitsizlik için denetlenecek.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratoroperatorlt"></a><a name="op_lt"></a> checked_array_iterator:: işleci&lt;

`checked_array_iterator`İşlecin sol tarafındaki ' ın sağ taraftaki değerinden küçük olup olmadığını sınar `checked_array_iterator` .

```cpp
bool operator<(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator`Eşitsizlik için denetlenecek.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratoroperatorgt"></a><a name="op_gt"></a> checked_array_iterator:: işleci&gt;

`checked_array_iterator`İşlecin sol tarafındaki ' ın sağ taraftan daha büyük olup olmadığını sınar `checked_array_iterator` .

```cpp
bool operator>(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator`Karşılaştırılacak.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [checked_array_iterator:: işleci &lt; ](#op_lt) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratoroperatorlt"></a><a name="op_lt_eq"></a> checked_array_iterator:: işleci&lt;=

`checked_array_iterator`İşlecin sol tarafındaki işlecinin sağ tarafta küçük veya ona eşit olup olmadığını test eder `checked_array_iterator` .

```cpp
bool operator<=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator`Karşılaştırılacak.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [checked_array_iterator:: işleci &gt; = ](#op_gt_eq) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratoroperatorgt"></a><a name="op_gt_eq"></a> checked_array_iterator:: işleci&gt;=

`checked_array_iterator`İşlecin sol tarafındaki işlecinin sağ taraftan daha büyük veya ona eşit olup olmadığını sınar `checked_array_iterator` .

```cpp
bool operator>=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator`Karşılaştırılacak.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratoroperator"></a><a name="op_star"></a> checked_array_iterator:: operator *

Adreslerin bulunduğu öğeyi döndürür `checked_array_iterator` .

```cpp
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen öğesinin değeri `checked_array_iterator` .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratoroperator-gt"></a><a name="op_arrow"></a> checked_array_iterator:: operator-&gt;

Tarafından belirtilen öğeye bir işaretçi döndürür `checked_array_iterator` .

```cpp
pointer operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından bahsedilen öğe için bir işaretçi `checked_array_iterator` .

### <a name="remarks"></a>Açıklamalar

Bkz. checked_array_iterator: bir kod örneği için [:p oınter](#pointer) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratoroperator"></a><a name="op_add_add"></a> checked_array_iterator:: operator + +

Öğesini bir `checked_array_iterator` sonraki öğeye artırır.

```cpp
checked_array_iterator& operator++();

checked_array_iterator<_Iterator> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, ön arttırılan `checked_array_iterator` ve ikincisi, postıncrement işleci, artın bir kopyasını döndürür `checked_array_iterator` .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratoroperator--"></a><a name="operator--"></a> checked_array_iterator:: operator--

`checked_array_iterator`Önceki öğeye kadar azaltır.

```cpp
checked_array_iterator<_Iterator>& operator--();

checked_array_iterator<_Iterator> operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, predecremented döndürür `checked_array_iterator` ve ikinci olarak, postazaltma işleci, azaltma işlevinin bir kopyasını döndürür `checked_array_iterator` .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratoroperator"></a><a name="op_add_eq"></a> checked_array_iterator:: operator + =

Öğesine belirtilen bir sapmayı ekler `checked_array_iterator` .

```cpp
checked_array_iterator<_Iterator>& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_Off*\
Yineleyicinin artılacağı fark.

### <a name="return-value"></a>Dönüş Değeri

Tarafından bahsedilen öğesine bir başvuru `checked_array_iterator` .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratoroperator"></a><a name="op_add"></a> checked_array_iterator:: operator +

Bir yineleyici için bir konum ekler ve yeni bir konum konumundaki `checked_array_iterator` Eklenen öğeyi yeni adreslemeyi döndürür.

```cpp
checked_array_iterator<_Iterator> operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

*_Off*\
Öğesine eklenecek olan Aralık `checked_array_iterator` .

### <a name="return-value"></a>Dönüş Değeri

Bir `checked_array_iterator` adres boşluğu öğesi.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratoroperator-"></a><a name="operator-_eq"></a> checked_array_iterator:: operator-=

Belirtilen bir sapmayı azaltır `checked_array_iterator` .

```cpp
checked_array_iterator<_Iterator>& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_Off*\
Yineleyicinin artılacağı fark.

### <a name="return-value"></a>Dönüş Değeri

Tarafından bahsedilen öğesine bir başvuru `checked_array_iterator` .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratoroperator-"></a><a name="operator-"></a> checked_array_iterator:: operator-

Bir yineleyiciden bir sapmayı azaltır ve yeni bir `checked_array_iterator` konum konumundaki ekli öğenin yeni adreslemesini döndürür.

```cpp
checked_array_iterator<_Iterator> operator-(difference_type _Off) const;

difference_type operator-(const checked_array_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*_Off*\
Öğesinden azaltılanacak olan Aralık `checked_array_iterator` .

### <a name="return-value"></a>Dönüş Değeri

Bir `checked_array_iterator` adres boşluğu öğesi.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratoroperator"></a><a name="op_at"></a> checked_array_iterator:: operator []

Belirtilen sayıda konum tarafından bahsedilen öğeden bir öğe kaydırmasına yönelik bir başvuru döndürür `checked_array_iterator` .

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

*_Off*\
Adresten gelen fark `checked_array_iterator` .

### <a name="return-value"></a>Dönüş Değeri

Öğe kaydırmasına başvuru.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="checked_array_iteratorpointer"></a><a name="pointer"></a> checked_array_iterator::p oınter

Tarafından bahsedilen bir öğeye işaretçi sağlayan bir tür `checked_array_iterator` .

```cpp
typedef typename iterator_traits<_Iterator>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [checked_array_iterator:: operator *](#op_star) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratorreference"></a><a name="reference"></a> checked_array_iterator:: Reference

Tarafından bahsedilen bir öğeye başvuru sağlayan bir tür `checked_array_iterator` .

```cpp
typedef typename iterator_traits<_Iterator>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [checked_array_iterator:: operator []](#op_at) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
