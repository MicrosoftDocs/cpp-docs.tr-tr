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
ms.openlocfilehash: 21d5825f8d9ea00359f2aa1c87291b831d1f330f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630119"
---
# <a name="collate-class"></a>collate Sınıfı

Bir dize içindeki karakterlerin sıralamasını ve gruplamasını denetlemek için bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan şablon sınıfı, aralarında karşılaştırma yapar ve dizelerin karmasını oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class collate : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*<br/>
Bir program içindeki karakterleri kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar `id`. Bazı dillerde, karakterler gruplandırılır ve tek bir karakter olarak ele alınır ve bazılarındaysa tekil karakterler iki karaktermiş gibi ele alınır. Harmanlama sınıfı tarafından sağlanan harmanlama hizmetleri bu durumları sıralamaya yönelik yöntem sağlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[COLLATE](#collate)|Sınıfındaki nesneler için oluşturucu `collate` dize sıralama kurallarını işlemek için bir yerel ayar modeli olarak hizmet verir.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Türü bir karakteri tanımlayan tür `CharType`.|
|[string_type](#string_type)|Türü dizeyi tanımlayan tür `basic_string` türü karakterler içeren `CharType`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Karşılaştırma](#compare)|Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırır.|
|[do_compare](#do_compare)|Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırmak için çağrılan sanal işlev.|
|[do_hash](#do_hash)|Kendi modeline özgü kurallara göre dizilerin karma değerini belirlemek için çağrılan sanal işlev.|
|[do_transform](#do_transform)|Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürmek için çağrılan bir sanal işlev.|
|[Karma](#hash)|Kendi modeline özgü kurallara göre dizilerin karma değerini belirler.|
|[transform](#transform)|Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  COLLATE::char_type

Türü bir karakteri tanımlayan tür `CharType`.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `CharType`.

## <a name="collate"></a>  COLLATE::COLLATE

Sınıfındaki nesneler için oluşturucu collate dize sıralama kurallarını işlemek için bir yerel ayar modeli olarak hizmet veren.

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

*_Refs*<br/>
Bellek yönetimi için nesne türünü belirtmek için kullanılan tamsayı değeri.

*_Locname*<br/>
Yerel ayar adı.

### <a name="remarks"></a>Açıklamalar

Olası değerler için *_Refs* parametresi ve bunların önemi:

- 0: nesne ömrü onu içeren yerel ayarlar tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerler tanımlanmadı.

Oluşturucu, temel nesnesiyle başlatır **yerel::**[modeli](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="compare"></a>  COLLATE::COMPARE

Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırır.

```cpp
int compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Karşılaştırılacak ilk dizideki ilk öğesinin işaretçisi.

*last1*<br/>
Karşılaştırılacak Birinci sıradaki son öğesinin işaretçisi.

*first2*<br/>
Karşılaştırılacak ikinci dizideki ilk öğesinin işaretçisi.

*Soyadı2*<br/>
Karşılaştırılacak ikinci dizideki son öğesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi döndürür:

- ilk dizi ikinci sırası sayısından az karşılaştırırsa -1.

- İkinci sırası daha azını ilk dizi karşılaştırırsa + 1.

- 0 dizileri eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

İlk dizi küçük erken eşit çiftindeki dizileri, daha küçük öğe varsa veya, hiçbir eşit çiftleri var, ancak ilk dizi kısadır karşılaştırır.

Üye işlevinin döndürdüğü [do_compare](#do_compare)( `first1`, `last1`, `first2`, `last2`).

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

## <a name="do_compare"></a>  COLLATE::do_compare

Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırmak için çağrılan sanal işlev.

```cpp
virtual int do_compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Karşılaştırılacak ilk dizideki ilk öğesinin işaretçisi.

*last1*<br/>
Karşılaştırılacak Birinci sıradaki son öğesinin işaretçisi.

*first2*<br/>
Karşılaştırılacak ikinci dizideki ilk öğesinin işaretçisi.

*Soyadı2*<br/>
Karşılaştırılacak ikinci dizideki son öğesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi döndürür:

- ilk dizi ikinci sırası sayısından az karşılaştırırsa -1.

- İkinci sırası daha azını ilk dizi karşılaştırırsa + 1.

- 0 dizileri eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, sıra karşılaştırır [* first1, Last1) * sıra *[first2, Soyadı2*). Uygulayarak değerlerini karşılaştırır `operator<` türdeki karşılık gelen öğeleri çiftleri arasındaki `CharType`. İlk dizi küçük erken eşit çiftindeki dizileri, daha küçük öğe varsa ya da eşit olmayan hiçbir çiftleri var, ancak ilk dizi kısadır karşılaştırır.

### <a name="example"></a>Örnek

Örneğin bakın [collate::compare](#compare), çağıran `do_compare`.

## <a name="do_hash"></a>  COLLATE::do_hash

Kendi modeline özgü kurallara göre dizilerin karma değerini belirlemek için çağrılan sanal işlev.

```cpp
virtual long do_hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Belirlenmesi için ayarlanmış olan değer dizideki ilk karaktere bir işaretçi var.

*Son*<br/>
Bir özelliği olan değer dizideki son karakter belirlenecek işaretçisidir.

### <a name="return-value"></a>Dönüş Değeri

Bir karma değer türü **uzun** sırası.

### <a name="remarks"></a>Açıklamalar

Bir karma değer, örneğin, dizileri sözde rastgele listelerin bir dizi bulunursa, yararlı olabilir.

### <a name="example"></a>Örnek

Örneğin bakın [karma](#hash), çağıran `do_hash`.

## <a name="do_transform"></a>  collate::do_transform

Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual string_type do_transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dönüştürülecek dizideki ilk karaktere bir işaretçi.

*Son*<br/>
Dönüştürülecek dizideki son karakter işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülen karakter dizisi bir dize.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi sınıfın bir nesnesi döndürür [string_type](#string_type) , denetlenen bir dizi sırası bir kopyasıdır [ `first`, `last`). Öğesinden türetilen bir sınıf, collate\< **CharType**> geçersiz kılmalar [do_compare](#do_compare), ayrıca geçersiz kılmalıdır `do_transform` eşleştirilecek. Geçirilen zaman `collate::compare`, iki dönüştürülen dizeleri dönüştürülmemiş dizeleri geçmesini türetilen sınıfta Karşılaştırılacak elde edebileceğiniz aynı sonucu elde etmek.

### <a name="example"></a>Örnek

Örneğin bakın [dönüştürme](#transform), çağıran `do_transform`.

## <a name="hash"></a>  COLLATE::hash

Kendi modeline özgü kurallara göre dizilerin karma değerini belirler.

```cpp
long hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Belirlenmesi için ayarlanmış olan değer dizideki ilk karaktere bir işaretçi var.

*Son*<br/>
Bir özelliği olan değer dizideki son karakter belirlenecek işaretçisidir.

### <a name="return-value"></a>Dönüş Değeri

Bir karma değer türü **uzun** sırası.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_hash](#do_hash)( `first`, `last`).

Bir karma değer, örneğin, dizileri sözde rastgele listelerin bir dizi bulunursa, yararlı olabilir.

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

## <a name="string_type"></a>  COLLATE::string_type

Türü dizeyi tanımlayan tür `basic_string` türü karakterler içeren `CharType`.

```cpp
typedef basic_string<CharType> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [basic_string](../standard-library/basic-string-class.md) kaynak dizisinin bir kopyasını, nesneleri depolayabilirsiniz.

### <a name="example"></a>Örnek

Bildirme ve kullanma konusunda bir örnek için `string_type`, bkz: [dönüştürme](#transform).

## <a name="transform"></a>  COLLATE::Transform

Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürür.

```cpp
string_type transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dönüştürülecek dizideki ilk karaktere bir işaretçi.

*Son*<br/>
Dönüştürülecek dizideki son karakter işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülen karakter dizisi içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_transform](#do_transform)(`first`, `last`).

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

[\<yerel ayar >](../standard-library/locale.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
