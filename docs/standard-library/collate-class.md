---
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
ms.openlocfilehash: f05c2e9482f8a0bada3868fdc946d4d26a0e0e1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371933"
---
# <a name="collate-class"></a>collate Sınıfı

Bir dize içindeki karakterlerin sıralanması ve gruplanması, bunlar ile dizelerin karmalarını karşılaştırmaları denetlemek için yerel bir yönü olarak hizmet verebilecek bir nesneyi açıklayan bir sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class collate : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk girişim benzersiz `id`bir pozitif değer depolar. Bazı dillerde, karakterler gruplandırılır ve tek bir karakter olarak ele alınır ve bazılarındaysa tekil karakterler iki karaktermiş gibi ele alınır. Harmanlama sınıfı tarafından sağlanan harmanlama hizmetleri bu durumları sıralamaya yönelik yöntem sağlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Collate](#collate)|Dize sıralama kuralları işlemek `collate` için yerel bir yönü olarak hizmet veren sınıf nesneleri için oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir tür `CharType`karakterini açıklayan bir tür.|
|[string_type](#string_type)|Tür karakterleri içeren bir `basic_string` tür dizesini `CharType`açıklayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Karşılaştırmak](#compare)|Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırır.|
|[do_compare](#do_compare)|Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırmak için çağrılan sanal işlev.|
|[do_hash](#do_hash)|Kendi modeline özgü kurallara göre dizilerin karma değerini belirlemek için çağrılan sanal işlev.|
|[do_transform](#do_transform)|Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürmek için çağrılan bir sanal işlev.|
|[Karma](#hash)|Kendi modeline özgü kurallara göre dizilerin karma değerini belirler.|
|[Dönüştürmek](#transform)|Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="collatechar_type"></a><a name="char_type"></a>harman::char_type

Bir tür `CharType`karakterini açıklayan bir tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `CharType`ile eş anlamlıdır.

## <a name="collatecollate"></a><a name="collate"></a>harman::harman

Dize sıralama kuralları işlemek için bir yerel fason olarak hizmet veren sınıf harman nesneleri için oluşturucu.

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

*_refs*\
Nesneiçin bellek yönetimi türünü belirtmek için kullanılan eden arameger değeri.

*_Locname*\
Yerel yerin adı.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve önemi şunlardır:

- 0: Nesnenin ömrü, onu içeren yerel nesneler tarafından yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değildir.

Kurucu, temel nesnesini yerel olarak başlaşır:: **locale::**[fason](../standard-library/locale-class.md#facet_class)( ).`_Refs`

## <a name="collatecompare"></a><a name="compare"></a>harman::karşılaştır

Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırır.

```cpp
int compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Parametreler

*ilk1*\
Karşılaştırılacak ilk sırada ilk öğeyi işaretle.

*son1*\
Karşılaştırılacak ilk dizideki son öğeyi işaretle.

*ilk2*\
Karşılaştırılacak ikinci sırada ilk öğeiçin işaretçi.

*son2*\
Karşılaştırılacak ikinci sırada son öğeyi işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev döner:

- -1 eğer ilk sekans ikinci sekanstan daha az karşılaştırırsa.

- +1 eğer ikinci sıra ilk ardandan daha az karşılaştırırsa.

- Diziler eşdeğerse 0.

### <a name="remarks"></a>Açıklamalar

İlk sıra, dizilerde en erken eşit olmayan çiftte daha küçük öğeye sahipse veya eşit olmayan çiftler yoksa, ilk sıra daha kısaysa daha az karşılaştırır.

Üye işlev [do_compare](#do_compare) `first1`döndürür ( , , `last1` `first2`, . `last2`

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

## <a name="collatedo_compare"></a><a name="do_compare"></a>harman::do_compare

Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırmak için çağrılan sanal işlev.

```cpp
virtual int do_compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Parametreler

*ilk1*\
Karşılaştırılacak ilk sırada ilk öğeyi işaretle.

*son1*\
Karşılaştırılacak ilk dizideki son öğeyi işaretle.

*ilk2*\
Karşılaştırılacak ikinci sırada ilk öğeiçin işaretçi.

*son2*\
Karşılaştırılacak ikinci sırada son öğeyi işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev döner:

- -1 eğer ilk sekans ikinci sekanstan daha az karşılaştırırsa.

- +1 eğer ikinci sıra ilk ardandan daha az karşılaştırırsa.

- Diziler eşdeğerse 0.

### <a name="remarks"></a>Açıklamalar

Korunan sanal üye işlevi [ * first1, Last1)* dizisini *[ first2, last2]* dizisiyle karşılaştırır. Bu tür `CharType`karşılık gelen `operator<` öğelerin çiftleri arasında uygulayarak değerleri karşılaştırır. İlk sıra, dizilerde en erken eşit olmayan çiftte daha küçük elemana sahipse veya eşit olmayan çiftler yoksa, ilk sıra daha kısaysa daha az karşılaştırır.

### <a name="example"></a>Örnek

Harmanlamak için örneğe [bakın::karşılaştırın](#compare), hangi çağrıları . `do_compare`

## <a name="collatedo_hash"></a><a name="do_hash"></a>harmlate::do_hash

Kendi modeline özgü kurallara göre dizilerin karma değerini belirlemek için çağrılan sanal işlev.

```cpp
virtual long do_hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Değeri olan dizideki ilk karaktere işaretçi belirlenecek.

*Son*\
Değeri olan dizideki son karaktere işaretçi belirlenecek.

### <a name="return-value"></a>Dönüş Değeri

Dizi için **uzun** olan türkarma değeri.

### <a name="remarks"></a>Açıklamalar

Karma değer, örneğin, bir dizi liste arasında sözde rasgele dizileri dağıtmak yararlı olabilir.

### <a name="example"></a>Örnek

Bkz. [karma](#hash)için örnek `do_hash`, hangi çağırır .

## <a name="collatedo_transform"></a><a name="do_transform"></a>harmlate::do_transform

Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual string_type do_transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizideki ilk karaktere işaretçi.

*Son*\
Dönüştürülecek dizideki son karaktere işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülmüş karakter dizisi olan bir dize.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen dizi sıranın bir kopyası `first` `last`olan sınıf [string_type](#string_type) bir nesnedöndürür [ , ). \< **Harmanlama CharType**> türetilen bir sınıf do_compare geçersiz `do_transform` [kılarsa,](#do_compare)aynı zamanda eşleşmesi geçersiz kılınmalıdır. `collate::compare`Geçirilen, iki dönüştürülmüş dizeleri türemiş sınıfta karşılaştırmak için dönüştürülmemiş dizeleri geçen alacağı aynı sonucu vermelidir.

### <a name="example"></a>Örnek

[Dönüştürme](#transform)örneğine bakın , `do_transform`hangi çağırır .

## <a name="collatehash"></a><a name="hash"></a>harman::karma

Kendi modeline özgü kurallara göre dizilerin karma değerini belirler.

```cpp
long hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Değeri olan dizideki ilk karaktere işaretçi belirlenecek.

*Son*\
Değeri olan dizideki son karaktere işaretçi belirlenecek.

### <a name="return-value"></a>Dönüş Değeri

Dizi için **uzun** olan türkarma değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_hash](#do_hash) `first`döndürür ( , `last`).

Karma değer, örneğin, bir dizi liste arasında sözde rasgele dizileri dağıtmak yararlı olabilir.

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

## <a name="collatestring_type"></a><a name="string_type"></a>harman::string_type

Tür karakterleri içeren bir `basic_string` tür dizesini `CharType`açıklayan bir tür.

```cpp
typedef basic_string<CharType> string_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, nesneleri kaynak dizinin kopyalarını depolayabilen sınıf şablonu [basic_string](../standard-library/basic-string-class.md) bir uzmanlık açıklar.

### <a name="example"></a>Örnek

Nasıl beyan ve kullanılacağına `string_type`bir örnek için bkz. [transform](#transform)

## <a name="collatetransform"></a><a name="transform"></a>harman::dönüştürme

Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürür.

```cpp
string_type transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizideki ilk karaktere işaretçi.

*Son*\
Dönüştürülecek dizideki son karaktere işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülmüş karakter dizisini içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_transform](#do_transform)`first`döndürür ( , `last`).

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

[\<yerel>](../standard-library/locale.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
