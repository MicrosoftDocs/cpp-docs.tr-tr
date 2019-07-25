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
ms.openlocfilehash: 68ee602c44a8515e1d41f04a4bd0fbb7edc924b7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452302"
---
# <a name="checkedarrayiterator-class"></a>checked_array_iterator Sınıfı

Sınıfı `checked_array_iterator` , bir diziyi veya işaretçiyi denetlenen bir yineleyici haline dönüştürmenizi sağlar. Bu uyarıları genel olarak susturmak yerine bu sınıfı ham işaretçiler veya diziler için bir sarmalayıcı olarak ( [make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator) işlevini kullanarak), Denetlenmemiş işaretçi uyarılarını denetlemek ve yönetmek için hedeflenmiş bir yol olarak kullanın. Gerekirse, [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md)bu sınıfının denetlenmeyen sürümünü kullanabilirsiniz.

> [!NOTE]
> Bu sınıf, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir. Örneğin, bu sınıfın kullanımını gerektirmeyen kodun nasıl yazılacağını gösteren bir örnek için, aşağıdaki ikinci örneğe bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class _Iterator>
class checked_array_iterator;
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [stdext](../standard-library/stdext-namespace.md) ad alanında tanımlanır.

Denetlenen Yineleyici özelliği hakkında daha fazla bilgi ve örnek kod için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek denetlenen bir dizi yineleyicisinin nasıl tanımlanacağını ve kullanılacağını göstermektedir.

Hedef kopyalanan öğeleri tutmak için yeterince büyük değilse, satırı değiştirdiyseniz duruma göre şöyle olur:

```cpp
copy(a, a + 5, checked_array_iterator<int*>(b, 5));
```

to

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

Standart Kitaplık algoritmaları kullanırken `checked_array_iterator` C++ sınıf ihtiyacını önlemek için, dinamik olarak ayrılan dizi yerine bir `vector` kullanmayı düşünün. Aşağıdaki örnek bunun nasıl yapılacağını göstermektedir.

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
|[checked_array_iterator](#checked_array_iterator)|Temel bir yineleyiciden `checked_array_iterator` varsayılan `checked_array_iterator` veya bir oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Aynı kapsayıcı içindeki öğelere başvuran iki `checked_array_iterator`s arasındaki farkı sağlayan bir tür.|
|[çağrısı](#pointer)|Tarafından bahsedilen bir öğeye işaretçi sağlayan bir tür `checked_array_iterator`.|
|[Başvuru](#reference)|Tarafından bahsedilen bir öğeye başvuru sağlayan bir tür `checked_array_iterator`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[base](#base)|Temel yineleyiciyi öğesinden `checked_array_iterator`kurtarır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator==](#op_eq_eq)|Eşitlik için `checked_array_iterator`iki s 'yi sınar.|
|[operator!=](#op_neq)|Eşitsizlik için `checked_array_iterator`iki s testi yapın.|
|[işleç <](#op_lt)|İşlecin sol tarafındaki `checked_array_iterator` ' ın sağ taraftaki değerinden küçük `checked_array_iterator` olup olmadığını sınar.|
|[işleç >](#op_gt)|İşlecin sol tarafındaki `checked_array_iterator` ' ın sağ taraftan daha büyük `checked_array_iterator` olup olmadığını sınar.|
|[işleç < =](#op_lt_eq)|İşlecin sol tarafındaki `checked_array_iterator` işlecinin sağ tarafta küçük veya ona eşit `checked_array_iterator` olup olmadığını test eder.|
|[operator>=](#op_gt_eq)|İşlecin sol tarafındaki `checked_array_iterator` işlecinin sağ taraftan daha büyük veya ona eşit `checked_array_iterator` olup olmadığını sınar.|
|[işlecinde](#op_star)|`checked_array_iterator` Adreslerin bulunduğu öğeyi döndürür.|
|[operator->](#op_arrow)|Tarafından belirtilen öğeye bir işaretçi döndürür `checked_array_iterator`.|
|[işleç + +](#op_add_add)|`checked_array_iterator` Öğesini bir sonraki öğeye artırır.|
|[işleç--](#operator--)|Önceki öğeye kadar azaltır. `checked_array_iterator`|
|[operator+=](#op_add_eq)|Öğesine belirtilen bir sapmayı ekler `checked_array_iterator`.|
|[işleç +](#op_add)|Bir yineleyici için bir konum ekler ve yeni bir konum `checked_array_iterator` konumundaki eklenen öğeyi yeni adreslemeyi döndürür.|
|[işleç-=](#operator-_eq)|Belirtilen bir `checked_array_iterator`sapmayı azaltır.|
|[işlecinde](#operator-)|Bir yineleyiciden bir sapmayı azaltır ve yeni bir konum `checked_array_iterator` konumundaki ekli öğenin yeni adreslemesini döndürür.|
|[işlecinde&#91;&#93;](#op_at)|Belirtilen sayıda konum tarafından bahsedilen öğeden bir `checked_array_iterator` öğe kaydırmasına yönelik bir başvuru döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** stdext

## <a name="base"></a>checked_array_iterator:: Base

Temel yineleyiciyi öğesinden `checked_array_iterator`kurtarır.

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

## <a name="checked_array_iterator"></a>checked_array_iterator::checked_array_iterator

Temel bir yineleyiciden `checked_array _iterator` varsayılan `checked_array_iterator` veya bir oluşturur.

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

## <a name="difference_type"></a>checked_array_iterator::d ifference_type

Aynı kapsayıcı içindeki öğelere başvuran iki `checked_array_iterator`s arasındaki farkı sağlayan bir tür.

```cpp
typedef typename iterator_traits<_Iterator>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`checked_array_iterator` Fark türü yineleyici fark türüyle aynıdır.

Kod örneği için bkz. [checked_array_iterator:: operator []](#op_at) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="op_eq_eq"></a>checked_array_iterator:: operator = =

Eşitlik için `checked_array_iterator`iki s 'yi sınar.

```cpp
bool operator==(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator` Eşitlik için denetlenecek.

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

## <a name="op_neq"></a>checked_array_iterator:: operator! =

Eşitsizlik için `checked_array_iterator`iki s testi yapın.

```cpp
bool operator!=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator` Eşitsizlik için denetlenecek.

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

## <a name="op_lt"></a>checked_array_iterator:: işleci&lt;

İşlecin sol tarafındaki `checked_array_iterator` ' ın sağ taraftaki değerinden küçük `checked_array_iterator` olup olmadığını sınar.

```cpp
bool operator<(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator` Eşitsizlik için denetlenecek.

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

## <a name="op_gt"></a>checked_array_iterator:: işleci&gt;

İşlecin sol tarafındaki `checked_array_iterator` ' ın sağ taraftan daha büyük `checked_array_iterator` olup olmadığını sınar.

```cpp
bool operator>(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator` Karşılaştırılacak.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [checked_array_iterator:: operator&lt; ](#op_lt) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="op_lt_eq"></a>checked_array_iterator:: işleci&lt;=

İşlecin sol tarafındaki `checked_array_iterator` işlecinin sağ tarafta küçük veya ona eşit `checked_array_iterator` olup olmadığını test eder.

```cpp
bool operator<=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator` Karşılaştırılacak.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [checked_array_iterator:: operator&gt; = ](#op_gt_eq) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="op_gt_eq"></a>checked_array_iterator:: işleci&gt;=

İşlecin sol tarafındaki `checked_array_iterator` işlecinin sağ taraftan daha büyük veya ona eşit `checked_array_iterator` olup olmadığını sınar.

```cpp
bool operator>=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
`checked_array_iterator` Karşılaştırılacak.

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

## <a name="op_star"></a>checked_array_iterator:: operator *

`checked_array_iterator` Adreslerin bulunduğu öğeyi döndürür.

```cpp
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen öğesinin değeri `checked_array_iterator`.

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

## <a name="op_arrow"></a>checked_array_iterator:: operator-&gt;

Tarafından belirtilen öğeye bir işaretçi döndürür `checked_array_iterator`.

```cpp
pointer operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından bahsedilen öğe için bir işaretçi `checked_array_iterator`.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [checked_array_iterator::p oınter](#pointer) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="op_add_add"></a>checked_array_iterator:: operator + +

`checked_array_iterator` Öğesini bir sonraki öğeye artırır.

```cpp
checked_array_iterator& operator++();

checked_array_iterator<_Iterator> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, ön arttırılan `checked_array_iterator` ve ikincisi, postıncrement işleci, artın `checked_array_iterator`bir kopyasını döndürür.

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

## <a name="operator--"></a>checked_array_iterator:: operator--

Önceki öğeye kadar azaltır. `checked_array_iterator`

```cpp
checked_array_iterator<_Iterator>& operator--();

checked_array_iterator<_Iterator> operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, predecremented `checked_array_iterator` döndürür ve ikinci olarak, postazaltma işleci, `checked_array_iterator`azaltma işlevinin bir kopyasını döndürür.

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

## <a name="op_add_eq"></a>checked_array_iterator:: operator + =

Öğesine belirtilen bir sapmayı ekler `checked_array_iterator`.

```cpp
checked_array_iterator<_Iterator>& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
Yineleyicinin artılacağı fark.

### <a name="return-value"></a>Dönüş Değeri

Tarafından bahsedilen öğesine bir başvuru `checked_array_iterator`.

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

## <a name="op_add"></a>checked_array_iterator:: operator +

Bir yineleyici için bir konum ekler ve yeni bir konum `checked_array_iterator` konumundaki eklenen öğeyi yeni adreslemeyi döndürür.

```cpp
checked_array_iterator<_Iterator> operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
Öğesine eklenecek olan Aralık `checked_array_iterator`.

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

## <a name="operator-_eq"></a>checked_array_iterator:: operator-=

Belirtilen bir `checked_array_iterator`sapmayı azaltır.

```cpp
checked_array_iterator<_Iterator>& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
Yineleyicinin artılacağı fark.

### <a name="return-value"></a>Dönüş Değeri

Tarafından bahsedilen öğesine bir başvuru `checked_array_iterator`.

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

## <a name="operator-"></a>checked_array_iterator:: operator-

Bir yineleyiciden bir sapmayı azaltır ve yeni bir konum `checked_array_iterator` konumundaki ekli öğenin yeni adreslemesini döndürür.

```cpp
checked_array_iterator<_Iterator> operator-(difference_type _Off) const;

difference_type operator-(const checked_array_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
Öğesinden azaltılanacak olan `checked_array_iterator`Aralık.

### <a name="return-value"></a>Dönüş Değeri

Bir `checked_array_iterator` adres boşluğu öğesi.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="op_at"></a>checked_array_iterator:: operator []

Belirtilen sayıda konum tarafından bahsedilen öğeden bir `checked_array_iterator` öğe kaydırmasına yönelik bir başvuru döndürür.

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
`checked_array_iterator` Adresten gelen fark.

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

## <a name="pointer"></a>checked_array_iterator::p oınter

Tarafından bahsedilen bir öğeye işaretçi sağlayan bir tür `checked_array_iterator`.

```cpp
typedef typename iterator_traits<_Iterator>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [checked_array_iterator:: operator *](#op_star) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="reference"></a>checked_array_iterator:: Reference

Tarafından bahsedilen bir öğeye başvuru sağlayan bir tür `checked_array_iterator`.

```cpp
typedef typename iterator_traits<_Iterator>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [checked_array_iterator:: operator []](#op_at) .

Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
