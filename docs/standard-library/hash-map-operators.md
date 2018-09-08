---
title: '&lt;hash_map&gt; işleçler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_map/std::operator!=
- hash_map/std::operator==
dev_langs:
- C++
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
ms.openlocfilehash: bd140fed954c097fa73f179c92cbc64f3148e77c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108467"
---
# <a name="lthashmapgt-operators"></a>&lt;hash_map&gt; işleçleri

|||
|-|-|
|[operator!=](#op_neq)|[işleç! = (multimap)](#op_neq_mm)|
|[operator==](#op_eq_eq)|[işleç == (multimap)](#op_eq_eq_mm)|

## <a name="op_neq"></a>  işleç! =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](unordered-map-class.md).

İşlecin sol tarafındaki hash_map nesne işlecin sağ tarafındaki hash_map nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `hash_map`.

*sağ*<br/>
Bir nesne türü `hash_map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_maps eşit; değilse, **false** hash_maps eşitse.

### <a name="remarks"></a>Açıklamalar

Hash_map nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki hash_maps eşit olur. Aksi takdirde, eşit oldukları.

Üyeleri [< hash_map >](hash-map.md) ve [< hash_set >](hash-set.md) üstbilgi dosyalarını [ stdext Namespace](stdext-namespace.md).

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

## <a name="op_eq_eq"></a>  işleç ==

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](unordered-map-class.md).

İşlecin sol tarafındaki hash_map nesnesinin işlecin sağ tarafındaki hash_map nesneye eşit olup olmadığını sınar.

```cpp
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `hash_map`.

*sağ*<br/>
Bir nesne türü `hash_map`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_map işlecinin sol tarafındaki ise, aksi takdirde işlecin sağ tarafındaki hash_map eşit **false**.

### <a name="remarks"></a>Açıklamalar

Hash_map nesneleri arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki hash_maps eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_neq_mm"></a>  işleç! = (hash_multimap)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](unordered-multimap-class.md).

İşlecin sol tarafındaki hash_multimap nesne işlecin sağ tarafındaki hash_multimap nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `hash_multimap`.

*sağ*<br/>
Bir nesne türü `hash_multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_multimaps eşit; değilse, **false** hash_multimaps eşitse.

### <a name="remarks"></a>Açıklamalar

Hash_multimap nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki hash_multimaps eşit olur. Aksi takdirde, eşit oldukları.

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

## <a name="op_eq_eq_mm"></a>  işleç == (hash_multimap)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](unordered-multimap-class.md).

İşlecin sol tarafındaki hash_multimap nesnesinin işlecin sağ tarafındaki hash_multimap nesneye eşit olup olmadığını sınar.

```cpp
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir nesne türü `hash_multimap`.

*sağ*<br/>
Bir nesne türü `hash_multimap`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_multimap işlecinin sol tarafındaki ise, aksi takdirde işlecin sağ tarafındaki hash_multimap eşit **false**.

### <a name="remarks"></a>Açıklamalar

Hash_multimap nesneler arasında karşılaştırma öğeleri üzerinde bir ikili karşılaştırma temel alır. Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki hash_multimaps eşit olur. Aksi takdirde, eşit oldukları.

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
