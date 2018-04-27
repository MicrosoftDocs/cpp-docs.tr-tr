---
title: '&lt;hash_map&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- hash_map/std::operator!=
- hash_map/std::operator==
dev_langs:
- C++
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
caps.latest.revision: 13
manager: ghogen
ms.openlocfilehash: 0b4b2a2c98e47752dbfb30afb2a0de522bcbb9f7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="lthashmapgt-operators"></a>&lt;hash_map&gt; işleçleri

|||
|-|-|
|[operator!=](#op_neq)|[operator! = (multimap)](#op_neq_mm)|
|[operator==](#op_eq_eq)|[operator == (multimap)](#op_eq_eq_mm)|

## <a name="op_neq"></a>  operator! =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](unordered-map-class.md).

Hash_map nesne işlecinin sol tarafındaki sağ tarafında hash_map nesnesine eşit değilse testleri.

```cpp
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `hash_map`.

`right` Türünde bir nesne `hash_map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_maps eşit; değilse **false** hash_maps eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Hash_map nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki hash_maps aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

Üyeleri [< hash_map >](hash-map.md) ve [< hash_set >](hash-set.md) başlık dosyaları [ stdext Namespace](stdext-namespace.md).

### <a name="example"></a>Örnek

```cpp
// hash_map_op_ne.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 != hm2 )
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;
   else
      cout << "The hash_maps hm1 and hm2 are equal." << endl;

   if ( hm1 != hm3 )
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;
   else
      cout << "The hash_maps hm1 and hm3 are equal." << endl;
}
```

```Output
The hash_maps hm1 and hm2 are not equal.
The hash_maps hm1 and hm3 are equal.
```

## <a name="op_eq_eq"></a>  operator ==

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](unordered-map-class.md).

Hash_map nesne işlecinin sol tarafındaki sağ tarafında hash_map nesnesine eşitse testleri.

```cpp
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `hash_map`.

`right` Türünde bir nesne `hash_map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_map işlecinin sol tarafındaki işlecinin sağ tarafında hash_map eşit; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Hash_map nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki hash_maps aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// hash_map_op_eq.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 == hm2 )
      cout << "The hash_maps hm1 and hm2 are equal." << endl;
   else
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;

   if ( hm1 == hm3 )
      cout << "The hash_maps hm1 and hm3 are equal." << endl;
   else
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;
}
```

```Output
The hash_maps hm1 and hm2 are not equal.
The hash_maps hm1 and hm3 are equal.
```

## <a name="op_neq_mm"></a>  operator! = (hash_multimap)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](unordered-multimap-class.md).

Testleri işlecinin sol tarafındaki hash_multimap nesnesi sağ tarafında hash_multimap nesnesine eşit değil.

```cpp
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `hash_multimap`.

`right` Türünde bir nesne `hash_multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_multimaps eşit; değilse **false** hash_multimaps eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Hash_multimap nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki hash_multimaps aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_op_ne.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 != hm2 )
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;

   if ( hm1 != hm3 )
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;
}
```

```Output
The hash_multimaps hm1 and hm2 are not equal.
The hash_multimaps hm1 and hm3 are equal.
```

## <a name="op_eq_eq_mm"></a>  operator == (hash_multimap)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](unordered-multimap-class.md).

Hash_multimap nesne işlecinin sol tarafındaki sağ tarafında hash_multimap nesnesine eşitse testleri.

```cpp
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne `hash_multimap`.

`right` Türünde bir nesne `hash_multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_multimap işlecinin sol tarafındaki işlecinin sağ tarafında hash_multimap eşit; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Hash_multimap nesneleri arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki hash_multimaps aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_op_eq.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap<int, int> hm1, hm2, hm3;
   int i;
   typedef pair<int, int> Int_Pair;

   for (i = 0; i < 3; i++)
   {
      hm1.insert(Int_Pair(i, i));
      hm2.insert(Int_Pair(i, i*i));
      hm3.insert(Int_Pair(i, i));
   }

   if ( hm1 == hm2 )
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;

   if ( hm1 == hm3 )
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;
}
```

```Output
The hash_multimaps hm1 and hm2 are not equal.
The hash_multimaps hm1 and hm3 are equal.
```

## <a name="see-also"></a>Ayrıca bkz.

[<hash_map>](hash-map.md)<br/>
