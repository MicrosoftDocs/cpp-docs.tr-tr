---
title: '&lt;vektör&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vector/std::operator!=
- vector/std::operator&gt;
- vector/std::operator&gt;=
- vector/std::operator&lt;
- vector/std::operator&lt;=
- vector/std::operator==
dev_langs:
- C++
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
helpviewer_keywords:
- std::operator!= (vector)
- std::operator&gt; (vector)
- std::operator&gt;= (vector)
- std::operator&lt; (vector)
- std::operator&lt;= (vector)
- std::operator== (vector)
ms.openlocfilehash: 779fe61bec63f55d7f3b8b3bb7f2e0d084fbab5b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltvectorgt-operators"></a>&lt;vektör&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;=](#op_gt_eq)|
|[işleci&lt;](#op_lt)|[işleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator! =

Testleri işlecinin sol tarafındaki nesnesi sağ tarafında nesnede eşit değil.

```cpp
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **vektör**.

`right` Türünde bir nesne **vektör**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** vektörlerinin eşit; değilse **false** vektörlerinin eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

İki vektör aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// vector_op_ne.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
     v2.push_back( 2 );

   if ( v1 != v2 )
      cout << "Vectors not equal." << endl;
   else
      cout << "Vectors equal." << endl;
}
```

```Output
Vectors not equal.
```

## <a name="op_lt"></a>  işleci&lt;

Nesne işlecinin sol tarafındaki sağ tarafında nesnede küçükse testleri.

```cpp
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **vektör**.

`right` Türünde bir nesne **vektör**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki vektör; işlecinin sağ tarafında vektör küçükse aksi **false**.

### <a name="example"></a>Örnek

```cpp
// vector_op_lt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 < v2 )
      cout << "Vector v1 is less than vector v2." << endl;
   else
      cout << "Vector v1 is not less than vector v2." << endl;
}
```

```Output
Vector v1 is less than vector v2.
```

## <a name="op_lt_eq"></a>  işleci&lt;=

Testleri işlecinin sol tarafındaki küçük veya eşit nesneye sağ tarafında nesnesidir.

```cpp
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **vektör**.

`right` Türünde bir nesne **vektör**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki vektör veya işlecinin sağ tarafında vektör eşit; Aksi takdirde düşükse **false**.

### <a name="example"></a>Örnek

```cpp
// vector_op_le.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 <= v2 )
      cout << "Vector v1 is less than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is greater than vector v2." << endl;
}
```

```Output
Vector v1 is less than or equal to vector v2.
```

## <a name="op_eq_eq"></a>  operator ==

Nesne işlecinin sol tarafındaki sağ tarafında nesnesine eşitse testleri.

```cpp
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **vektör**.

`right` Türünde bir nesne **vektör**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki vektör eşitse işlecinin sağ tarafında vektör aksi **false**.

### <a name="remarks"></a>Açıklamalar

İki vektör aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// vector_op_eq.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v2.push_back( 1 );

   if ( v1 == v2 )
      cout << "Vectors equal." << endl;
   else
      cout << "Vectors not equal." << endl;
}
```

```Output
Vectors equal.
```

## <a name="op_gt"></a>  işleci&gt;

Testleri işlecinin sol tarafındaki nesneyi sağ tarafında nesnede değerinden daha büyük.

```cpp
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **vektör**.

`right` Türünde bir nesne **vektör**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki vektör işlecinin sağ tarafında vektör büyük; tersi durumda ise **false**.

### <a name="example"></a>Örnek

```cpp
// vector_op_gt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

   v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 > v2 )
      cout << "Vector v1 is greater than vector v2." << endl;
   else
      cout << "Vector v1 is not greater than vector v2." << endl;
}
```

```Output
Vector v1 is greater than vector v2.
```

## <a name="op_gt_eq"></a>  işleci&gt;=

Büyük veya ona eşit nesnesine sağ tarafında işlecinin sol tarafındaki nesnedir sağlayıp sağlamadığını test.

```cpp
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **vektör**.

`right` Türünde bir nesne **vektör**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki vektör eşitse büyüktür veya vektör sağ tarafındaki vektör aksi **false**.

### <a name="example"></a>Örnek

```cpp
// vector_op_ge.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

     v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 >= v2 )
      cout << "Vector v1 is greater than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is less than vector v2." << endl;
}
```

```Output
Vector v1 is greater than or equal to vector v2.
```

## <a name="see-also"></a>Ayrıca bkz.

[\<vektör >](../standard-library/vector.md)<br/>
