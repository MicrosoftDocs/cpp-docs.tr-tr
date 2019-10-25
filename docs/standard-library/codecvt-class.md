---
title: codecvt Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 631c3b88be5e2a03798ff6d8e3fb200ad257a8d7
ms.sourcegitcommit: 4b0928a1a497648d0d327579c8262f25ed20d02e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72890182"
---
# <a name="codecvt-class"></a>codecvt Sınıfı

Bir yerel ayar modeli olarak kullanılabilecek bir nesneyi açıklayan bir sınıf şablonu. Programın içindeki karakterleri ve program dışındaki karakterleri kodlamak için kullanılan değerler dizisi arasındaki dönüştürmeleri denetleyebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>Parametreler

*CharType* \
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*Bayt* \
Bir program dışındaki karakterleri kodlamak için kullanılan bir tür.

*StateType* \
Karakter temsillerinin iç ve dış türleri arasındaki bir dönüştürmenin ara durumlarını temsil etmek için kullanılan bir tür.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, *CharType* türünde bir değer dizisi ve *byte*türünde bir değer dizisi arasındaki dönüşümleri denetlemek için bir [yerel ayar modeli](../standard-library/locale-class.md#facet_class)olarak kullanılabilecek bir nesneyi tanımlar. *StateType* sınıfı, dönüştürmeyi ve bir dönüştürme sırasında gerekli durum bilgilerini depolayan *StateType* sınıfının bir nesnesi.

İç kodlama karakter başına sabit sayıda bayt içeren bir temsili kullanır, genellikle **char** veya tür **wchar_t**yazın.

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne `id`, ilk depolanan bir sıfır değeri içerir. Depolanan değerine erişmek için yapılan ilk girişim `id` benzersiz bir pozitif değer depolar.

[Do_in](#do_in) ve [do_out](#do_out) şablon sürümleri her zaman `codecvt_base::noconv`döndürür.

Standart C++ kitaplık, çeşitli açık uzmanlık tanımlar:

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

**wchar_t** ve **char** dizileri arasında dönüştürür.

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

UTF-16 olarak kodlanan `char16_t` dizileri ve UTF-8 olarak kodlanmış **karakter** dizileri arasında dönüştürür.

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

UTF-32 (UCS-4) olarak kodlanmış `char32_t` dizileri ve UTF-8 olarak kodlanmış **karakter** dizileri arasında dönüştürür.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[codecvt](#codecvt)|Dönüşümleri işlemek için bir yerel ayar modeli olarak hizmet veren `codecvt` sınıfının nesneleri için Oluşturucu.|

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
|[do_encoding](#do_encoding)|`Byte` akışının kodlanması durum bağımlıysa test eden bir sanal işlev, kullanılan `Byte` değerleri ve üretilen `CharType` değerleri arasındaki oran sabittir ve varsa, bu oranın değerini belirler.|
|[do_in](#do_in)|İç `Byte` değerleri dizisini dış `CharType` değerleri dizisine dönüştürmek için çağrılan bir sanal işlev.|
|[do_length](#do_length)|Belirli bir dış `Byte` değerleri dizisinin kaç `Byte` değerinin verilen sayıda iç `CharType` değerden daha fazla olmadığını belirleyen ve bu sayıda `Byte` değeri döndüren bir sanal işlev.|
|[do_max_length](#do_max_length)|Bir iç `CharType` üretmek için gereken en fazla dış bayt sayısını döndüren bir sanal işlev.|
|[do_out](#do_out)|İç `CharType` değerlerini bir dizi dış bayt dizisine dönüştürmek için çağrılan bir sanal işlev.|
|[do_unshift](#do_unshift)|Bir `Byte` değerleri dizisindeki son karakteri tamamlamaya yönelik bir duruma bağlı dönüştürmeye gereken `Byte` değerlerini sağlamak için adlı bir sanal işlev.|
|[şifreleme](#encoding)|`Byte` akışının kodlamasının durum bağımlı olup olmadığını test eder, kullanılan `Byte` değerleri ve üretilen `CharType` değerleri arasındaki oran sabittir ve varsa, bu oranın değerini belirler.|
|[in](#in)|Bir `Byte` değerleri dizisinin dış temsilini bir `CharType` değerleri dizisinin iç gösterimine dönüştürür.|
|[uzunluklu](#length)|Belirli bir dış `Byte` değerleri dizisinin kaç `Byte` değerinin verilen sayıda iç `CharType` değerden daha fazla olmadığını ve bu sayıda `Byte` değeri döndürdüğünü belirler.|
|[max_length](#max_length)|Bir iç `CharType`üretmek için gereken en fazla dış `Byte` değer sayısını döndürür.|
|[out](#out)|İç `CharType` değerleri dizisini dış `Byte` değerleri dizisine dönüştürür.|
|[unshift](#unshift)|`Byte` değerlerinin dizisindeki son karakteri tamamlaması için duruma bağlı bir dönüşümde gereken dış `Byte` değerlerini sağlar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="always_noconv"></a>codecvt:: always_noconv

Hiçbir dönüştürmenin gerçekleştirilip oluşturulmayacağını sınar.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Hiçbir dönüştürmenin gerçekleştirilmesi gerekmiyorsa **true** olan bir Boolean değeri; en az bir tane yapılması gerekiyorsa **false** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_always_noconv](#do_always_noconv)döndürür.

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

## <a name="codecvt"></a>codecvt:: codecvt

Dönüştürmeleri işlemek için bir yerel ayar modeli olarak hizmet veren codecvt sınıfının nesneleri için Oluşturucu.

```cpp
explicit codecvt(size_t refs = 0);
```

### <a name="parameters"></a>Parametreler

*refs* \
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- 2: Bu değerler tanımlı değil.

Oluşturucu, `locale::facet` temel nesnesini [locale:: model](../standard-library/locale-class.md#facet_class)`(refs)`ile başlatır.

## <a name="do_always_noconv"></a>codecvt::d o_always_noconv

Hiçbir dönüştürmenin gerçekleştirilip oluşturulmayacağını test etmek için çağrılan bir sanal işlev.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi, yalnızca [do_in](#do_in) veya [do_out](#do_out) öğesine yapılan her çağrı `noconv`döndürürse **true** değerini döndürür.

Şablon sürümü her zaman **true**değerini döndürür.

### <a name="example"></a>Örnek

`do_always_noconv`çağıran [always_noconv](#always_noconv)için örneğe bakın.

## <a name="do_encoding"></a>codecvt::d o_encoding

`Byte` akışının kodlanması durum bağımlıysa test eden bir sanal işlev, kullanılan `Byte` değerleri ve üretilen `CharType` değerleri arasındaki oran sabittir ve varsa, bu oranın değerini belirler.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi şunu döndürür:

- -1, `extern_type` tür dizilerinin kodlaması durum bağımlıdır.

- 0, kodlama değişen uzunluklardan oluşan dizileri içeriyorsa.

- *N*, kodlama yalnızca uzunluk dizilerini içeriyorsa *n*

### <a name="example"></a>Örnek

`do_encoding`çağıran [kodlama](#encoding)örneğine bakın.

## <a name="do_in"></a>codecvt::d o_in

Dış `Byte` değerleri dizisini iç `CharType` değerleri dizisine dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual result do_in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Parametreler

*durum* \
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1* \
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*last1* \
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*next1* \
Dönüştürülmüş sıranın sonunun ötesinde, ilk Dönüştürülmeyen karaktere kadar olan işaretçi.

*first2* \
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*last2* \
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*next2* \
Son dönüştürülen `CharType` sonra gelen `CharType` işaretçisi, hedef dizideki ilk değiştirilmemiş karaktere.

### <a name="return-value"></a>Dönüş Değeri

İşlemin başarısını, kısmen başarısını veya başarısızlığını gösteren bir dönüş. İşlevi şunu döndürür:

- kaynak sırası hatalı biçimlendirilmişse `codecvt_base::error`.

- işlev dönüştürme işlemi gerçekleştirmediğini `codecvt_base::noconv`.

- dönüştürme başarılı olursa `codecvt_base::ok`.

- Kaynak yetersizse, dönüştürmenin başarılı olması için hedef yeterince büyük değilse `codecvt_base::partial`.

### <a name="remarks"></a>Açıklamalar

*durum* , yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, saklı değerini gereken şekilde değiştirir. Depolanan değeri aksi durumda belirtilmemiş olur.

### <a name="example"></a>Örnek

`do_in`çağıran [içindeki](#in)için örneğe bakın.

## <a name="do_length"></a>codecvt::d o_length

Belirli bir dış `Byte` değerleri dizisinin kaç `Byte` değerinin verilen sayıda iç `CharType` değerden daha fazla olmadığını belirleyen ve bu sayıda `Byte` değeri döndüren bir sanal işlev.

```cpp
virtual int do_length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>Parametreler

*durum* \
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1* \
Dış dizinin başlangıcına yönelik işaretçi.

*last1* \
Dış dizinin sonuna yönelik işaretçi.

*len2*\
Üye işlevi tarafından döndürülebilecek en fazla `Byte` değeri sayısı.

### <a name="return-value"></a>Dönüş Değeri

[`first1`, `last1`) konumundaki dış kaynak sırası tarafından *tanımlanan, en*fazla dönüştürme sayısının sayısını temsil eden bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, *durum* için `do_in( state, first1, last1, next1, buf, buf + len2, next2)` (durum kopyası), bazı arabellek `buf`ve `next1` ve `next2`işaretçiler için etkin bir şekilde çağırır.

Ardından `next2`  -  `buf` döndürür. Bu *nedenle, [* `first1`, `last1`) adresindeki kaynak sırası tarafından tanımlanan en fazla dönüştürme sayısını sayar.

Şablon sürümü her zaman *last1* - *first1* ve *len2*'in daha küçük olduğunu döndürür.

### <a name="example"></a>Örnek

`do_length`çağıran [length](#length)örneğine bakın.

## <a name="do_max_length"></a>codecvt::d o_max_length

Bir iç `CharType`oluşturmak için gereken en fazla dış `Byte` değer sayısını döndüren bir sanal işlev.

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CharType`üretmek için gereken en fazla `Byte` değeri sayısı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, *first1* ve *last1*'in rastgele geçerli değerleri için [do_length](#do_length)`( first1, last1, 1)` tarafından döndürülebilecek en büyük izin verilen değeri döndürür.

### <a name="example"></a>Örnek

`do_max_length`çağıran [max_length](#max_length)için örneğe bakın.

## <a name="do_out"></a>codecvt::d o_out

İç `CharType` değerleri dizisini dış `Byte` değerleri dizisine dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual result do_out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*durum* \
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1* \
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*last1* \
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*next1* \
Son `CharType` dönüştürüldükten sonra, Dönüştürülmeyen ilk `CharType` bir işaretçiye başvuru.

*first2* \
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*last2* \
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*next2* \
Son `Byte` dönüştürüldükten sonra, Dönüştürülmeyen ilk `Byte` bir işaretçiye başvuru.

### <a name="return-value"></a>Dönüş Değeri

İşlevi şunu döndürür:

- kaynak sırası hatalı biçimlendirilmişse `codecvt_base::error`.

- işlev dönüştürme işlemi gerçekleştirmediğini `codecvt_base::noconv`.

- dönüştürme başarılı olursa `codecvt_base::ok`.

- Kaynak yetersizse veya hedef dönüştürmenin başarılı olması için yeterince büyük değilse `codecvt_base::partial`.

### <a name="remarks"></a>Açıklamalar

*durum* , yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, saklı değerini gereken şekilde değiştirir. Depolanan değeri aksi durumda belirtilmemiş olur.

### <a name="example"></a>Örnek

`do_out`çağıran, [Out](#out)örneğine bakın.

## <a name="do_unshift"></a>codecvt::d o_unshift

Bir `Byte` değerleri dizisindeki son karakteri tamamlamaya yönelik bir duruma bağlı dönüştürmeye gereken `Byte` değerlerini sağlamak için adlı bir sanal işlev.

```cpp
virtual result do_unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*durum* \
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first2* \
Hedef aralıktaki ilk konuma yönelik işaretçi.

*last2* \
Hedef aralıktaki son konuma yönelik işaretçi.

*next2* \
Hedef dizideki ilk değiştirilmemiş öğenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlevi şunu döndürür:

- *durum* geçersiz bir durumu temsil ediyorsa `codecvt_base::error`

- işlev dönüştürme işlemi gerçekleştirmediğini `codecvt_base::noconv`

- dönüştürme başarılı olursa `codecvt_base::ok`

- hedef dönüştürmenin başarılı olması için yeterince büyük değilse `codecvt_base::partial`

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, `CharType`(0) kaynak öğeyi, Sonlandırıcı öğe `Byte`(0) dışında, [`first2`, `last2`) içinde depoladığı bir hedef diziye dönüştürmeye çalışır. Her zaman, hedef dizideki ilk değiştirilmemiş öğe için *Next2* a işaretçisini depolar.

_ *State* , yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, saklı değerini gereken şekilde değiştirir. Genellikle, kaynak öğe `CharType` dönüştürülürken (0) ilk dönüştürme durumunda geçerli durum kalır.

### <a name="example"></a>Örnek

`do_unshift`çağıran [unshift](#unshift)için örneğe bakın.

## <a name="encoding"></a>codecvt:: Encoding

`Byte` akışının kodlamasının durum bağımlı olup olmadığını test eder, kullanılan `Byte` değerleri ve üretilen `CharType` değerleri arasındaki oran sabittir ve varsa, bu oranın değerini belirler.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri pozitif ise, bu değer `CharType` karakteri üretmek için gereken `Byte` karakterlerin sabit sayısıdır.

Korumalı sanal üye işlevi şunu döndürür:

- -1, `extern_type` tür dizilerinin kodlaması durum bağımlıdır.

- 0, kodlama değişen uzunluklardan oluşan dizileri içeriyorsa.

- *N*, kodlama yalnızca N uzunluklu dizileri içeriyorsa *.*

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_encoding](#do_encoding)döndürür.

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

## <a name="extern_type"></a>codecvt:: extern_type

Dış temsiller için kullanılan karakter türü.

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `Byte` şablon parametresi için bir eş anlamlı.

## <a name="in"></a>codecvt:: ın

Bir `Byte` değerleri dizisinin dış temsilini bir `CharType` değerleri dizisinin iç gösterimine dönüştürür.

```cpp
result in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Parametreler

*durum* \
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1* \
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*last1* \
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*next1* \
Dönüştürülmüş sıranın sonundaki işaretçiyi, ilk Dönüştürülmeyen karaktere kadar olan işaretçi.

*first2* \
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*last2* \
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*next2* \
Son dönüştürüldükten sonra gelen `CharType` işaretçisi, hedef dizideki ilk değiştirilmemiş karaktere `Chartype`.

### <a name="return-value"></a>Dönüş Değeri

İşlemin başarısını, kısmen başarısını veya başarısızlığını gösteren bir dönüş. İşlevi şunu döndürür:

- kaynak sırası hatalı biçimlendirilmişse `codecvt_base::error`.

- işlev dönüştürme işlemi gerçekleştirmediğini `codecvt_base::noconv`.

- dönüştürme başarılı olursa `codecvt_base::ok`.

- Kaynak yetersizse veya hedef dönüştürmenin başarılı olması için yeterince büyük değilse `codecvt_base::partial`.

### <a name="remarks"></a>Açıklamalar

*durum* , yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, gerektiği gibi saklı değerini değiştirir. Kısmi dönüştürmeden sonra, yeni karakter geldiğinde dönüştürmenin sürdürülmesine izin vermek için *durum* ayarlanmalıdır.

Üye işlevi [do_in](#do_in)`( state, first1,  last1,  next1, first2, last2,  next2)`döndürür.

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

## <a name="intern_type"></a>codecvt:: intern_type

İç temsiller için kullanılan karakter türü.

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `CharType` şablon parametresi için bir eş anlamlı.

## <a name="length"></a>codecvt:: length

Belirli bir dış `Byte` değerleri dizisinin kaç `Byte` değerinin verilen sayıda iç `CharType` değerden daha fazla olmadığını ve bu sayıda `Byte` değeri döndürdüğünü belirler.

```cpp
int length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>Parametreler

*durum* \
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1* \
Dış dizinin başlangıcına yönelik işaretçi.

*last1* \
Dış dizinin sonuna yönelik işaretçi.

*len2*\
Üye işlevi tarafından döndürülebilecek en fazla bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

[`first1`, `last1`) konumundaki dış kaynak sırası tarafından *tanımlanan, en*fazla dönüştürme sayısının sayısını temsil eden bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_length](#do_length)`( state, first1, last1, len2)`döndürür.

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

## <a name="max_length"></a>codecvt:: max_length

Bir iç `CharType`üretmek için gereken en fazla dış `Byte` değer sayısını döndürür.

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CharType`üretmek için gereken en fazla `Byte` değeri sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_max_length](#do_max_length)döndürür.

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

## <a name="out"></a>codecvt:: Out

İç `CharType` değerleri dizisini dış `Byte` değerleri dizisine dönüştürür.

```cpp
result out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*durum* \
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1* \
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*last1* \
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*next1* \
Son `CharType` dönüştürüldükten sonra Dönüştürülmeyen ilk `CharType` işaretçisine başvuru.

*first2* \
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*last2* \
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*next2* \
Son dönüştürülen `Byte` sonra Dönüştürülmeyen ilk `Byte` işaretçisine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi [do_out](#do_out)`( state, first1, last1, next1, first2, last2, next2)`döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [codecvt::d o_out](#do_out).

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

## <a name="state_type"></a>codecvt:: state_type

İç ve dış temsiller arasındaki dönüştürmeler sırasında ara durumları temsil etmek için kullanılan bir karakter türü.

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `StateType` şablon parametresi için bir eş anlamlı.

## <a name="unshift"></a>codecvt:: unshift

Bir `Byte` değerleri dizisindeki son karakteri tamamlamaya yönelik duruma bağlı bir dönüştürmede gereken `Byte` değerlerini sağlar.

```cpp
result unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*durum* \
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first2* \
Hedef aralıktaki ilk konuma yönelik işaretçi.

*last2* \
Hedef aralıktaki son konuma yönelik işaretçi.

*next2* \
Hedef dizideki ilk değiştirilmemiş öğenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlevi şunu döndürür:

- durum geçersiz bir durum gösteriyorsa `codecvt_base::error`.

- işlev dönüştürme işlemi gerçekleştirmediğini `codecvt_base::noconv`.

- dönüştürme başarılı olursa `codecvt_base::ok`.

- hedef dönüştürmenin başarılı olması için yeterince büyük değilse `codecvt_base::partial`.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, `CharType`(0) kaynak öğeyi, Sonlandırıcı öğe `Byte`(0) dışında, [`first2`, `last2`) içinde depoladığı bir hedef diziye dönüştürmeye çalışır. Her zaman, hedef dizideki ilk değiştirilmemiş öğe için *Next2* a işaretçisini depolar.

*durum* , yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, gerektiği gibi saklı değerini değiştirir. Genellikle, kaynak öğe `CharType` dönüştürülürken (0) ilk dönüştürme durumunda geçerli durum kalır.

Üye işlevi [do_unshift](#do_unshift)`( state, first2, last2, next2 )`döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<locale >](../standard-library/locale.md) \
[Kod sayfaları](../c-runtime-library/code-pages.md) \
[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md) \
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
