---
title: codecvt sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
dev_langs:
- C++
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fac73456108669950f59f2399495526b8b319f07
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956813"
---
# <a name="codecvt-class"></a>codecvt Sınıfı

Bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı. Programın içindeki karakterleri ve program dışındaki karakterleri kodlamak için kullanılan değerler dizisi arasındaki dönüştürmeleri denetleyebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>Parametreler

*CharType* bir program içindeki karakterleri kodlamak için kullanılan tür.

*Bayt* bir program dışındaki karakterleri kodlamak için kullanılan bir tür.

*StateType* karakter temsillerinin iç ve dış türleri arasındaki bir dönüştürmenin Ara durumlarını temsil etmek için kullanılan bir tür.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı olarak hizmet verebilen bir nesneyi tanımlayan bir [yerel ayar modeli](../standard-library/locale-class.md#facet_class)türü değerler dizisi arasındaki dönüştürmeleri denetlemek için *CharType* türü değerler dizisi *bayt*. Sınıf *StateType* dönüştürmeyi karakterize ve sınıfın bir nesnesi belirtir *StateType* herhangi bir dönüştürme sırasında gerekli durumu bilgilerini depolar.

İç kodlama bir gösterimini bayt karakter başına sabit sayıda genellikle kullanır **char** veya türü **wchar_t**.

Statik nesne bir yerel ayar modelinde olduğu gibi `id` bir başlangıç sıfır değeri saklanan. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar `id`.

Şablon sürümleri [do_in](#do_in) ve [do_out](#do_out) her zaman dönüş `codecvt_base::noconv`.

C++ Standart Kitaplığı çeşitli açık uzmanlık tanımlar:

`template<>`

`codecvt<wchar_t, char, mbstate_t>`

arasında dönüştürür **wchar_t** ve **char** dizileri.

`template<>`

`codecvt<char16_t, char, mbstate_t>`

arasında dönüştürür `char16_t` UTF-16 kodlanmış diziler ve **char** UTF-8 olarak kodlanmış diziler.

`template<>`

`codecvt<char32_t, char, mbstate_t>`

arasında dönüştürür `char32_t` UTF-32 (UCS-4) kodlanmış diziler ve **char** UTF-8 olarak kodlanmış diziler.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[codecvt](#codecvt)|Sınıfındaki nesneler için oluşturucu `codecvt` dönüştürmeleri işlemek için bir yerel ayar modeli hizmet verir.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[extern_type](#extern_type)|Dış temsiller için kullanılan karakter türü.|
|[intern_type](#intern_type)|İç temsiller için kullanılan karakter türü.|
|[state_type](#state_type)|İç ve dış temsiller arasındaki dönüştürmeler sırasında ara durumları temsil etmek için kullanılan bir karakter türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[always_noconv](#always_noconv)|Bir dönüştürme yapılıp yapılmayacağını sınar.|
|[do_always_noconv](#do_always_noconv)|Hiçbir dönüştürme yapılması gerekip gerekmediğini sınamak için çağrılan bir sanal işlev.|
|[do_encoding](#do_encoding)|Bir sanal işlev olmadığını test eder, kodlama `Byte` akışının kodlamasının durum bağımlı olup olmadığını arasındaki oran `Byte`kullanılıp kullanılmayacağını ve `CharType`sabittir ve yanıt olumluysa, bu durumda, bu oran değerini belirler.|
|[do_in](#do_in)|İç dönüştürmek için çağrılan sanal işlev `Byte`dizisini dış `CharType`s.|
|[do_length](#do_length)|Belirleyen bir sanal işlev kaç `Byte`dış verili dizisinin `Byte`iç belirli bir sayıdan daha fazla olmayan `CharType`s ve bu sayı kadar döndürür `Byte`s.|
|[do_max_length](#do_max_length)|En yüksek dış bayt sayısını oluşturmak için gerekli iç döndüren bir sanal işlev `CharType`.|
|[do_out](#do_out)|İç dönüştürmek için çağrılan sanal işlev `CharType`dizisini dış baytların s.|
|[do_unshift](#do_unshift)|Sağlamak için çağrılan sanal işlev `Byte`dizisindeki son karakteri tamamlamak için durum bağımlı bir dönüştürmede gereken `Byte`s.|
|[Kodlama](#encoding)|Olmadığını test eder, kodlama `Byte` akışının kodlamasının durum bağımlı olup olmadığını arasındaki oran `Byte`kullanılıp kullanılmayacağını ve `CharType`sabittir ve yanıt olumluysa, bu durumda, bu oran değerini belirler.|
|[in](#in)|Bir dizi bir dış temsilini dönüştürür `Byte`s, bir dizi bir iç temsiline `CharType`s.|
|[Uzunluğu](#length)|Belirler kaç `Byte`dış verili dizisinin `Byte`iç belirli bir sayıdan daha fazla olmayan `CharType`s ve bu sayı kadar döndürür `Byte`s.|
|[max_length](#max_length)|Dış maksimum sayısını döndürür `Byte`s bir dahili üretmek için gerekli `CharType`.|
|[out](#out)|İç dönüştürür `CharType`dizisini dış `Byte`s.|
|[unshift](#unshift)|Dış sağlar `Byte`dizisindeki son karakteri tamamlamak için durum bağımlı bir dönüştürmede gereken `Byte`s.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="always_noconv"></a>  codecvt::always_noconv

Bir dönüştürme yapılıp yapılmayacağını sınar.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Boolean değer **true** herhangi bir dönüştürme yapılıp; **false** en az bir yapılması gerekiyor.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_always_noconv](#do_always_noconv).

### <a name="example"></a>Örnek

```cpp
// codecvt_always_noconv.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvt"></a>  codecvt::codecvt

Dönüştürmeleri işlemek için bir yerel ayar modeli hizmet veren sınıf codecvt nesneler için oluşturucu.

```cpp
explicit codecvt(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs* nesne için bellek yönetimi türünü belirtmek için kullanılan bir tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için *_Refs* parametresi ve bunların önemi:

- 0: nesne ömrü onu içeren yerel ayarlar tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerler tanımlanmadı.

Oluşturucu başlatır, `locale::facet` temel nesne **yerel::**[modeli](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="do_always_noconv"></a>  codecvt::do_always_noconv

Hiçbir dönüştürme yapılması gerekip gerekmediğini sınamak için çağrılan bir sanal işlev.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi döndürür **true** yalnızca yapılan her çağrı [do_in](#do_in) veya [do_out](#do_out) döndürür `noconv`.

Şablon sürümü her zaman döndürür **true**.

### <a name="example"></a>Örnek

Örneğin bakın [always_noconv](#always_noconv), çağıran `do_always_noconv`.

## <a name="do_encoding"></a>  codecvt::do_encoding

Bir sanal işlev olmadığını test eder, kodlama `Byte` akışının kodlamasının durum bağımlı olup olmadığını arasındaki oran `Byte`kullanılıp kullanılmayacağını ve `CharType`sabittir ve yanıt olumluysa bu durumda, bu oran değerini belirler.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi döndürür:

- -1, kodlama türü dönüştürülmelerini `extern_type` durumuna bağlıdır.

- 0, kodlama değişen uzunluktaki dizileri içeriyorsa.

- *N*, kodlama yalnızca dizilerinin uzunluğu içeriyorsa *N*

### <a name="example"></a>Örnek

Örneğin bakın [kodlama](#encoding), çağıran `do_encoding`.

## <a name="do_in"></a>  codecvt::do_in

Dizisini dış dönüştürmek için çağrılan sanal işlev `Byte`iç dizisini `CharType`s.

```cpp
virtual result do_in(
    StateType& _State,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Parametreler

*Duru_m* üye işleve yapılan çağrılar arasındaki tutulan dönüştürme durumu.

*first1* başına dönüştürülecek dizisinin işaretçisi.

*last1* dönüştürülecek dizisi sonu işaretçisi.

*next1* ilk Dönüştürülmeyen karaktere dönüştürülmüş sıralı ötesinde işaretçi.

*first2* işaretçiyi dönüştürülmüş sıralı başlangıcına.

*Soyadı2* dönüştürülmüş sıralı sonu işaretçisi.

*next2* işaretçisine `CharType` son dönüştürülen sonra gelen `CharType`, hedef dizideki ilk değiştirilmemiş karaktere.

### <a name="return-value"></a>Dönüş Değeri

Başarı, kısmi başarısı veya başarısızlığı işlemin gösterir döndürür. İşlev döndürür:

- `codecvt_base::error` Kaynak sırası olgu ise oluşturulmuş.

- `codecvt_base::noconv` herhangi bir dönüştürme işlevi uyguluyorsa.

- `codecvt_base::ok` Dönüştürme başarılı olursa.

- `codecvt_base::partial` yeterli kaynak olup olmadığını veya hedef dönüştürme başarılı olması için yeteri kadar büyük değil.

### <a name="remarks"></a>Açıklamalar

*Duru_m* yeni bir kaynak dizisi başına ilk dönüştürme durumunu temsil etmelidir. İşlev başarılı bir dönüştürme geçerli durumu yansıtacak şekilde depolanmış değerini değiştirir. Depolanan değerine, aksi takdirde belirtilmeyen olur.

### <a name="example"></a>Örnek

Örneğin bakın [içinde](#in), çağıran `do_in`.

## <a name="do_length"></a>  codecvt::do_length

Belirleyen bir sanal işlev kaç `Byte`dış verili dizisinin `Byte`iç belirli bir sayıdan daha fazla olmayan `CharType`s ve bu sayı kadar döndürür `Byte`s.

```cpp
virtual int do_length(
    const StateType& _State,
    const Byte* first1,
    const Byte* last1,
    size_t _Len2) const;
```

### <a name="parameters"></a>Parametreler

*Duru_m* üye işleve yapılan çağrılar arasındaki tutulan dönüştürme durumu.

*first1* başına dış dizisinin işaretçisi.

*last1* dış dizi sonu işaretçisi.

*_Len2* sayısı `Byte`üye işlevi tarafından döndürülen s.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürme, büyüktür sayısı sayısını temsil eden bir tamsayı *_Len2*dış kaynak sırası tarafından tanımlanan [ `first1`, `last1`).

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi etkili bir şekilde çağıran `do_in`( `_State`, `first1`, `last1`, `next1`, `_Buf`, `_Buf`  +  `_Len2`, `next2`) için*Duru_m* (durum kopyası), bazı arabellek `_Buf`, işaretçileri ve `next1`ve `next2`.

Ardından döndürür `next2`  -  `buf`. Bu nedenle, bu dönüştürme, büyüktür maksimum sayısını sayar *_Len2*kaynak sırası tarafından tanımlanan [ `first1`, `last1`).

Şablon sürümü her zaman küçük olanı döndürür *last1* - *first1* ve *_Len2*.

### <a name="example"></a>Örnek

Örneğin bakın [uzunluğu](#length), çağıran `do_length`.

## <a name="do_max_length"></a>  codecvt::do_max_length

Dış en fazla sayısını döndüren bir sanal işlev `Byte`s bir dahili üretmek için gerekli `CharType`.

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

En fazla `Byte`s oluşturmak gerekli `CharType`.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi tarafından döndürülen izin verilen en büyük değeri döndürür [do_length](#do_length)( `first1`, `last1`, 1) rastgele geçerli değerler için *first1* ve *last1*.

### <a name="example"></a>Örnek

Örneğin bakın [max_length](#max_length), çağıran `do_max_length`.

## <a name="do_out"></a>  codecvt::do_out

İç dönüştürmek için çağrılan sanal işlev `CharType`dizisini dış `Byte`s.

```cpp
virtual result do_out(
    StateType& _State,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*Duru_m* üye işleve yapılan çağrılar arasındaki tutulan dönüştürme durumu.

*first1* başına dönüştürülecek dizisinin işaretçisi.

*last1* dönüştürülecek dizisi sonu işaretçisi.

*next1* ilk işaretçi başvurusu dönüştürmeden `CharType`, son sonra `CharType` dönüştürülür.

*first2* işaretçiyi dönüştürülmüş sıralı başlangıcına.

*Soyadı2* dönüştürülmüş sıralı sonu işaretçisi.

*next2* ilk işaretçi başvurusu dönüştürmeden `Byte`, son sonra `Byte` dönüştürülür.

### <a name="return-value"></a>Dönüş Değeri

İşlev döndürür:

- `codecvt_base::error` Kaynak sırası olgu ise oluşturulmuş.

- `codecvt_base::noconv` herhangi bir dönüştürme işlevi uyguluyorsa.

- `codecvt_base::ok` Dönüştürme başarılı olursa.

- `codecvt_base::partial` yeterli kaynak olup olmadığını veya hedef dönüştürme başarılı olması için yeteri kadar büyük değil.

### <a name="remarks"></a>Açıklamalar

*Duru_m* yeni bir kaynak dizisi başına ilk dönüştürme durumunu temsil etmelidir. İşlev başarılı bir dönüştürme geçerli durumu yansıtacak şekilde depolanmış değerini değiştirir. Depolanan değerine, aksi takdirde belirtilmeyen olur.

### <a name="example"></a>Örnek

Örneğin bakın [kullanıma](#out), çağıran `do_out`.

## <a name="do_unshift"></a>  codecvt::do_unshift

Sağlamak için çağrılan sanal işlev `Byte`dizisindeki son karakteri tamamlamak için durum bağımlı bir dönüştürmede gereken `Byte`s.

```cpp
virtual result do_unshift(
    StateType& _State,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*Duru_m* üye işleve yapılan çağrılar arasındaki tutulan dönüştürme durumu.

*first2* hedef aralıktaki ilk konumu için işaretçi.

*Soyadı2* hedef aralıktaki son Konum işaretçisi.

*next2* hedef dizideki ilk değiştirilmemiş öğesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlev döndürür:

- `codecvt_base::error` _ *durumu* geçersiz bir durumu temsil eder

- `codecvt_base::noconv` herhangi bir dönüştürme işlevi uyguluyorsa

- `codecvt_base::ok` Dönüştürme başarılı olursa

- `codecvt_base::partial` Hedef dönüştürme başarılı olması için yeterince büyük değilse

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, kaynak öğesi a dönüştürmeyi dener `CharType`(0) içinde depolayan bir hedef dizisine [ `first2`, `last2`), sonlandıran öğe dışında `Byte`(0). Her zaman içinde depolar *next2* hedef dizideki ilk değiştirilmemiş öğeye bir işaretçi.

_ *Durumu* yeni bir kaynak dizisi başına ilk dönüştürme durumunu temsil etmelidir. İşlev başarılı bir dönüştürme geçerli durumu yansıtacak şekilde depolanmış değerini değiştirir. Genellikle, kaynak öğesi dönüştürme `CharType`(0) geçerli durumu ilk dönüştürme durumda bırakır.

### <a name="example"></a>Örnek

Örneğin bakın [unshift](#unshift), çağıran `do_unshift`.

## <a name="encoding"></a>  codecvt::Encoding

Olmadığını test eder, kodlama `Byte` akışının kodlamasının durum bağımlı olup olmadığını arasındaki oran `Byte`kullanılıp kullanılmayacağını ve `CharType`sabittir ve yanıt olumluysa, bu durumda, bu oran değerini belirler.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri pozitif sonra bu değeri sabit sayısıdır `Byte` üretmek için gereken karakter `CharType` karakter.

Korumalı sanal üye işlevi döndürür:

- -1, kodlama türü dönüştürülmelerini `extern_type` durumuna bağlıdır.

- 0, kodlama değişen uzunluktaki dizileri içeriyorsa.

- *N*, kodlama yalnızca dizilerinin uzunluğu içeriyorsa *n*

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_encoding](#do_encoding).

### <a name="example"></a>Örnek

```cpp
// codecvt_encoding.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
}
```

```Output
1
1
1
```

## <a name="extern_type"></a>  codecvt::extern_type

Dış temsiller için kullanılan karakter türü.

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Byte`.

## <a name="in"></a>  codecvt::in

Bir dizi bir dış temsilini dönüştürür `Byte`s, bir dizi bir iç temsiline `CharType`s.

```cpp
result in(
    StateType& _State,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Parametreler

*Duru_m* üye işleve yapılan çağrılar arasındaki tutulan dönüştürme durumu.

*first1* başına dönüştürülecek dizisinin işaretçisi.

*last1* dönüştürülecek dizisi sonu işaretçisi.

*next1* ötesinde dönüştürülmüş sıralı ilk Dönüştürülmeyen karaktere bir işaretçi.

*first2* işaretçiyi dönüştürülmüş sıralı başlangıcına.

*Soyadı2* dönüştürülmüş sıralı sonu işaretçisi.

*next2* işaretçisine `CharType` son dönüştürülen sonra gelen `Chartype` hedef dizideki ilk değiştirilmemiş karaktere.

### <a name="return-value"></a>Dönüş Değeri

Başarı, kısmi başarısı veya başarısızlığı işlemin gösterir döndürür. İşlev döndürür:

- `codecvt_base::error` Kaynak sırası olgu ise oluşturulmuş.

- `codecvt_base::noconv` herhangi bir dönüştürme işlevi uyguluyorsa.

- `codecvt_base::ok` Dönüştürme başarılı olursa.

- `codecvt_base::partial` yeterli kaynak olup olmadığını veya hedef dönüştürme başarılı olması için yeteri kadar büyük değil.

### <a name="remarks"></a>Açıklamalar

*Duru_m* yeni bir kaynak dizisi başına ilk dönüştürme durumunu temsil etmelidir. İşlevi, depolanan değerine gerektiğinde başarılı bir dönüştürme geçerli durumu yansıtacak şekilde değiştirir. Kısmi bir dönüştürme işleminin ardından *duru_m* dönüştürme yeni karakter geldiğinde sürdürmek için izin vermek için ayarlanması gerekir.

Üye işlevinin döndürdüğü [do_in](#do_in)( `_State`, _ *First1 last1, next1, First2, _Llast2, next2*).

### <a name="example"></a>Örnek

```cpp
// codecvt_in.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )
   << L"The converted string is:\n ["
   << &pwszInt[0]
   << L"]" << endl;
   exit(-1);
}
```

```Output
It worked! The converted string is:
 [This is the string to be converted!]
```

## <a name="intern_type"></a>  codecvt::intern_type

İç temsiller için kullanılan karakter türü.

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `CharType`.

## <a name="length"></a>  codecvt::length

Belirler kaç `Byte`dış verili dizisinin `Byte`iç belirli bir sayıdan daha fazla olmayan `CharType`s ve bu sayı kadar döndürür `Byte`s.

```cpp
int length(
    const StateType& _State,
    const Byte* first1,
    const Byte* last1,
    size_t _Len2) const;
```

### <a name="parameters"></a>Parametreler

*Duru_m* üye işleve yapılan çağrılar arasındaki tutulan dönüştürme durumu.

*first1* başına dış dizisinin işaretçisi.

*last1* dış dizi sonu işaretçisi.

*_Len2* üye işlevi tarafından döndürülen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürme, büyüktür sayısı sayısını temsil eden bir tamsayı *_Len2*dış kaynak sırası tarafından tanımlanan [ `first1`, `last1`).

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_length](#do_length)( *duru_m, first1*, `last1`, `_Len2`).

### <a name="example"></a>Örnek

```cpp
// codecvt_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << endl;
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="max_length"></a>  codecvt::max_length

Dış maksimum sayısını döndürür `Byte`s bir dahili üretmek için gerekli `CharType`.

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

En fazla `Byte`s oluşturmak gerekli `CharType`.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_max_length](#do_max_length).

### <a name="example"></a>Örnek

```cpp
// codecvt_max_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc( "C");//English_Britain" );//German_Germany
   int res = use_facet<codecvt<char, char, mbstate_t> >
     ( loc ).max_length( );
   wcout << res << endl;
}
```

```Output
1
```

## <a name="out"></a>  codecvt::out

İç dönüştürür `CharType`dizisini dış `Byte`s.

```cpp
result out(
    StateType& _State,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*Duru_m* üye işleve yapılan çağrılar arasındaki tutulan dönüştürme durumu.

*first1* başına dönüştürülecek dizisinin işaretçisi.

*last1* dönüştürülecek dizisi sonu işaretçisi.

*next1* ilk işaretçi başvurusu dönüştürmeden `CharType` en son `CharType` dönüştürülür.

*first2* işaretçiyi dönüştürülmüş sıralı başlangıcına.

*Soyadı2* dönüştürülmüş sıralı sonu işaretçisi.

*next2* ilk işaretçi başvurusu dönüştürmeden `Byte` son dönüştürülen sonra `Byte`.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevinin döndürdüğü [do_out](#do_out)( `_State`, `first1`, `last1`, `next1`, `first2`, `last2`, `next2`).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [codecvt::do_out](#do_out).

### <a name="example"></a>Örnek

```cpp
// codecvt_out.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
#include <wchar.h>
using namespace std;
#define LEN 90
int main( )
{
   char pszExt[LEN+1];
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );
   char* pszNext;
   const wchar_t* pwszNext;
   mbstate_t state;
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).out( state,
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );
   pszExt[wcslen( pwszInt )] = 0;
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )
   << "The converted string is:\n ["
   << &pszExt[0]
   << "]" << endl;
}
```

```Output
It worked: The converted string is:
 [This is the wchar_t string to be converted.]
```

## <a name="state_type"></a>  codecvt::state_type

İç ve dış temsiller arasındaki dönüştürmeler sırasında ara durumları temsil etmek için kullanılan bir karakter türü.

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `StateType`.

## <a name="unshift"></a>  codecvt::unshift

Sağlar `Byte`dizisindeki son karakteri tamamlamak için durum bağımlı bir dönüştürmede gereken `Byte`s.

```cpp
result unshift(
    StateType& _State,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*Duru_m* üye işleve yapılan çağrılar arasındaki tutulan dönüştürme durumu.

*first2* hedef aralıktaki ilk konumu için işaretçi.

*Soyadı2* hedef aralıktaki son Konum işaretçisi.

*next2* hedef dizideki ilk değiştirilmemiş öğesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlev döndürür:

- `codecvt_base::error` durum, geçersiz bir durumu temsil eder.

- `codecvt_base::noconv` herhangi bir dönüştürme işlevi uyguluyorsa.

- `codecvt_base::ok` Dönüştürme başarılı olursa.

- `codecvt_base::partial` Hedef dönüştürme başarılı olması için yeterince büyük değilse.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, kaynak öğesi a dönüştürmeyi dener `CharType`(0) içinde depolayan bir hedef dizisine [ `first2`, `last2`), sonlandıran öğe dışında `Byte`(0). Her zaman içinde depolar *next2* hedef dizideki ilk değiştirilmemiş öğeye bir işaretçi.

*Duru_m* yeni bir kaynak dizisi başına ilk dönüştürme durumunu temsil etmelidir. İşlevi, depolanan değerine gerektiğinde başarılı bir dönüştürme geçerli durumu yansıtacak şekilde değiştirir. Genellikle, kaynak öğesi dönüştürme `CharType`(0) geçerli durumu ilk dönüştürme durumda bırakır.

Üye işlevinin döndürdüğü [do_unshift](#do_unshift)( `_State`, `first2`, `last2`, `next2` ).

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[Kod Sayfaları](../c-runtime-library/code-pages.md)<br/>
[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
