---
title: '&lt;hash_map&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::operator!=
- hash_map/std::operator==
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
ms.openlocfilehash: c4cc73feb3c8163a2be9f0122f57eaa0fb8ab3b8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448725"
---
# <a name="lthashmapgt-operators"></a>&lt;hash_map&gt; işleçleri

|||
|-|-|
|[operator!=](#op_neq)|[işleç! = (multimap)](#op_neq_mm)|
|[operator==](#op_eq_eq)|[işleç = = (multimap)](#op_eq_eq_mm)|

## <a name="op_neq"></a>işleç! =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_map sınıfıdır](unordered-map-class.md).

İşlecin sol tarafındaki hash_map nesnesinin, sağ taraftaki hash_map nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Türünde `hash_map`bir nesne.

*Right*\
Türünde `hash_map`bir nesne.

### <a name="return-value"></a>Dönüş Değeri

hash_maps eşitse **true** ; hash_maps eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Hash_map nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki hash_maps aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

[< Hash_map >](hash-map.md) ve [< hash_set >](hash-set.md) başlık dosyaları [stdext ad alanında](stdext-namespace.md).

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

## <a name="op_eq_eq"></a>işleç = =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_map sınıfıdır](unordered-map-class.md).

İşlecin sol tarafındaki hash_map nesnesinin, sağ taraftaki hash_map nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Türünde `hash_map`bir nesne.

*Right*\
Türünde `hash_map`bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki hash_map işlecin sağ tarafındaki hash_map öğesine eşitse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Hash_map nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki hash_maps aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="op_neq_mm"></a>işleç! = (hash_multimap)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_multimap sınıfıdır](unordered-multimap-class.md).

İşlecin sol tarafındaki hash_multimap nesnesinin, sağ taraftaki hash_multimap nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Türünde `hash_multimap`bir nesne.

*Right*\
Türünde `hash_multimap`bir nesne.

### <a name="return-value"></a>Dönüş Değeri

hash_multimaps eşitse **true** ; hash_multimaps eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Hash_multimap nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki hash_multimaps aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="op_eq_eq_mm"></a>operator = = (hash_multimap)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_multimap sınıfıdır](unordered-multimap-class.md).

İşlecin sol tarafındaki hash_multimap nesnesinin, sağ taraftaki hash_multimap nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Türünde `hash_multimap`bir nesne.

*Right*\
Türünde `hash_multimap`bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki hash_multimap işlecin sağ tarafındaki hash_multimap öğesine eşitse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Hash_multimap nesneleri arasındaki karşılaştırma, öğelerinin ikili bir karşılaştırmasını temel alır. İki hash_multimaps aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olduğunda eşittir. Aksi takdirde, bunlar eşit değildir.

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

[<hash_map>](hash-map.md)
