---
title: '&lt;vektör&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- vector/std::operator!=
- vector/std::operator&gt;
- vector/std::operator&gt;=
- vector/std::operator&lt;
- vector/std::operator&lt;=
- vector/std::operator==
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
helpviewer_keywords:
- std::operator!= (vector)
- std::operator&gt; (vector)
- std::operator&gt;= (vector)
- std::operator&lt; (vector)
- std::operator&lt;= (vector)
- std::operator== (vector)
ms.openlocfilehash: f6717add93c489f536bd0c0b0f82b74bbd915985
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240989"
---
# <a name="ltvectorgt-operators"></a>&lt;vektör&gt; işleçleri

## <a name="op_neq"></a> işleç! =

İşlecin sol tarafındaki nesne işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `vector`.

*sağ*\
Bir nesne türü `vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** vektörler eşit; değilse, **false** vektörler eşitse.

### <a name="remarks"></a>Açıklamalar

Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki vektör eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_lt"></a> İşleci&lt;

İşlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki nesneden küçük olup olmadığını sınar.

```cpp
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `vector`.

*sağ*\
Bir nesne türü `vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki vektör; işlecin sağ tarafındaki vektör altındaysa Aksi takdirde **false**.

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

## <a name="op_lt_eq"></a> İşleci&lt;=

Nesnesinin işlecin sol tarafındaki küçüktür veya eşittir nesnesinin işlecin sağ tarafındaki olup olmadığını sınar.

```cpp
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `vector`.

*sağ*\
Bir nesne türü `vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki vektör daha veya işlecin sağ tarafındaki vektör eşit; Aksi takdirde küçükse **false**.

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

## <a name="op_eq_eq"></a> işleç ==

İşlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.

```cpp
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `vector`.

*sağ*\
Bir nesne türü `vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** vektör işlecinin sol tarafındaki ise, aksi takdirde işlecin sağ tarafındaki vektör eşit **false**.

### <a name="remarks"></a>Açıklamalar

Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki vektör eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_gt"></a> İşleci&gt;

İşlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki nesneden büyük olup olmadığını sınar.

```cpp
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `vector`.

*sağ*\
Bir nesne türü `vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki vektör ise, aksi takdirde vektör işlecin sağ tarafındaki büyük **false**.

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

## <a name="op_gt_eq"></a> İşleci&gt;=

İşlecin sol tarafındaki nesnesinin değerinden büyük veya işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.

```cpp
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `vector`.

*sağ*\
Bir nesne türü `vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** vektör işlecinin sol tarafındaki büyük veya eşit vektör sağ tarafında vektör; tersi durumda ise **false**.

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
