---
description: 'Daha fazla bilgi edinin: COLLATE sınıfı'
title: collate Sınıfı
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate
- locale/std::collate::char_type
- locale/std::collate::string_type
- locale/std::collate::compare
- locale/std::collate::do_compare
- locale/std::collate::do_hash
- locale/std::collate::do_transform
- locale/std::collate::hash
- locale/std::collate::transform
helpviewer_keywords:
- std::collate [C++]
- std::collate [C++], char_type
- std::collate [C++], string_type
- std::collate [C++], compare
- std::collate [C++], do_compare
- std::collate [C++], do_hash
- std::collate [C++], do_transform
- std::collate [C++], hash
- std::collate [C++], transform
ms.assetid: 92168798-9628-4a2e-be6e-fa62dcd4d6a6
ms.openlocfilehash: cef6d30167aa61c674913ac7844f6eb021a82529
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325068"
---
# <a name="collate-class"></a>collate Sınıfı

Bir dize içindeki karakterlerin sıralamasını ve gruplamasını denetlemek için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir sınıf şablonu, aralarında karşılaştırmalar ve dizelerin karması.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class collate : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, içinde benzersiz bir pozitif değer depolar `id` . Bazı dillerde, karakterler gruplandırılır ve tek bir karakter olarak ele alınır ve bazılarındaysa tekil karakterler iki karaktermiş gibi ele alınır. Harmanlama sınıfı tarafından sağlanan harmanlama hizmetleri bu durumları sıralamaya yönelik yöntem sağlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[harman](#collate)|`collate`Dize sıralama kurallarını işlemek için bir yerel ayar modeli olarak hizmet veren sınıfının nesneleri için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Türünde bir karakteri tanımlayan tür `CharType` .|
|[string_type](#string_type)|Türünde karakter içeren türde bir dizeyi tanımlayan tür `basic_string` `CharType` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Karşılaştır](#compare)|Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırır.|
|[do_compare](#do_compare)|Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırmak için çağrılan sanal işlev.|
|[do_hash](#do_hash)|Kendi modeline özgü kurallara göre dizilerin karma değerini belirlemek için çağrılan sanal işlev.|
|[do_transform](#do_transform)|Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürmek için çağrılan bir sanal işlev.|
|[yla](#hash)|Kendi modeline özgü kurallara göre dizilerin karma değerini belirler.|
|[Dönüşümler](#transform)|Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="collatechar_type"></a><a name="char_type"></a> harmanlama:: char_type

Türünde bir karakteri tanımlayan tür `CharType` .

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `CharType` .

## <a name="collatecollate"></a><a name="collate"></a> collate:: COLLATE

Dize sıralama kurallarını işlemek için bir yerel ayar modeli olarak hizmet veren sınıf harmanlama nesneleri için Oluşturucu.

```cpp
public:
    explicit collate(
    size_t _Refs = 0);

protected:
    collate(
const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

*_Locname*\
Yerel ayarın adı.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \> 1: Bu değerler tanımlı değil.

Oluşturucu kendi temel nesnesini **locale::**[model](../standard-library/locale-class.md#facet_class)() ile başlatır `_Refs` .

## <a name="collatecompare"></a><a name="compare"></a> collate:: Compare

Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırır.

```cpp
int compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Parametreler

*first1*\
Karşılaştırılacak ilk dizideki ilk öğe işaretçisi.

*last1*\
Karşılaştırılacak ilk dizideki son öğenin işaretçisi.

*first2*\
Karşılaştırılacak ikinci dizideki ilk öğenin işaretçisi.

*last2*\
Karşılaştırılacak ikinci dizideki son öğenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi şunu döndürür:

- -1 ilk sıra ikinci diziden daha az karşılaştırırsa.

- İkinci sıra ilk diziden daha az karşılaştırırsa + 1.

- diziler eşdeğer ise 0.

### <a name="remarks"></a>Açıklamalar

İlk sıra, dizideki en yakın eşit olmayan çiftte daha küçük bir öğe varsa veya eşit olmayan çiftler yoksa, ancak ilk sıra daha kısadır.

Üye işlevi [do_compare](#do_compare)döndürür ( `first1` ,, `last1` , `first2` `last2` ).

### <a name="example"></a>Örnek

```cpp
// collate_compare.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main() {
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare ( s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << result1 << endl;

   locale loc2 ( "C" );
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << result2 << endl;
}
```

## <a name="collatedo_compare"></a><a name="do_compare"></a> harmanlama::d o_compare

Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırmak için çağrılan sanal işlev.

```cpp
virtual int do_compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Parametreler

*first1*\
Karşılaştırılacak ilk dizideki ilk öğe işaretçisi.

*last1*\
Karşılaştırılacak ilk dizideki son öğenin işaretçisi.

*first2*\
Karşılaştırılacak ikinci dizideki ilk öğenin işaretçisi.

*last2*\
Karşılaştırılacak ikinci dizideki son öğenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi şunu döndürür:

- -1 ilk sıra ikinci diziden daha az karşılaştırırsa.

- İkinci sıra ilk diziden daha az karşılaştırırsa + 1.

- diziler eşdeğer ise 0.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi [* First1, last1) * konumundaki diziyi *[first2, last2*) sırasıyla karşılaştırır. `operator<`Türündeki karşılık gelen öğelerin çiftleri arasında uygulanarak değerleri karşılaştırır `CharType` . İlk sıra, dizideki en yakın eşit olmayan çiftte daha küçük bir öğe varsa veya eşit olmayan çiftler yoksa, ancak ilk sıra daha kısadır.

### <a name="example"></a>Örnek

Öğesini çağıran [collate:: Compare](#compare)örneğine bakın `do_compare` .

## <a name="collatedo_hash"></a><a name="do_hash"></a> harmanlama::d o_hash

Kendi modeline özgü kurallara göre dizilerin karma değerini belirlemek için çağrılan sanal işlev.

```cpp
virtual long do_hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dizide değeri belirlenecek olan ilk karaktere yönelik bir işaretçi.

*soyadına*\
Dizideki değeri belirlenecek olan son karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dizi için türün karma değeri **`long`** .

### <a name="remarks"></a>Açıklamalar

Karma değer, örneğin bir liste dizisi genelinde rastgele dizileri rastgele dağıtırken yararlı olabilir.

### <a name="example"></a>Örnek

' İ çağıran [karma](#hash)örneğine bakın `do_hash` .

## <a name="collatedo_transform"></a><a name="do_transform"></a> harmanlama::d o_transform

Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual string_type do_transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek dizideki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Dönüştürülecek dizideki son karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülmüş karakter dizisi olan bir dize.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen sırası [,) sırasının bir kopyası olan [string_type](#string_type) sınıfının bir nesnesini döndürür `first` `last` . Harmanlanmalardan türetilen bir sınıf \< **CharType**> [do_compare](#do_compare)geçersiz kıldığında, eşleşmesi için de geçersiz kılar `do_transform` . Öğesine geçirildiğinde `collate::compare` , dönüştürülmüş dizeleri türetilmiş sınıfta karşılaştırmak üzere geçirmeden elde edilen iki dize aynı sonucu verir.

### <a name="example"></a>Örnek

Öğesini çağıran [dönüştürme](#transform)örneğine bakın `do_transform` .

## <a name="collatehash"></a><a name="hash"></a> collate:: Hash

Kendi modeline özgü kurallara göre dizilerin karma değerini belirler.

```cpp
long hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dizide değeri belirlenecek olan ilk karaktere yönelik bir işaretçi.

*soyadına*\
Dizideki değeri belirlenecek olan son karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dizi için türün karma değeri **`long`** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_hash](#do_hash)( `first` ,) döndürür `last` .

Karma değer, örneğin bir liste dizisi genelinde rastgele dizileri rastgele dağıtırken yararlı olabilir.

### <a name="example"></a>Örnek

```cpp
// collate_hash.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("\x00dfzz abc."); // \x00df is the German sharp-s (looks like beta), it comes before z in the alphabet
   _TCHAR * s2 = _T("zzz abc."); // \x00df is the German sharp-s (looks like beta), it comes before z in the alphabet

   long r1 = use_facet< collate<_TCHAR> > ( loc ).
      hash (s1, &s1[_tcslen( s1 )-1 ]);
   long r2 =  use_facet< collate<_TCHAR> > ( loc ).
      hash (s2, &s2[_tcslen( s2 )-1 ] );
   cout << r1 << " " << r2 << endl;
}
```

```Output
541187293 551279837
```

## <a name="collatestring_type"></a><a name="string_type"></a> harmanlama:: string_type

Türünde karakter içeren türde bir dizeyi tanımlayan tür `basic_string` `CharType` .

```cpp
typedef basic_string<CharType> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir sınıf şablonu [basic_string](../standard-library/basic-string-class.md) , nesneleri kaynak dizinin kopyalarını depolayabilen bir özelleşme tanımlar.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için `string_type` bkz. [Transform](#transform).

## <a name="collatetransform"></a><a name="transform"></a> collate:: Transform

Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürür.

```cpp
string_type transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek dizideki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Dönüştürülecek dizideki son karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülmüş karakter sırasını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_transform](#do_transform)( `first` ,) döndürür `last` .

### <a name="example"></a>Örnek

```cpp
// collate_transform.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   _TCHAR* s1 = _T("\x00dfzz abc.");
   // \x00df is the German sharp-s (looks like beta),
   // it comes before z in the alphabet
   _TCHAR* s2 = _T("zzz abc.");

   collate<_TCHAR>::string_type r1;   // OK for typedef
   r1 = use_facet< collate<_TCHAR> > ( loc ).
      transform (s1, &s1[_tcslen( s1 )-1 ]);

   cout << r1 << endl;

   basic_string<_TCHAR> r2 = use_facet< collate<_TCHAR> > ( loc ).
      transform (s2, &s2[_tcslen( s2 )-1 ]);

   cout << r2 << endl;

   int result1 = use_facet<collate<_TCHAR> > ( loc ).compare
      (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );

   cout << _tcscmp(r1.c_str( ),r2.c_str( )) << result1
      << _tcscmp(s1,s2) <<endl;
}
```

```Output

-1-11
```

## <a name="see-also"></a>Ayrıca bkz.

[\<locale>](../standard-library/locale.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
