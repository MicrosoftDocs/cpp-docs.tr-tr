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
ms.openlocfilehash: 936b3ab63b454e8f7e0490c2d155356a7c3b240f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459829"
---
# <a name="codecvt-class"></a>codecvt Sınıfı

Bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı. Programın içindeki karakterleri ve program dışındaki karakterleri kodlamak için kullanılan değerler dizisi arasındaki dönüştürmeleri denetleyebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*Bayt*\
Bir program dışındaki karakterleri kodlamak için kullanılan bir tür.

*StateType*\
Karakter temsillerinin iç ve dış türleri arasındaki bir dönüştürmenin ara durumlarını temsil etmek için kullanılan bir tür.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, *CharType* türünde bir değer dizisi ve *byte*türünde bir değer dizisi arasındaki dönüşümleri denetlemek için bir [yerel ayar modeli](../standard-library/locale-class.md#facet_class)olarak kullanılabilecek bir nesneyi tanımlar. *StateType* sınıfı, dönüştürmeyi ve bir dönüştürme sırasında gerekli durum bilgilerini depolayan *StateType* sınıfının bir nesnesi.

İç kodlama karakter başına sabit sayıda bayt içeren bir temsili kullanır, genellikle **char** veya tür **wchar_t**yazın.

Herhangi bir yerel ayar modelinde olduğu gibi, statik `id` nesne, ilk depolanan bir sıfır değeri içerir. Depolanan değerine erişmek için yapılan ilk girişim, içinde `id`benzersiz bir pozitif değer depolar.

[Do_in](#do_in) ve [do_out](#do_out) şablon sürümleri her zaman döndürülür `codecvt_base::noconv`.

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

UTF- `char16_t` 16 olarak kodlanan diziler ve UTF-8 olarak kodlanmış **karakter** dizileri arasında dönüştürür.

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

UTF- `char32_t` 32 (UCS-4) olarak kodlanmış sıralar ve UTF-8 olarak kodlanmış **karakter** dizileri arasında dönüştürür.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[codecvt](#codecvt)|Dönüştürmeleri işlemek için bir yerel ayar `codecvt` modeli olarak hizmet veren sınıfının nesneleri için Oluşturucu.|

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
|[do_encoding](#do_encoding)|`Byte` Akışın kodlanması durum bağımlıysa test eden, kullanılan ve `CharType`üretilen s `Byte`arasındaki oranın sabit olup olmadığı, bu oranın değerini belirleyen sanal bir işlev.|
|[do_in](#do_in)|Dahili `Byte`bir dizisini dış `CharType`s dizisine dönüştürmek için çağrılan bir sanal işlev.|
|[do_length](#do_length)|Belirli bir dış `Byte`dizi dizisinin kaç tane `Byte`için belirtilen sayıda iç `CharType`iş olduğunu belirleyen ve bu sayıda `Byte`s döndüren bir sanal işlev.|
|[do_max_length](#do_max_length)|Bir iç `CharType`oluşturmak için gereken en fazla dış bayt sayısını döndüren bir sanal işlev.|
|[do_out](#do_out)|Dahili `CharType`bir dizisini dış baytların dizisine dönüştürmek için çağrılan bir sanal işlev.|
|[do_unshift](#do_unshift)|Bir, `Byte`bir `Byte`dizi içindeki son karakteri tamamlamaya yönelik duruma bağlı bir dönüşümde gereken öğeleri sağlamak için adlı bir sanal işlev.|
|[şifreleme](#encoding)|`Byte` Akış kodlamasının durum bağımlıysa, kullanılan ve `CharType`üretilen s `Byte`arasındaki oranın sabit olup olmadığı, bu oranın değerini belirler.|
|[in](#in)|Bir dizi öğesinin dış temsilini `Byte`bir `CharType`dizi iç gösterimine dönüştürür.|
|[length](#length)|Belirli bir dış `Byte` `Byte`dizi dizisinin kaç tane için verilen sayıda iç `CharType`iş olduğunu belirler ve bu sayıda `Byte`s döndürür.|
|[max_length](#max_length)|Bir iç `Byte` `CharType`oluşturmak için gereken en fazla dış dizi sayısını döndürür.|
|[out](#out)|Dahili `CharType`bir dizisini dış `Byte`s dizisine dönüştürür.|
|[unshift](#unshift)|`Byte` ,`Byte`S dizisindeki son karakteri tamamlamaya yönelik duruma bağlı bir dönüşümde gereken dış öğeleri sağlar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="always_noconv"></a>codecvt:: always_noconv

Bir dönüştürme yapılıp yapılmayacağını sınar.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir dönüştürme yapılması gerekmiyorsa **true** olan bir Boolean değeri; **false** , en az bir işlem yapılması gerekiyor.

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
explicit codecvt(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: Nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- 2: Bu değerler tanımlı değil.

Oluşturucu kendi `locale::facet` temel nesnesini **locale::** [model](../standard-library/locale-class.md#facet_class)(`_Refs`) ile başlatır.

## <a name="do_always_noconv"></a>codecvt::d o_always_noconv

Hiçbir dönüştürme yapılması gerekip gerekmediğini sınamak için çağrılan bir sanal işlev.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi yalnızca `noconv` [do_in](#do_in) veya [do_out](#do_out) için her çağrı döndürülürse **true** değerini döndürür.

Şablon sürümü her zaman **true**değerini döndürür.

### <a name="example"></a>Örnek

Çağıran`do_always_noconv` [always_noconv](#always_noconv)için örneğe bakın.

## <a name="do_encoding"></a>codecvt::d o_encoding

`Byte` Akış kodlamasının durum bağımlı olup olmadığını test eden sanal bir işlev, kullanılan ve `CharType`üretilen s `Byte`arasındaki oran sabittir ve ise bu oranın değerini belirler.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi şunu döndürür:

- -1, tür `extern_type` dizilerinin kodlaması durum bağımlıdır.

- 0, kodlama değişen uzunluklardan oluşan dizileri içeriyorsa.

- *N*, kodlama yalnızca uzunluk dizilerini içeriyorsa *n*

### <a name="example"></a>Örnek

Çağıran`do_encoding` [kodlamaya](#encoding)yönelik örneğe bakın.

## <a name="do_in"></a>codecvt::d o_in

Bir dış `Byte`öğeleri dizisini iç `CharType`s dizisine dönüştürmek için çağrılan bir sanal işlev.

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

*_Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1*\
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*last1*\
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*next1*\
Dönüştürülmüş sıranın sonunun ötesinde, ilk Dönüştürülmeyen karaktere kadar olan işaretçi.

*first2*\
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*last2*\
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*next2*\
`CharType` Son dönüştürüldükten`CharType`sonra gelen işaretçisi, hedef dizideki ilk değiştirilmemiş karaktere.

### <a name="return-value"></a>Dönüş Değeri

İşlemin başarısını, kısmen başarısını veya başarısızlığını gösteren bir dönüş. İşlevi şunu döndürür:

- `codecvt_base::error`kaynak sırası hatalı biçimlendirilmişse.

- `codecvt_base::noconv`işlev dönüştürme işlemi gerçekleştirmeyebilir.

- `codecvt_base::ok`dönüştürme başarılı olursa.

- `codecvt_base::partial`Kaynak yetersizse veya hedef yeterince büyük değilse dönüştürmenin başarılı olması için.

### <a name="remarks"></a>Açıklamalar

*_State* , yeni bir kaynak dizisinin başındaki ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, saklı değerini gereken şekilde değiştirir. Depolanan değeri aksi durumda belirtilmemiş olur.

### <a name="example"></a>Örnek

İçindeki`do_in`için örneğe bakın [](#in).

## <a name="do_length"></a>codecvt::d o_length

Belirli bir dış `Byte`dizi dizisinin kaç tane `Byte`için belirtilen sayıda iç `CharType`iş olduğunu belirleyen ve bu sayıda `Byte`s döndüren bir sanal işlev.

```cpp
virtual int do_length(
    const StateType& _State,
    const Byte* first1,
    const Byte* last1,
    size_t _Len2) const;
```

### <a name="parameters"></a>Parametreler

*_Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1*\
Dış dizinin başlangıcına yönelik işaretçi.

*last1*\
Dış dizinin sonuna yönelik işaretçi.

*_Len2*\
Üye işlevi tarafından döndürülebilecek en fazla `Byte`s sayısı.

### <a name="return-value"></a>Dönüş Değeri

[`first1` ,`last1`) Konumundaki dış kaynak sırası tarafından tanımlanan, en fazla dönüştürme sayısı olan *_Len2*' den büyük bir sayıyı temsil eden bir tamsayı.

### <a name="remarks"></a>Açıklamalar

`do_in`Korumalı sanal üye işlevi _ için ( ,`next1`,,, `_Buf` ,,`next2`)etkin bir şekilde çağırır `_Len2` `_Buf` `first1` `_State` `last1`  +   *Durum* (durum kopyası), bazı arabellek `_Buf`ve işaretçiler `next1`ve `next2`.

Ardından döndürür `next2`.  -  `buf` Bu nedenle, [ `first1`, `last1`) adresindeki kaynak sırası tarafından tanımlanan, *_Len2*' den büyük değil en fazla dönüştürme sayısını sayar.

Şablon sürümü her zaman *last1* - *first1* ve *_Len2*' den daha küçük bir değer döndürür.

### <a name="example"></a>Örnek

Çağıran`do_length` [length](#length)örneğine bakın.

## <a name="do_max_length"></a>codecvt::d o_max_length

Bir iç `Byte` `CharType`oluşturmak için gereken en fazla dış dizi sayısını döndüren bir sanal işlev.

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tane `Byte` `CharType`oluşturmak için gereken en fazla sayı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, *first1* ve *last1*'in rastgele geçerli değerleri için [do_length](#do_length)( `first1`, `last1`, 1) tarafından döndürülebilecek en büyük izin verilen değeri döndürür.

### <a name="example"></a>Örnek

Çağıran`do_max_length` [max_length](#max_length)için örneğe bakın.

## <a name="do_out"></a>codecvt::d o_out

Dahili `CharType`bir dizisini dış `Byte`s dizisine dönüştürmek için çağrılan bir sanal işlev.

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

*_Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1*\
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*last1*\
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*next1*\
`CharType` Son`CharType` dönüştürüldükten sonra, ilk Dönüştürülmeyen bir işaretçiye yönelik başvuru.

*first2*\
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*last2*\
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*next2*\
`Byte` Son`Byte` dönüştürüldükten sonra, ilk Dönüştürülmeyen bir işaretçiye yönelik başvuru.

### <a name="return-value"></a>Dönüş Değeri

İşlevi şunu döndürür:

- `codecvt_base::error`kaynak sırası hatalı biçimlendirilmişse.

- `codecvt_base::noconv`işlev dönüştürme işlemi gerçekleştirmeyebilir.

- `codecvt_base::ok`dönüştürme başarılı olursa.

- `codecvt_base::partial`Kaynak yetersizse veya hedef dönüştürmenin başarılı olması için yeterince büyük değilse.

### <a name="remarks"></a>Açıklamalar

*_State* , yeni bir kaynak dizisinin başındaki ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, saklı değerini gereken şekilde değiştirir. Depolanan değeri aksi durumda belirtilmemiş olur.

### <a name="example"></a>Örnek

[İçin örneğe](#out)bakın ve çağırır `do_out`.

## <a name="do_unshift"></a>codecvt::d o_unshift

Bir, `Byte`bir `Byte`dizi içindeki son karakteri tamamlamaya yönelik duruma bağlı bir dönüşümde gereken öğeleri sağlamak için adlı bir sanal işlev.

```cpp
virtual result do_unshift(
    StateType& _State,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*_Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first2*\
Hedef aralıktaki ilk konuma yönelik işaretçi.

*last2*\
Hedef aralıktaki son konuma yönelik işaretçi.

*next2*\
Hedef dizideki ilk değiştirilmemiş öğenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlevi şunu döndürür:

- `codecvt_base::error`_ *durumu* geçersiz bir durumu temsil ediyorsa

- `codecvt_base::noconv`işlev dönüştürme işlemi gerçekleştirmeyebilir

- `codecvt_base::ok`dönüştürme başarılı olursa

- `codecvt_base::partial`hedef dönüştürmenin başarılı olması için yeterince büyük değilse

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, `CharType`sonlandırma öğesi `Byte`(0) dışında, kaynak öğeyi (0), [ `first2`, `last2`) içinde depoladığı bir hedef diziye dönüştürmeye çalışır. Her zaman, hedef dizideki ilk değiştirilmemiş öğe için *Next2* a işaretçisini depolar.

_ *State* , yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, saklı değerini gereken şekilde değiştirir. Genellikle, kaynak öğeyi `CharType`(0) dönüştürmek, ilk dönüştürme durumunda geçerli durumu bırakır.

### <a name="example"></a>Örnek

Öğesini çağıran `do_unshift` [unshift](#unshift)için örneğe bakın.

## <a name="encoding"></a>codecvt:: Encoding

`Byte` Akış kodlamasının durum bağımlıysa, kullanılan ve `CharType`üretilen s `Byte`arasındaki oranın sabit olup olmadığı, bu oranın değerini belirler.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri pozitif ise, bu değer `Byte` `CharType` karakter üretmek için gereken sabit karakter sayısıdır.

Korumalı sanal üye işlevi şunu döndürür:

- -1, tür `extern_type` dizilerinin kodlaması durum bağımlıdır.

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

Tür, şablon parametresi `Byte`için bir eş anlamlı.

## <a name="in"></a>codecvt:: ın

Bir dizi öğesinin dış temsilini `Byte`bir `CharType`dizi iç gösterimine dönüştürür.

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

*_Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1*\
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*last1*\
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*next1*\
Dönüştürülmüş sıranın sonundaki işaretçiyi, ilk Dönüştürülmeyen karaktere kadar olan işaretçi.

*first2*\
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*last2*\
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*next2*\
Hedef dizideki ilk değiştirilmemiş karaktere son dönüştürüldükten `Chartype` sonra gelen işaretçisi. `CharType`

### <a name="return-value"></a>Dönüş Değeri

İşlemin başarısını, kısmen başarısını veya başarısızlığını gösteren bir dönüş. İşlevi şunu döndürür:

- `codecvt_base::error`kaynak sırası hatalı biçimlendirilmişse.

- `codecvt_base::noconv`işlev dönüştürme işlemi gerçekleştirmeyebilir.

- `codecvt_base::ok`dönüştürme başarılı olursa.

- `codecvt_base::partial`Kaynak yetersizse veya hedef dönüştürmenin başarılı olması için yeterince büyük değilse.

### <a name="remarks"></a>Açıklamalar

*_State* , yeni bir kaynak dizisinin başındaki ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, gerektiği gibi saklı değerini değiştirir. Kısmi dönüştürmeden sonra, yeni karakter geldiğinde dönüştürmenin sürdürülmesine izin vermek için *_State* ayarlanmalıdır.

Üye işlevi [do_in](#do_in)( `_State`, _ *first1, last1, next1, First2, _Llast2, Next2*) döndürür.

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

Tür, şablon parametresi `CharType`için bir eş anlamlı.

## <a name="length"></a>codecvt:: length

Belirli bir dış `Byte` `Byte`dizi dizisinin kaç tane için verilen sayıda iç `CharType`iş olduğunu belirler ve bu sayıda `Byte`s döndürür.

```cpp
int length(
    const StateType& _State,
    const Byte* first1,
    const Byte* last1,
    size_t _Len2) const;
```

### <a name="parameters"></a>Parametreler

*_Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1*\
Dış dizinin başlangıcına yönelik işaretçi.

*last1*\
Dış dizinin sonuna yönelik işaretçi.

*_Len2*\
Üye işlevi tarafından döndürülebilecek en fazla bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

[`first1` ,`last1`) Konumundaki dış kaynak sırası tarafından tanımlanan, en fazla dönüştürme sayısı olan *_Len2*' den büyük bir sayıyı temsil eden bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_length](#do_length)döndürür ( *_State, first1*, `last1`, `_Len2`).

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

Bir iç `Byte` `CharType`oluşturmak için gereken en fazla dış dizi sayısını döndürür.

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tane `Byte` `CharType`oluşturmak için gereken en fazla sayı.

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

Dahili `CharType`bir dizisini dış `Byte`s dizisine dönüştürür.

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

*_Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first1*\
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*last1*\
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*next1*\
`CharType` Son`CharType` dönüştürüldükten sonra ilk Dönüştürülmeyen işaretçiye olan başvuru.

*first2*\
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*last2*\
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*next2*\
Son dönüştürüldükten `Byte` `Byte`sonra ilk Dönüştürülmeyen işaretçiye olan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi [do_out](#do_out) `_State`döndürür ( `last1` `first1` ,`next1`,,,, ,`next2`). `last2` `first2`

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

Tür, şablon parametresi `StateType`için bir eş anlamlı.

## <a name="unshift"></a>codecvt:: unshift

, `Byte` S`Byte`dizisindeki son karakteri tamamlamaya yönelik duruma bağlı bir dönüşümde gereken öğeleri sağlar.

```cpp
result unshift(
    StateType& _State,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*_Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*first2*\
Hedef aralıktaki ilk konuma yönelik işaretçi.

*last2*\
Hedef aralıktaki son konuma yönelik işaretçi.

*next2*\
Hedef dizideki ilk değiştirilmemiş öğenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlevi şunu döndürür:

- `codecvt_base::error`durum, geçersiz bir durumu temsil ediyorsa.

- `codecvt_base::noconv`işlev dönüştürme işlemi gerçekleştirmeyebilir.

- `codecvt_base::ok`dönüştürme başarılı olursa.

- `codecvt_base::partial`hedef dönüştürmenin başarılı olması için yeterince büyük değilse.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, `CharType`sonlandırma öğesi `Byte`(0) dışında, kaynak öğeyi (0), [ `first2`, `last2`) içinde depoladığı bir hedef diziye dönüştürmeye çalışır. Her zaman, hedef dizideki ilk değiştirilmemiş öğe için *Next2* a işaretçisini depolar.

*_State* , yeni bir kaynak dizisinin başındaki ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, gerektiği gibi saklı değerini değiştirir. Genellikle, kaynak öğeyi `CharType`(0) dönüştürmek, ilk dönüştürme durumunda geçerli durumu bırakır.

Üye işlevi [do_unshift](#do_unshift)döndürür `_State`(, `first2` `last2` ,,).`next2`

## <a name="see-also"></a>Ayrıca bkz.

[\<Yerel ayar >](../standard-library/locale.md)\
[Kod sayfaları](../c-runtime-library/code-pages.md)\
[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
