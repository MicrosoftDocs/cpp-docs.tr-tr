---
title: collate sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a18745faf6a8fe0e57e57b15c811cc153780a4f7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="collate-class"></a>collate Sınıfı

Bir dize içindeki karakterlerin sıralamasını ve gruplamasını denetlemek için bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan şablon sınıfı, aralarında karşılaştırma yapar ve dizelerin karmasını oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class collate : public locale::facet;
```

### <a name="parameters"></a>Parametreler

`CharType` Bir program içinden karakterlerin kodlanması için kullanılan türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.** Bazı dillerde, karakterler gruplandırılır ve tek bir karakter olarak ele alınır ve bazılarındaysa tekil karakterler iki karaktermiş gibi ele alınır. Harmanlama sınıfı tarafından sağlanan harmanlama hizmetleri bu durumları sıralamaya yönelik yöntem sağlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[COLLATE](#collate)|Sınıfının nesneleri için oluşturucu `collate` kuralları sıralama dize işlemek için yerel ayar model görev yapar.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir karakter türü açıklayan türü `CharType`.|
|[STRING_TYPE](#string_type)|Türü bir dize açıklayan türü `basic_string` türü karakterler içeren `CharType`.|

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

Bir karakter türü açıklayan türü **CharType**.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **CharType**.

## <a name="collate"></a>  COLLATE::COLLATE

Sınıfının nesneleri için oluşturucu kuralları sıralama dize işlemek için yerel ayar model hizmet veren collate.

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

`_Refs` Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.

`_Locname` Yerel ayar adı.

### <a name="remarks"></a>Açıklamalar

Olası değerler için `_Refs` parametre ve bunların anlamlı:

- 0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerleri tanımlanmamış.

Oluşturucu temel nesnesiyle başlatır **locale::**[modeli](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="compare"></a>  COLLATE::COMPARE

Eşitlik ve eşitsizlik için kendi modeline özgü kurallara göre iki karakterli dizileri karşılaştırır.

```cpp
int compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Parametreler

`first1` Karşılaştırılacak ilk dizisinin ilk öğesi işaretçisi.

`last1` Karşılaştırılacak ilk dizisi son öğesi işaretçisi.

`first2` Karşılaştırılacak ikinci dizisinin ilk öğesi işaretçisi.

`last2` Karşılaştırılacak ikinci dizisi son öğesi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi döndürür:

- ilk dizi ikinci dizisi sayısından az karşılaştırır, -1.

- İkinci sırası ilk dizisi sayısından az karşılaştırır, + 1.

- 0 sıraları eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

İlk dizi daha az serileri erken eşit olmayan çiftindeki küçük öğenin varsa veya, hiçbir eşit olmayan çiftleri var, ancak ilk dizisi kısadır karşılaştırır.

Üye işlevi döndürür [do_compare](#do_compare)( `first1`, `last1`, `first2`, `last2`).

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

`first1` Karşılaştırılacak ilk dizisinin ilk öğesi işaretçisi.

`last1` Karşılaştırılacak ilk dizisi son öğesi işaretçisi.

`first2` Karşılaştırılacak ikinci dizisinin ilk öğesi işaretçisi.

`last2` Karşılaştırılacak ikinci dizisi son öğesi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi döndürür:

- ilk dizi ikinci dizisi sayısından az karşılaştırır, -1.

- İkinci sırası ilk dizisi sayısından az karşılaştırır, + 1.

- 0 sıraları eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye fonksiyonu adresindeki dizisi karşılaştırır [* first1, Last1) * dizisiyle *[first2, Soyadı2*). Uygulayarak değerlerini karşılaştırır **işleci <** türdeki karşılık gelen öğeleri çiftleri arasındaki **CharType**. İlk dizi daha az serileri erken eşit olmayan çiftindeki küçük öğenin varsa ya da eşit olmayan bir çiftleri var, ancak ilk dizisi kısadır karşılaştırır.

### <a name="example"></a>Örnek

Örneğin bkz [collate::compare](#compare), çağıran `do_compare`.

## <a name="do_hash"></a>  COLLATE::do_hash

Kendi modeline özgü kurallara göre dizilerin karma değerini belirlemek için çağrılan sanal işlev.

```cpp
virtual long do_hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

`first` Bir özelliği olan değer dizisi ilk karakteri belirlenecek işaretçidir.

`last` Bir özelliği olan değer dizisi son karakter belirlenecek işaretçidir.

### <a name="return-value"></a>Dönüş Değeri

Bir karma değer türü **uzun** dizisi.

### <a name="remarks"></a>Açıklamalar

Bir karma değer, örneğin, dizileri sözde rastgele listeleri bir dizi arasında dağıtılmasında yararlı olabilir.

### <a name="example"></a>Örnek

Örneğin bkz [karma](#hash), çağıran `do_hash`.

## <a name="do_transform"></a>  collate::do_transform

Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual string_type do_transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

`first` Dönüştürülecek sıradaki ilk karakteri bir işaretçi.

`last` Dönüştürülecek sıradaki son karakter bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülen bir karakter dizisi olan bir dize.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye fonksiyonu sınıfın bir nesnesi döndüren [STRING_TYPE](#string_type) , denetlenen sırası dizisi kopyasıdır [ `first`, `last`). Öğesinden türetilmiş bir sınıf, collate\< **CharType**> geçersiz kılmaları [do_compare](#do_compare), ayrıca geçersiz kılmalısınız `do_transform` eşleşecek şekilde. İçin geçirildiğinde `collate::compare`, iki dönüştürülmüş dizeyi dönüştürülmemiş dizeleri geçirme türetilen sınıfta karşılaştırmak için elde edebileceğiniz aynı sonucu verecek.

### <a name="example"></a>Örnek

Örneğin bkz [dönüştürme](#transform), çağıran `do_transform`.

## <a name="hash"></a>  COLLATE::hash

Kendi modeline özgü kurallara göre dizilerin karma değerini belirler.

```cpp
long hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

`first` Bir özelliği olan değer dizisi ilk karakteri belirlenecek işaretçidir.

`last` Bir özelliği olan değer dizisi son karakter belirlenecek işaretçidir.

### <a name="return-value"></a>Dönüş Değeri

Bir karma değer türü **uzun** dizisi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_hash](#do_hash)( `first`, `last`).

Bir karma değer, örneğin, dizileri sözde rastgele listeleri bir dizi arasında dağıtılmasında yararlı olabilir.

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

Türü bir dize açıklayan türü `basic_string` türü karakterler içeren **CharType**.

```cpp
typedef basic_string<CharType> string_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı uzmanlaşması türünü açıklayan [basic_string](../standard-library/basic-string-class.md) nesnelerin kaynak sıradaki kopyalarını depolayabilirsiniz.

### <a name="example"></a>Örnek

Bildirme ve kullanma konusunda bir örnek için `string_type`, bkz: [dönüştürme](#transform).

## <a name="transform"></a>  COLLATE::Transform

Yerel ayarındaki karakter dizisini lexicographical karşılaştırmasına benzer şekilde aynı yerel ayardan dönüştürülen diğer karakter dizileri ile kullanılabilecek bir dize dönüştürür.

```cpp
string_type transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

`first` Dönüştürülecek sıradaki ilk karakteri bir işaretçi.

`last` Dönüştürülecek sıradaki son karakter bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülen bir karakter dizisi içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_transform](#do_transform)( `first`, `last`).

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
