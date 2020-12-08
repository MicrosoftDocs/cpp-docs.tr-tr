---
title: '**`CStringT`** Sınıfı'
description: Microsoft ATL sınıfı için API başvurusu **`CStringT`**
ms.date: 12/06/2020
f1_keywords:
- CStringT
- CSTRINGT/ATL::CStringT
- CSTRINGT/ATL::CStringT::CStringT
- CSTRINGT/ATL::CStringT::AllocSysString
- CSTRINGT/ATL::CStringT::AnsiToOem
- CSTRINGT/ATL::CStringT::AppendFormat
- CSTRINGT/ATL::CStringT::Collate
- CSTRINGT/ATL::CStringT::CollateNoCase
- CSTRINGT/ATL::CStringT::Compare
- CSTRINGT/ATL::CStringT::CompareNoCase
- CSTRINGT/ATL::CStringT::Delete
- CSTRINGT/ATL::CStringT::Find
- CSTRINGT/ATL::CStringT::FindOneOf
- CSTRINGT/ATL::CStringT::Format
- CSTRINGT/ATL::CStringT::FormatMessage
- CSTRINGT/ATL::CStringT::FormatMessageV
- CSTRINGT/ATL::CStringT::FormatV
- CSTRINGT/ATL::CStringT::GetEnvironmentVariable
- CSTRINGT/ATL::CStringT::Insert
- CSTRINGT/ATL::CStringT::Left
- CSTRINGT/ATL::CStringT::LoadString
- CSTRINGT/ATL::CStringT::MakeLower
- CSTRINGT/ATL::CStringT::MakeReverse
- CSTRINGT/ATL::CStringT::MakeUpper
- CSTRINGT/ATL::CStringT::Mid
- CSTRINGT/ATL::CStringT::OemToAnsi
- CSTRINGT/ATL::CStringT::Remove
- CSTRINGT/ATL::CStringT::Replace
- CSTRINGT/ATL::CStringT::ReverseFind
- CSTRINGT/ATL::CStringT::Right
- CSTRINGT/ATL::CStringT::SetSysString
- CSTRINGT/ATL::CStringT::SpanExcluding
- CSTRINGT/ATL::CStringT::SpanIncluding
- CSTRINGT/ATL::CStringT::Tokenize
- CSTRINGT/ATL::CStringT::Trim
- CSTRINGT/ATL::CStringT::TrimLeft
- CSTRINGT/ATL::CStringT::TrimRight
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.openlocfilehash: f9ec5c02aa1ed9377a38d30d9a4152af5e164d58
ms.sourcegitcommit: 7b131db4ed39bddb4a456ebea402f47c5cbd69d3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2020
ms.locfileid: "96776550"
---
# <a name="cstringt-class"></a>`CStringT` Sınıfı

Bu sınıf bir nesneyi temsil eder **`CStringT`** .

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>Parametreler

*`BaseType`*\
Dize sınıfının karakter türü. Aşağıdakilerden biri olabilir:

- **`char`** (ANSI karakter dizeleri için).

- **`wchar_t`** (Unicode karakter dizeleri için).

- **`TCHAR`** (hem ANSI hem de Unicode karakter dizeleri için).

*`StringTraits`*\
Dize sınıfının C Run-Time (CRT) kitaplık desteğinin gerekip gerekmediğini ve dize kaynaklarının nerede olduğunu belirler. Aşağıdakilerden biri olabilir:

- **`StrTraitATL<wchar_t | char | TCHAR, ChTraitsCRT<wchar_t | char | TCHAR>>`**

   Sınıfı, CRT desteğinin yanı sıra `m_hInstResource` (uygulamanın modül sınıfının bir üyesi) tarafından belirtilen modüldeki kaynak dizeleri aramalarını gerektirir.

- **`StrTraitATL<wchar_t | char | TCHAR, ChTraitsOS<wchar_t | char |TCHAR>>`**

   Sınıfı, `m_hInstResource` (uygulamanın modül sınıfının bir üyesi) tarafından belirtilen MODÜLDE CRT desteği ve arama gerektirmez.

- **`StrTraitMFC<wchar_t | char | TCHAR, ChTraitsCRT<wchar_t | char | TCHAR>>`**

   Sınıfı CRT desteği gerektirir ve standart MFC arama algoritmasını kullanarak kaynak dizeleri arar.

- **`StrTraitMFC<wchar_t | char | TCHAR, ChTraitsOS<wchar_t | char | TCHAR>>`**

   Sınıfı, standart MFC arama algoritmasını kullanarak CRT desteği gerektirmez ve kaynak dizeleri arar.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[`CStringT::CStringT`](#cstringt)|**`CStringT`** Çeşitli yollarla bir nesne oluşturur.|
|[`CStringT::~CStringT`](#_dtorcstringt)|Bir nesneyi yok eder **`CStringT`** .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[`CStringT::AllocSysString`](#allocsysstring)|Verilerden bir `BSTR` ayırır **`CStringT`** .|
|[`CStringT::AnsiToOem`](#ansitooem)|ANSI karakter kümesinden OEM karakter kümesine yerinde dönüştürme yapar.|
|[`CStringT::AppendFormat`](#appendformat)|Biçimlendirilen verileri varolan bir nesneye ekler **`CStringT`** .|
|[`CStringT::Collate`](#collate)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarlı, yerel ayara özgü bilgileri kullanır).|
|[`CStringT::CollateNoCase`](#collatenocase)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarsız, yerel ayara özgü bilgileri kullanır).|
|[`CStringT::Compare`](#compare)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarlı).|
|[`CStringT::CompareNoCase`](#comparenocase)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarsız).|
|[`CStringT::Delete`](#delete)|Dizeden bir karakter veya karakter siler.|
|[`CStringT::Find`](#find)|Daha büyük bir dizenin içinde bir karakter veya alt dize bulur.|
|[`CStringT::FindOneOf`](#findoneof)|Bir kümeden ilk eşleşen karakteri bulur.|
|[`CStringT::Format`](#format)|Dizeyi olduğu gibi biçimlendirir `sprintf` .|
|[`CStringT::FormatMessage`](#formatmessage)|Bir ileti dizesini biçimlendirir.|
|[`CStringT::FormatMessageV`](#formatmessagev)|Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.|
|[`CStringT::FormatV`](#formatv)|Dizeyi değişken bir bağımsız değişken listesi kullanarak biçimlendirir.|
|[`CStringT::GetEnvironmentVariable`](#getenvironmentvariable)|Dizeyi belirtilen ortam değişkeninin değerine ayarlar.|
|[`CStringT::Insert`](#insert)|Dize içindeki verilen dizine tek bir karakter veya alt dize ekler.|
|[`CStringT::Left`](#left)|Bir dizenin sol kısmını ayıklar.|
|[`CStringT::LoadString`](#loadstring)|**`CStringT`** Bir Windows kaynağından varolan bir nesneyi yükler.|
|[`CStringT::MakeLower`](#makelower)|Bu dizedeki tüm karakterleri küçük harfe dönüştürür.|
|[`CStringT::MakeReverse`](#makereverse)|Dizeyi tersine çevirir.|
|[`CStringT::MakeUpper`](#makeupper)|Bu dizedeki tüm karakterleri büyük harfli karakterlere dönüştürür.|
|[`CStringT::Mid`](#mid)|Bir dizenin orta kısmını ayıklar.|
|[`CStringT::OemToAnsi`](#oemtoansi)|OEM karakter kümesinden ANSI karakter kümesine yerinde dönüştürme yapar.|
|[`CStringT::Remove`](#remove)|Bir dizeden belirtilen karakterleri kaldırır.|
|[`CStringT::Replace`](#replace)|Belirtilen karakterleri diğer karakterlerle değiştirir.|
|[`CStringT::ReverseFind`](#reversefind)|Daha büyük bir dizenin içinde bir karakter bulur; uçtan başlar.|
|[`CStringT::Right`](#right)|Bir dizenin sağ kısmını ayıklar.|
|[`CStringT::SetSysString`](#setsysstring)|Varolan bir `BSTR` nesneyi nesnesinden alınan verilerle ayarlar **`CStringT`** .|
|[`CStringT::SpanExcluding`](#spanexcluding)|Tarafından tanımlanan karakter kümesinde olmayan, ilk karakterle başlayarak dizeden karakter ayıklar `pszCharSet` .|
|[`CStringT::SpanIncluding`](#spanincluding)|Yalnızca bir küme içindeki karakterleri içeren bir alt dize ayıklar.|
|[`CStringT::Tokenize`](#tokenize)|Belirtilen belirteçleri bir hedef dizede ayıklar.|
|[`CStringT::Trim`](#trim)|Dizedeki tüm baştaki ve sondaki boşluk karakterlerini kırpar.|
|[`CStringT::TrimLeft`](#trimleft)|Dizeden öndeki boşluk karakterlerini kırpar.|
|[`CStringT::TrimRight`](#trimright)|Dizeden sondaki boşluk karakterlerini kırpar.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[`CStringT::operator =`](#operator_eq)|Nesnesine yeni bir değer atar **`CStringT`** .|
|[`CStringT::operator +`](#operator_add)|İki dizeyi veya bir karakteri ve dizeyi art arda ekler.|
|[`CStringT::operator +=`](#operator_add_eq)|Varolan bir dizenin sonuna yeni bir dize ekler.|
|[`CStringT::operator ==`](#operator_eq_eq)|İki dizenin mantıksal olarak eşit olup olmadığını belirler.|
|[`CStringT::operator !=`](#operator_neq)|İki dizenin mantıksal olarak eşit olup olmadığını belirler.|
|[`CStringT::operator <`](#operator_lt)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha az olup olmadığını belirler.|
|[`CStringT::operator >`](#operator_gt)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha büyük olup olmadığını belirler.|
|[`CStringT::operator <=`](#operator_lt_eq)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden küçük veya ona eşit olup olmadığını belirler.|
|[`CStringT::operator >=`](#operator_gt_eq)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden büyük veya ona eşit olup olmadığını belirler.|

## <a name="remarks"></a>Açıklamalar

**`CStringT`**[CSimpleStringT sınıfından](../../atl-mfc-shared/reference/csimplestringt-class.md)devralır. Karakter işleme, sıralama ve arama gibi gelişmiş özellikler tarafından uygulanır **`CStringT`** .

> [!NOTE]
> **`CStringT`** nesneler özel durum atma özelliğine sahiptir. Bu **`CStringT`** , herhangi bir nedenle bir nesne bellekten tükenmediğinde oluşur.

Bir **`CStringT`** nesne, değişken uzunlukta karakterlerden oluşur. **`CStringT`** Temel olarak benzer sözdizimini kullanarak işlevleri ve işleçleri sağlar. Birleştirme ve karşılaştırma işleçleri, Basitleştirilmiş bellek yönetimiyle birlikte **`CStringT`** nesnelerin sıradan karakter dizileri kullanmaktan daha kolay kullanılmasını sağlar.

> [!NOTE]
> Gömülü null karakterler içeren örnekler oluşturmak mümkün olsa da **`CStringT`** , bunun için önerilir. Katıştırılmış null karakterler içeren nesnelerde Yöntemler ve işleçler çağırma **`CStringT`** istenmeden sonuçlar verebilir.

Ve parametrelerinin farklı birleşimlerini kullanarak `BaseType` nesneler, `StringTraits` **`CStringT`** ATL kitaplıkları tarafından önceden tanımlanmış olan aşağıdaki türlerde gelebilir.

Bir ATL uygulamasında kullanıyorsanız:

`CString`, `CStringA` ve, `CStringW` MFC DLL 'den (MFC90.DLL) aktarılmış, hiçbir koşulda Kullanıcı dll 'lerinden aktarılmalıdır. Bu, **`CStringT`** birden çok kez tanımlanmasını engellemek için yapılır.

> [!NOTE]
> Kodunuz [CStringT kullanarak dize sınıflarını dışarı aktarma](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md)bölümünde açıklanan bağlayıcı hatalarının geçici çözümünü içeriyorsa, bu kodu kaldırmalısınız. Artık buna ihtiyacınız yoktur.

Aşağıdaki dize türleri MFC tabanlı uygulamalar içinde kullanılabilir:

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CStringA`|CRT desteği olan bir ANSI karakter türü dizesi.|
|`CStringW`|CRT desteği olan bir Unicode karakter türü dizesi.|
|`CString`|Yalnızca CRT desteğiyle birlikte ANSI ve Unicode karakter türleri.|

Aşağıdaki dize türleri, tanımlanan projelerde mevcuttur `ATL_CSTRING_NO_CRT` :

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CAtlStringA`|CRT desteği olmayan bir ANSI karakter türü dizesi.|
|`CAtlStringW`|CRT desteği olmayan bir Unicode karakter türü dizesi.|
|`CAtlString`|CRT desteği olmayan ANSI ve Unicode karakter türleri.|

Tanımlı olmayan projelerde aşağıdaki dize türleri mevcuttur `ATL_CSTRING_NO_CRT` :

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CAtlStringA`|CRT desteği olan bir ANSI karakter türü dizesi.|
|`CAtlStringW`|CRT desteği olan bir Unicode karakter türü dizesi.|
|`CAtlString`|Yalnızca CRT desteğiyle birlikte ANSI ve Unicode karakter türleri.|

`CString` nesneler aşağıdaki özelliklere de sahiptir:

- **`CStringT`** birleştirme işlemleri nedeniyle nesneler büyüyebilir.

- **`CStringT`** nesneler "değer semantiğini" izler. Bir nesneyi bir **`CStringT`** dizenin işaretçisi olarak değil, gerçek bir dize olarak düşünün.

- **`CStringT`** İşlev bağımsız değişkenleri için ücretsiz olarak nesneleri kullanabilirsiniz `PCXSTR` .

- Dize arabellekleri için özel bellek yönetimi. Daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="cstringt-predefined-types"></a>CStringT önceden tanımlanmış türler

, **`CStringT`** Desteklenen karakter türünü ( [wchar_t](../../c-runtime-library/standard-types.md) veya [char](../../c-runtime-library/standard-types.md)) tanımlamak için bir şablon bağımsız değişkeni kullandığından, yöntem parametresi türleri her zaman karmaşık olabilir. Bu sorunu basitleştirmek için, bir dizi önceden tanımlanmış tür tanımlanmıştır ve sınıf boyunca kullanılır **`CStringT`** . Aşağıdaki tabloda çeşitli türler listelenmektedir:

|Ad|Açıklama|
|----------|-----------------|
|`XCHAR`|**`wchar_t`** Nesneyle aynı karakter türünde tek bir karakter (ya da **`char`** ) **`CStringT`** .|
|`YCHAR`|**`wchar_t`** **`char`** Nesneyle aynı karakter türüne sahip tek bir karakter (ya da) **`CStringT`** .|
|`PXSTR`|* * * * * * * * **`wchar_t`** **`char`** Nesnesi ile aynı karakter türüne sahip bir karakter dizesinin (ya da) bir işaretçisi `CStringT` .|
|`PYSTR`|**`wchar_t`** **`char`** Nesneyle aynı karakter türüne sahip bir karakter dizesinin (ya da ya da) bir işaretçisi **`CStringT`** .|
|`PCXSTR`|**`const`** **`wchar_t`** **`char`** Nesneyle aynı karakter türüne sahip bir karakter dizesinin (ya da) işaretçisi **`CStringT`** .|
|`PCYSTR`|**`const`** **`wchar_t`** **`char`** Nesneyle aynı karakter türüne sahip bir karakter dizesinin (ya da ya da) bir işaretçisi **`CStringT`** .|

> [!NOTE]
> Daha önce belgelenmemiş yöntemlerin (örneğin,) kullanıldığı kodun, `CString` `AssignCopy` aşağıdaki belgelenmiş Yöntemleri (veya gibi) kullanan kodla değiştirilmelidir **`CStringT`** `GetBuffer` `ReleaseBuffer` . Bu yöntemler öğesinden devralınır `CSimpleStringT` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)

**`CStringT`**

## <a name="requirements"></a>Gereksinimler

|Üst bilgi|Şunun için kullanın:|
|------------|-------------|
|CStringT. h|Yalnızca MFC dize nesneleri|
|atlstr. h|MFC olmayan dize nesneleri|

## <a name="cstringtallocsysstring"></a><a name="allocsysstring"></a> `CStringT::AllocSysString`

Türünde bir Otomasyon uyumlu dize ayırır `BSTR` ve **`CStringT`** nesnenin içeriğini, Sonlandırıcı null karakteri de dahil olmak üzere kopyalar.

```cpp
BSTR AllocSysString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan dize.

### <a name="remarks"></a>Açıklamalar

MFC programlarında, yetersiz bellek varsa bir [CMemoryException sınıfı](../../mfc/reference/cmemoryexception-class.md) oluşturulur. ATL programlarında bir [CAtlException](../../atl/reference/catlexception-class.md) atılır. Bu işlev, genellikle otomasyon için dizeler döndürmek üzere kullanılır.

Genellikle, bu dize bir COM işlevine parametre olarak geçiriltiyse `[in]` , bu, çağıranın dizeyi serbest bırakma yapılmasını gerektirir. Bu, Windows SDK açıklandığı gibi [SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)kullanılarak yapılabilir. Daha fazla bilgi için bkz. [BIR BSTR Için bellek ayırma ve serbest bırakma](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).

Windows 'daki OLE ayırma işlevleri hakkında daha fazla bilgi için Windows SDK [SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) bölümüne bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CStringT::AllocSysString` .

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

## <a name="cstringtansitooem"></a><a name="ansitooem"></a> `CStringT::AnsiToOem`

Bu nesnedeki tüm karakterleri **`CStringT`** ANSI karakter KÜMESINDEN OEM karakter kümesine dönüştürür.

```cpp
void AnsiToOem();
```

### <a name="remarks"></a>Açıklamalar

Tanımlanmış ise işlev kullanılamaz `_UNICODE` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

## <a name="cstringtappendformat"></a><a name="appendformat"></a> `CStringT::AppendFormat`

Biçimlendirilen verileri varolan bir nesneye ekler **`CStringT`** .

```cpp
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>Parametreler

*`pszFormat`*\
Biçim denetimi dizesi.

*`nFormatID`*\
Biçim denetimi dizesini içeren dize kaynak tanımlayıcısı.

*`argument`*\
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

Bu işlev, içinde bir dizi karakter ve değer biçimlendirir ve ekler **`CStringT`** . Her bir isteğe bağlı bağımsız değişken (varsa) dönüştürülür ve tarafından tanımlanan dize kaynağından karşılık gelen biçim belirtimine göre eklenir *`pszFormat`* *`nFormatID`* .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

## <a name="cstringtcollate"></a><a name="collate"></a> `CStringT::Collate`

Genel metin işlevini kullanarak iki dizeyi karşılaştırır `_tcscoll` .

```cpp
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*`psz`*\
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, bu **`CStringT`** nesne daha küçükse 0 < *`psz`* veya bu nesne daha büyükse 0 > **`CStringT`** *`psz`* .

### <a name="remarks"></a>Açıklamalar

`_tcscoll`TCHAR içinde tanımlanan genel metin işlevi. H, `strcoll` `wcscoll` `_mbscoll` derleme zamanında tanımlanan karakter kümesine bağlı olarak, ya da ile eşlenir. Her işlev, şu anda kullanılan kod sayfasına göre dizelerin büyük/küçük harfe duyarlı bir karşılaştırmasını yapar. Daha fazla bilgi için bkz. [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

## <a name="cstringtcollatenocase"></a><a name="collatenocase"></a> `CStringT::CollateNoCase`

Genel metin işlevini kullanarak iki dizeyi karşılaştırır `_tcscoll` .

```cpp
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*`psz`*\
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır (büyük/küçük harf yok sayılıyor) <, bu **`CStringT`** nesne küçüktür *`psz`* (büyük/küçük harf yok sayılıyor) veya bu nesne daha büyükse 0 > **`CStringT`** *`psz`* (büyük/küçük harf yok sayılıyor).

### <a name="remarks"></a>Açıklamalar

`_tcscoll`TCHAR içinde tanımlanan genel metin işlevi. H, `stricoll` `wcsicoll` `_mbsicoll` derleme zamanında tanımlanan karakter kümesine bağlı olarak, ya da ile eşlenir. Her işlev, kullanılmakta olan kod sayfasına göre dizelerin büyük/küçük harf duyarsız bir karşılaştırmasını yapar. Daha fazla bilgi için bkz. [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

## <a name="cstringtcompare"></a><a name="compare"></a> `CStringT::Compare`

İki dizeyi karşılaştırır (büyük/küçük harfe duyarlı).

```cpp
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>Parametreler

*`psz`*\
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, bu **`CStringT`** nesne daha küçükse 0 < *`psz`* veya bu nesne daha büyükse 0 > **`CStringT`** *`psz`* .

### <a name="remarks"></a>Açıklamalar

`_tcscmp`TCHAR içinde tanımlanan genel metin işlevi. H, `strcmp` `wcscmp` `_mbscmp` derleme zamanında tanımlanan karakter kümesine bağlı olarak, ya da ile eşlenir. Her işlev, dizelerin büyük küçük harfe duyarlı bir karşılaştırmasını yapar ve yerel ayarından etkilenmez. Daha fazla bilgi için bkz. [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).

Dize gömülü null değerler içeriyorsa, karşılaştırma amaçları doğrultusunda dizenin ilk gömülü null karakterde kesilme olarak kabul edilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CStringT::Compare` .

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

## <a name="cstringtcomparenocase"></a><a name="comparenocase"></a> `CStringT::CompareNoCase`

İki dizeyi karşılaştırır (büyük/küçük harfe duyarsız).

```cpp
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*`psz`*\
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır (büyük/küçük harf yok sayılıyor) <, bu **`CStringT`** nesne küçüktür *`psz`* (büyük/küçük harf yok sayılıyor) veya bu nesne daha büyükse 0 >**`CStringT`** *`psz`* (büyük/küçük harf yok sayılıyor).

### <a name="remarks"></a>Açıklamalar

`_tcsicmp`TCHAR içinde tanımlanan genel metin işlevi. H, `_stricmp` `_wcsicmp` `_mbsicmp` derleme zamanında tanımlanan karakter kümesine bağlı olarak ya da veya ile eşlenir. Her işlev, dizelerin büyük/küçük harf duyarsız bir karşılaştırmasını yapar. Karşılaştırma, yerel ayarın LC_CTYPE göre değişir ancak LC_COLLATE. Daha fazla bilgi için bkz. [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

## <a name="cstringtcstringt"></a><a name="cstringt"></a> `CStringT::CStringT`

Bir **`CStringT`** nesnesi oluşturur.

```cpp
CStringT() throw() :
    CThisSimpleString(StringTraits::GetDefaultManager());

explicit CStringT(IAtlStringMgr* pStringMgr) throw() :
    CThisSimpleString( pStringMgr);

CStringT(const VARIANT& varSrc);

CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);

CStringT(const CStringT& strSrc) :
    CThisSimpleString( strSrc);

operator CSimpleStringT<
                    BaseType,
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()

template <bool bMFCDLL>
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :
    CThisSimpleString( strSrc);

template <class SystemString>
CStringT(SystemString^ pString) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength) :
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());

CStringT(const YCHAR* pch, int nLength) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :
    CThisSimpleString( pch, nLength, pStringMgr);

CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);
```

### <a name="parameters"></a>Parametreler

*`pch`*\
Null ile Sonlandırılmamış, *nLength* uzunluklu bir karakter dizisine yönelik bir işaretçi.

*`nLength`*\
*PCH* içindeki karakter sayısının sayısı.

*`ch`*\
Tek bir karakter.

*`pszSrc`*\
Bu nesneye kopyalanacak null ile sonlandırılmış bir dize **`CStringT`** .

*`pStringMgr`*\
Nesne için bellek Yöneticisi işaretçisi **`CStringT`** . Ve için bellek yönetimi hakkında daha fazla bilgi için `IAtlStringMgr` **`CStringT`** bkz. [CStringT ile bellek yönetimi](../../atl-mfc-shared/memory-management-with-cstringt.md).

*`strSrc`*\
**`CStringT`** Bu nesneye Kopyalanacak varolan bir nesne **`CStringT`** . Ve hakkında daha fazla bilgi için `CThisString` `CThisSimpleString` , açıklamalar bölümüne bakın.

*`varSrc`*\
Bu nesneye kopyalanacak bir değişken nesne **`CStringT`** .

*`BaseType`*\
Dize sınıfının karakter türü. Aşağıdakilerden biri olabilir:

**`char`** (ANSI karakter dizeleri için).

**`wchar_t`** (Unicode karakter dizeleri için).

`TCHAR` (hem ANSI hem de Unicode karakter dizeleri için).

*`bMFCDLL`*\
Projenin bir MFC DLL () olup olmadığını belirten Boole değeri () `TRUE` `FALSE` .

*`SystemString`*\
Olmalıdır `System::String` ve projenin ile derlenmesi gerekir `/clr` .

*`pString`*\
Bir nesne için tanıtıcı **`CStringT`** .

### <a name="remarks"></a>Açıklamalar

Oluşturucular giriş verilerini yeni ayrılmış depolama alanına kopyalayacağından, bellek özel durumları oluşabilir. Bu oluşturuculardan bazıları dönüştürme işlevleri olarak davranır. Bu, örneğin, bir **`LPTSTR`** nesnenin beklenildiği bir konumu değiştirmenize olanak sağlar **`CStringT`** .

- **`CStringT`**( `LPCSTR` `lpsz` ): Bir **`CStringT`** ANSI dizesinden Unicode oluşturur. Bu oluşturucuyu, aşağıdaki örnekte gösterildiği gibi bir dize kaynağını yüklemek için de kullanabilirsiniz.

- `CStringT(``LPCWSTR` `lpsz` ): Bir **`CStringT`** Unicode dizesinden bir oluşturur.

- **`CStringT`**( `const unsigned char*` `psz` ): Bir **`CStringT`** işaretçisinden için bir işaretçisi oluşturmanıza izin verir **`unsigned char`** .

> [!NOTE]
> `_CSTRING_DISABLE_NARROW_WIDE_CONVERSION`ANSI ve Unicode dizeleri arasında örtük dize dönüştürmeyi devre dışı bırakmak için makroyu tanımlayın. Makro, dönüştürmeyi destekleyen derleme oluşturucularından hariç tutar.

*`strSrc`* Parametresi bir ya da nesnesi olabilir **`CStringT`** `CThisSimpleString` . İçin **`CStringT`** , varsayılan örneklerinden birini ( `CString` , `CStringA` , veya) kullanın `CStringW` ; için `CThisSimpleString` bir **`this`** işaretçi kullanın. `CThisSimpleString` sınıfından daha az yerleşik işlevselliğe sahip daha küçük bir dize sınıfı olan [CSimpleStringT sınıfının](../../atl-mfc-shared/reference/csimplestringt-class.md)bir örneğini bildirir **`CStringT`** .

Aşırı yükleme işleci bir `CSimpleStringT<>&()` **`CStringT`** bildirimden bir nesne oluşturur `CSimpleStringT` .

> [!NOTE]
> Gömülü null karakterler içeren örnekler oluşturmak mümkün olsa da **`CStringT`** , bunun için önerilir. Katıştırılmış null karakterler içeren nesnelerde Yöntemler ve işleçler çağırma **`CStringT`** istenmeden sonuçlar verebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

## <a name="cstringtcstringt"></a><a name="_dtorcstringt"></a> `CStringT::~CStringT`

Nesneyi yok eder **`CStringT`** .

```cpp
~CStringT() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok eder **`CStringT`** .

## <a name="cstringtdelete"></a><a name="delete"></a> `CStringT::Delete`

Verilen dizindeki karakterle başlayan bir dizeden bir karakter veya karakter siler.

```cpp
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>Parametreler

*`iIndex`*\
Silinecek nesnedeki ilk karakterin sıfır tabanlı dizini **`CStringT`** .

*`nCount`*\
Kaldırılacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen dizenin uzunluğu.

### <a name="remarks"></a>Açıklamalar

*`nCount`* Dizeden daha uzunsa, dizenin geri kalanı kaldırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

## <a name="cstringtfind"></a><a name="find"></a> `CStringT::Find`

Bu dizeyi bir karakter veya alt dizenin ilk eşleşmesi için arar.

```cpp
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>Parametreler

*`pszSub`*\
Aranacak alt dize.

*`iStart`*\
Aramaya başlamak için dizedeki karakterin dizini veya baştan başlamak için 0.

*`ch`*\
Aranacak tek bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Bu **`CStringT`** nesnedeki, istenen alt dize veya karakter bulunmazsa,-1 ile eşleşen ilk karakterin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

İşlev, hem tek karakterleri (çalışma zamanı işlevine benzer şekilde) hem de `strchr` dizeleri (şuna benzer şekilde) kabul etmek için aşırı yüklenmiştir `strstr` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

## <a name="cstringtfindoneof"></a><a name="findoneof"></a> `CStringT::FindOneOf`

Bu dizeyi, içinde yer alan herhangi bir karakterle eşleşen ilk karakter için arar *`pszCharSet`* .

```cpp
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>Parametreler

*`pszCharSet`*\
Eşleştirme için karakter içeren dize.

### <a name="return-value"></a>Dönüş Değeri

Bu dizedeki ' de bulunan ilk karakterin sıfır tabanlı dizini *`pszCharSet`* ; eşleşme yoksa-1.

### <a name="remarks"></a>Açıklamalar

İçindeki herhangi bir karakterin ilk oluşumunu bulur *`pszCharSet`* .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

## <a name="cstringtformat"></a><a name="format"></a> `CStringT::Format`

Biçimli verileri **`CStringT`** , [Sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) verileri C stili karakter dizisine biçimlendiren aynı şekilde yazar.

```cpp
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>Parametreler

*`nFormatID`*\
Biçim denetimi dizesini içeren dize kaynak tanımlayıcısı.

*`pszFormat`*\
Biçim denetimi dizesi.

*`argument`*\
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

Bu işlev, içindeki bir dizi karakter ve değeri biçimlendirir ve depolar **`CStringT`** . Her bir isteğe bağlı bağımsız değişken (varsa), *`pszFormat`* veya tarafından tanımlanan dize kaynağından karşılık gelen biçim belirtimine göre dönüştürülür ve çıktı *`nFormatID`* .

Dize nesnesinin kendisi için bir parametre olarak sunulursa çağrı başarısız olur `Format` . Örneğin, aşağıdaki kod öngörülemeyen sonuçlara neden olur:

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

Daha fazla bilgi için bkz. [Biçim belirtimi sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

## <a name="cstringtformatmessage"></a><a name="formatmessage"></a> `CStringT::FormatMessage`

Bir ileti dizesini biçimlendirir.

```cpp
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>Parametreler

*`nFormatID`*\
Biçimlendirilmemiş ileti metnini içeren dize kaynak tanımlayıcısı.

*`pszFormat`*\
Biçim denetimi dizesini işaret eder. Bu, ekleme ve biçimlendirme için taranır. Biçim dizesi, parametrelerin rastgele bir sıraya eklenmesine izin verdiğinden, çalışma zamanı işlevine *printf* stili biçim dizelerine benzer.

*`argument`*\
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

İşlev, giriş olarak bir ileti tanımı gerektirir. İleti tanımı tarafından *`pszFormat`* tanımlanan dize kaynağından veya tarafından belirlenir *`nFormatID`* . İşlevi, **`CStringT`** istenen katıştırılmış ekleme dizilerini işlemek için, biçimli ileti metnini nesnesine kopyalar.

> [!NOTE]
> `FormatMessage` Yeni biçimlendirilen dize için sistem belleği ayırmaya çalışır. Bu deneme başarısız olursa, otomatik olarak bir bellek özel durumu oluşturulur.

Her ekleme veya parametresinden sonra karşılık gelen bir parametreye sahip olmalıdır *`pszFormat`* *`nFormatID`* . İleti metni içinde, iletiyi dinamik olarak biçimlendirmek için birkaç kaçış dizisi desteklenir. Daha fazla bilgi için Windows SDK Windows [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) işlevine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

## <a name="cstringtformatmessagev"></a><a name="formatmessagev"></a> `CStringT::FormatMessageV`

Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.

```cpp
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>Parametreler

*`pszFormat`*\
Biçim denetimi dizesini işaret eder. Bu, ekleme ve biçimlendirme için taranır. Biçim dizesi, `printf` parametrelerin rastgele bir sıraya eklenmesine izin verdiği sürece, çalışma zamanı işlev stili biçim dizelerine benzerdir.

*`pArgList`*\
Bağımsız değişken listesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

İşlevi, girdi olarak, tarafından belirlendiği şekilde bir ileti tanımı gerektirir *`pszFormat`* . İşlevi, **`CStringT`** istenen katıştırılmış ekleme dizilerini işlemek için biçimli ileti metnini ve bağımsız değişkenlerin değişken listesini nesnesine kopyalar.

> [!NOTE]
> `FormatMessageV` Yeni biçimlendirilen dize için sistem belleği ayırmayı deneyen [CStringT:: FormatMessage](#formatmessage)' ı çağırır. Bu deneme başarısız olursa, otomatik olarak bir bellek özel durumu oluşturulur.

Daha fazla bilgi için Windows SDK Windows [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) işlevine bakın.

## <a name="cstringtformatv"></a><a name="formatv"></a> `CStringT::FormatV`

Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.

```cpp
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>Parametreler

*`pszFormat`*\
Biçim denetimi dizesini işaret eder. Bu, ekleme ve biçimlendirme için taranır. Biçim dizesi, `printf` parametrelerin rastgele bir sıraya eklenmesine izin verdiği sürece, çalışma zamanı işlev stili biçim dizelerine benzerdir.

*`args`*\
Bağımsız değişken listesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Biçimli bir dize ve bağımsız değişkenlerin değişken listesini **`CStringT`** , `vsprintf_s` verileri C stili karakter dizisine biçimlendiren şekilde biçimlendirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

## <a name="cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a> `CStringT::GetEnvironmentVariable`

Dizeyi belirtilen ortam değişkeninin değerine ayarlar.

```cpp
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>Parametreler

*`pszVar`*\
Ortam değişkenini belirten, null ile sonlandırılmış bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çağıran işlemin ortam bloğundan belirtilen değişkenin değerini alır. Değer, null ile sonlandırılmış bir karakter dizesi biçiminde olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

## <a name="cstringtinsert"></a><a name="insert"></a> `CStringT::Insert`

Dize içindeki verilen dizine tek bir karakter veya alt dize ekler.

```cpp
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>Parametreler

*`iIndex`*\
Ekleme gerçekleşmeden önceki karakterin dizini.

*`psz`*\
Eklenecek alt dizeye yönelik bir işaretçi.

*`ch`*\
Eklenecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen dizenin uzunluğu.

### <a name="remarks"></a>Açıklamalar

*`iIndex`* Parametresi, karakter veya alt dize için yer açmak üzere taşınacak ilk karakteri tanımlar. *NIndex* sıfırsa, ekleme dizenin tamamının önüne gelir. *NIndex* dizenin uzunluğundan daha yüksekse, işlev mevcut dizeyi ve ya da tarafından belirtilen yeni malzemeyi birleştirir *`ch`* *`psz`* .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

## <a name="cstringtleft"></a><a name="left"></a> `CStringT::Left`

*`nCount`* Bu nesneden en soldaki karakterleri ayıklar **`CStringT`** ve ayıklanan alt dizenin bir kopyasını döndürür.

```cpp
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>Parametreler

*`nCount`*\
Bu nesneden Ayıklanacak karakter sayısı **`CStringT`** .

### <a name="return-value"></a>Dönüş Değeri

**`CStringT`** Belirtilen karakter aralığının bir kopyasını içeren nesne. Döndürülen **`CStringT`** nesne boş olabilir.

### <a name="remarks"></a>Açıklamalar

*`nCount`* Dize uzunluğunu aşarsa, tüm dize ayıklanır. `Left` , temel `Left` işleve benzerdir.

Çok baytlı karakter kümeleri (MBCS) için *`nCount`* her 8 bit sırayı bir karakter olarak değerlendirir, böylece *`nCount`* çok baytlık karakterlerin sayısını iki ile çarpılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

## <a name="cstringtloadstring"></a><a name="loadstring"></a> `CStringT::LoadString`

*NID* tarafından tanımlanan bir Windows dize kaynağını varolan bir **`CStringT`** nesneye okur.

```cpp
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>Parametreler

*`hInstance`*\
Modülün örneğine yönelik bir tanıtıcı.

*`nID`*\
Bir Windows dize kaynak KIMLIĞI.

*`wLanguageID`*\
Dize kaynağının dili.

### <a name="return-value"></a>Dönüş Değeri

Kaynak yükü başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen dil (*wLanguage*) kullanarak belirtilen modülden (*HINSTANCE*) dize kaynağını (*NID*) yükler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

## <a name="cstringtmakelower"></a><a name="makelower"></a> `CStringT::MakeLower`

**`CStringT`** Nesneyi küçük harfli bir dizeye dönüştürür.

```cpp
CStringT& MakeLower();
```

### <a name="return-value"></a>Dönüş Değeri

Elde edilen küçük harfli dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

## <a name="cstringtmakereverse"></a><a name="makereverse"></a> `CStringT::MakeReverse`

Nesnedeki karakterlerin sırasını tersine çevirir **`CStringT`** .

```cpp
CStringT& MakeReverse();
```

### <a name="return-value"></a>Dönüş Değeri

Elde edilen ters dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

## <a name="cstringtmakeupper"></a><a name="makeupper"></a> `CStringT::MakeUpper`

**`CStringT`** Nesneyi büyük bir dizeye dönüştürür.

```cpp
CStringT& MakeUpper();
```

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan büyük dize.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

## <a name="cstringtmid"></a><a name="mid"></a> `CStringT::Mid`

*`nCount`* Bu nesneden, length karakter alt dizesini **`CStringT`** konumdan başlayarak kümeden ayıklar *`iFirst`* (sıfır tabanlı).

```cpp
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>Parametreler

*`iFirst`*\
Bu **`CStringT`** nesnedeki, ayıklanan alt dizeye dahil edilecek ilk karakterin sıfır tabanlı dizini.

*`nCount`*\
Bu nesneden Ayıklanacak karakter sayısı **`CStringT`** . Bu parametre sağlanmazsa, dizenin geri kalanı ayıklanır.

### <a name="return-value"></a>Dönüş Değeri

**`CStringT`** Belirtilen karakter aralığının bir kopyasını içeren nesne. Döndürülen **`CStringT`** nesne boş olabilir.

### <a name="remarks"></a>Açıklamalar

İşlevi ayıklanan alt dizenin bir kopyasını döndürür. `Mid` , temel PARÇAAL işlevine benzerdir (temel olan dizinler tek tabanlı olur hariç).

Çok baytlı karakter kümeleri (MBCS) için *`nCount`* her 8 bit karaktere başvurur; diğer bir deyişle, bir çok baytlı karakter içindeki bir lider ve sondaki bayt iki karakter olarak sayılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

## <a name="cstringtoemtoansi"></a><a name="oemtoansi"></a> `CStringT::OemToAnsi`

Bu nesnedeki tüm karakterleri **`CStringT`** OEM karakter KÜMESINDEN ANSI karakter kümesine dönüştürür.

```cppcpp
void OemToAnsi();
```

### <a name="remarks"></a>Açıklamalar

Tanımlandıysa, bu işlev kullanılamaz `_UNICODE` .

### <a name="example"></a>Örnek

[CStringT:: Ansıtooem](#ansitooem)örneğine bakın.

## <a name="cstringtoperator-"></a><a name="operator_eq"></a> `CStringT::operator =`

Dizeye yeni bir değer atar.

```cpp
CStringT& operator=(const CStringT& strSrc);

template<bool bMFCDLL>
CStringT& operator=(const CSimpleStringT<BaseType, bMFCDLL>& str);
CStringT& operator=(PCXSTR pszSrc);
CStringT& operator=(PCYSTR pszSrc);
CStringT& operator=(const unsigned char* pszSrc);
CStringT& operator=(XCHAR ch);
CStringT& operator=(YCHAR ch);
CStringT& operator=(const VARIANT& var);
```

### <a name="parameters"></a>Parametreler

*`strSrc`*\
**`CStringT`** Bu dizeye atanacak bir.

*`str`*\
Bir `CThisSimpleString` nesneye başvuru.

*`bMFCDLL`*\
Projenin bir MFC DLL olup olmadığını belirten bir Boole değeri.

*`BaseType`*\
Dize temel türü.

*`var`*\
Bu dizeye atanacak bir değişken nesne.

*`ch`*\
Dizeye atanacak bir ANSI veya Unicode karakteri.

*`pszSrc`*\
Atanmakta olan özgün dizeye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Atama işleci başka bir **`CStringT`** nesneyi, bir karakter işaretçisini veya tek bir karakteri kabul eder. Yeni depolama alanı ayrılabileceği için bu işleci her kullanışınızda, bellek özel durumları oluşabilir.

Hakkında bilgi için `CThisSimpleString` [CStringT:: CStringT](#cstringt)konusunun açıklamalar bölümüne bakın.

> [!NOTE]
> Gömülü null karakterler içeren örnekler oluşturmak mümkün olsa da **`CStringT`** , bunun için önerilir. Katıştırılmış null karakterler içeren nesnelerde Yöntemler ve işleçler çağırma **`CStringT`** istenmeden sonuçlar verebilir.

## <a name="cstringtoperator-"></a><a name="operator_add"></a> `CStringT::operator +`

İki dizeyi veya bir karakteri ve dizeyi birleştirir.

```cpp
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```

### <a name="parameters"></a>Parametreler

*`ch1`*\
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*`ch2`*\
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*`str1`*\
Bir **`CStringT`** dize veya karakterle birleştirmek için.

*`str2`*\
Bir **`CStringT`** dize veya karakterle birleştirmek için.

*`psz1`*\
Bir dize veya karakterle birleştirmek için null ile sonlandırılmış bir dize işaretçisi.

*`psz2`*\
Dize veya karakterle birleştirilecek dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

İşlevin yedi aşırı yükleme biçimi vardır `CStringT::operator+` . İlk sürüm, varolan iki **`CStringT`** nesneyi birleştirir. Sonraki iki, bir **`CStringT`** nesneyi ve null ile sonlandırılmış dizeyi birleştirir. Sonraki iki bir **`CStringT`** nesne ve bır ANSI karakteri birleştirir. Son iki, bir **`CStringT`** nesneyi ve bir Unicode karakterini birleştirir.

> [!NOTE]
> Gömülü null karakterler içeren örnekler oluşturmak mümkün olsa da **`CStringT`** , bunun için önerilir. Katıştırılmış null karakterler içeren nesnelerde Yöntemler ve işleçler çağırma **`CStringT`** istenmeden sonuçlar verebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_add_eq"></a> `CStringT::operator +=`

Dizenin sonundaki karakterleri birleştirir.

```cpp
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```

### <a name="parameters"></a>Parametreler

*`str`*\
Bir `CThisSimpleString` nesneye başvuru.

*`bMFCDLL`*\
Projenin bir MFC DLL olup olmadığını belirten bir Boole değeri.

*`BaseType`*\
Dize temel türü.

*`var`*\
Bu dizeyi birleştirmek için bir değişken nesne.

*`ch`*\
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*`pszSrc`*\
Art arda eklenen orijinal dizeye yönelik bir işaretçi.

*`strSrc`*\
**`CStringT`** Bu dizeyi birleştirmek için bir.

### <a name="remarks"></a>Açıklamalar

İşleç başka bir **`CStringT`** nesneyi, bir karakter işaretçisini veya tek bir karakteri kabul eder. Bu nesneye eklenen karakterler için yeni depolama alanı ayrılamadığından, bu birleştirme işlecini her kullandığınızda bellek özel durumları oluşabilir **`CStringT`** .

Hakkında bilgi için `CThisSimpleString` [CStringT:: CStringT](#cstringt)konusunun açıklamalar bölümüne bakın.

> [!NOTE]
> Gömülü null karakterler içeren örnekler oluşturmak mümkün olsa da **`CStringT`** , bunun için önerilir. Katıştırılmış null karakterler içeren nesnelerde Yöntemler ve işleçler çağırma **`CStringT`** istenmeden sonuçlar verebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_eq_eq"></a> `CStringT::operator ==`

İki dizenin mantıksal olarak eşit olup olmadığını belirler.

```cpp
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>Parametreler

*`ch1`*\
Karşılaştırma için bir ANSI veya Unicode karakteri.

*`ch2`*\
Karşılaştırma için bir ANSI veya Unicode karakteri.

*`str1`*\
Bir **`CStringT`** karşılaştırma için.

*`str2`*\
Bir **`CStringT`** karşılaştırma için.

*`psz1`*\
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*`psz2`*\
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir dizenin veya karakterin sağ taraftaki bir dizeye veya karaktere eşit olup olmadığını test eder ve döndürür `TRUE` `FALSE` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_neq"></a> `CStringT::operator !=`

İki dizenin mantıksal olarak eşit olup olmadığını belirler.

```cpp
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>Parametreler

*`ch1`*\
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*`ch2`*\
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*`str1`*\
Bir **`CStringT`** karşılaştırma için.

*`str2`*\
Bir **`CStringT`** karşılaştırma için.

*`psz1`*\
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*`psz2`*\
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir dize veya karakter sağ taraftaki bir dizeye veya karaktere eşit değilse sınar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_lt"></a> `CStringT::operator <`

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha az olup olmadığını belirler.

```cpp
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*`str1`*\
Bir **`CStringT`** karşılaştırma için.

*`str2`*\
Bir **`CStringT`** karşılaştırma için.

*`psz1`*\
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*`psz2`*\
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgrafik karşılaştırması, şu kadar karakter olarak karakter:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karaktere sahip olduğunu ve bu nedenle dizelerin eşit olduğunu bulduğunu bulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_gt"></a> `CStringT::operator >`

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha büyük olup olmadığını belirler.

```cpp
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*`str1`*\
Bir **`CStringT`** karşılaştırma için.

*`str2`*\
Bir **`CStringT`** karşılaştırma için.

*`psz1`*\
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*`psz2`*\
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgrafik karşılaştırması, şu kadar karakter olarak karakter:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karakter içerdiğinden, dizelerin eşit olduğundan emin olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_lt_eq"></a> `CStringT::operator <=`

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden küçük veya ona eşit olup olmadığını belirler.

```cpp
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*`str1`*\
Bir **`CStringT`** karşılaştırma için.

*`str2`*\
Bir **`CStringT`** karşılaştırma için.

*`psz1`*\
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*`psz2`*\
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgrafik karşılaştırması, şu kadar karakter olarak karakter:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karakter içerdiğinden, dizelerin eşit olduğundan emin olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_gt_eq"></a> `CStringT::operator >=`

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden büyük veya ona eşit olup olmadığını belirler.

```cpp
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*`str1`*\
Bir **`CStringT`** karşılaştırma için.

*`str2`*\
Bir **`CStringT`** karşılaştırma için.

*`psz1`*\
Karşılaştırma için bir dizeye yönelik işaretçi.

*`psz2`*\
Karşılaştırma için bir dizeye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgrafik karşılaştırması, şu kadar karakter olarak karakter:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karakter içerdiğinden, dizelerin eşit olduğundan emin olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

## <a name="cstringtremove"></a><a name="remove"></a> `CStringT::Remove`

Belirtilen karakterin tüm örneklerini dizeden kaldırır.

```cpp
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>Parametreler

*`chRemove`*\
Dizeden kaldırılacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Dizeden kaldırılan karakter sayısı. Dize değiştirilmemişse sıfır.

### <a name="remarks"></a>Açıklamalar

Karakter karşılaştırmaları büyük/küçük harfe duyarlıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

## <a name="cstringtreplace"></a><a name="replace"></a> `CStringT::Replace`

Öğesinin iki sürümü vardır `Replace` . İlk sürüm, bir alt dizenin bir veya daha fazla kopyasını başka bir alt dize kullanarak değiştirir. Her iki alt dize de null ile sonlandırılır. İkinci sürüm, bir karakterin bir veya daha fazla kopyasını başka bir karakter kullanarak değiştirir. Her iki sürüm de ' de depolanan karakter verilerinde çalışır **`CStringT`** .

```cpp
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>Parametreler

*`pszOld`*\
İle değiştirilmeleri için null ile sonlandırılmış bir dize işaretçisi *`pszNew`* .

*`pszNew`*\
Yerine, null ile sonlandırılmış bir dize işaretçisi *`pszOld`* .

*`chOld`*\
İle değiştirildiği karakter *`chNew`* .

*`chNew`*\
Değiştirme karakteri *`chOld`* .

### <a name="return-value"></a>Dönüş Değeri

Karakter veya alt dizenin değiştirilen örneklerinin sayısını veya dize değiştirilmemişse sıfır değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`Replace` dize uzunluğunu değiştirebilir *`pszNew`* *`pszOld`* , ancak aynı uzunlukta olması gerekmez ve eski alt dizenin birkaç kopyası yeni bir tane olarak değiştirilebilir. İşlev, büyük/küçük harfe duyarlı bir eşleşme yapar.

Örnek örnekleri **`CStringT`** `CString` , ve ' dir `CStringA` `CStringW` .

İçin `CStringA` , `Replace` ANSI veya çok BAYTLı (MBCS) karakterlerle birlikte kullanılır. İçin `CStringW` , `Replace` geniş karakterlerle işe yarar.

İçin `CString` , karakter veri türü, aşağıdaki tablodaki sabitlerin tanımlı olup olmadığına bağlı olarak, derleme zamanında seçilir.

|Tanımlı sabit|Karakter veri türü|
|----------------------|-------------------------|
|`_UNICODE`|Geniş karakterler|
|`_MBCS`|Çok baytlı karakterler|
|Hiçbiri|Tek baytlık karakterler|
|Her ikisi|Tanımlayan|

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

## <a name="cstringtreversefind"></a><a name="reversefind"></a> `CStringT::ReverseFind`

Bu **`CStringT`** nesneyi bir karakterin son eşleşmesi için arar.

```cpp
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>Parametreler

*`ch`*\
Aranacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Bu nesnedeki, istenen karakterle eşleşen son karakterin sıfır tabanlı dizini **`CStringT`** veya karakter bulunamazsa-1.

### <a name="remarks"></a>Açıklamalar

İşlevi, çalışma zamanı işlevine benzer `strrchr` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

## <a name="cstringtright"></a><a name="right"></a> `CStringT::Right`

Bu nesneden son (en sağdaki) karakterleri ayıklar *`nCount`* **`CStringT`** ve ayıklanan alt dizenin bir kopyasını döndürür.

```cpp
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>Parametreler

*`nCount`*\
Bu nesneden Ayıklanacak karakter sayısı **`CStringT`** .

### <a name="return-value"></a>Dönüş Değeri

**`CStringT`** Belirtilen karakter aralığının bir kopyasını içeren nesne. Döndürülen **`CStringT`** nesne boş olabilir.

### <a name="remarks"></a>Açıklamalar

*`nCount`* Dize uzunluğunu aşarsa, tüm dize ayıklanır. `Right` , temel `Right` işleve benzerdir (temel içindeki dizinler sıfır tabanlı olur hariç).

Çok baytlı karakter kümeleri (MBCS) için *`nCount`* her 8 bit karaktere başvurur; diğer bir deyişle, bir çok baytlı karakter içindeki bir lider ve sondaki bayt iki karakter olarak sayılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

## <a name="cstringtsetsysstring"></a><a name="setsysstring"></a> `CStringT::SetSysString`

**`BSTR`** Tarafından işaret *`pbstr`* edilen değeri, null karakteri de dahil olmak üzere tarafından işaret edilen olarak konumlandırır ve **`CStringT`** içine kopyalar.

```cpp
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>Parametreler

*`pbstr`*\
Karakter dizesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yeni dize.

### <a name="remarks"></a>Açıklamalar

Nesnenin içeriğine bağlı olarak **`CStringT`** , başvurduğu değerin değeri **`BSTR`** *`pbstr`* değişebilir. `CMemoryException`Yeterli bellek yoksa işlev bir oluşturur.

Bu işlev genellikle otomasyon için başvuruya göre geçirilen dizelerin değerini değiştirmek için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

## <a name="cstringtspanexcluding"></a><a name="spanexcluding"></a> `CStringT::SpanExcluding`

Tarafından tanımlanan karakter kümesinde olmayan, ilk karakterle başlayarak dizeden karakter ayıklar *`pszCharSet`* .

```cpp
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Parametreler

*`pszCharSet`*\
Bir karakter kümesi olarak yorumlanan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Dizedeki *`pszCharSet`* ilk karakterle başlayan ve ayrıca içinde olan dizedeki ilk karakterle biten *`pszCharSet`* (yani, dizedeki ilk karakterle başlayan, ancak bulunan dizedeki ilk karakter hariç), içinde olmayan karakter içeren bir alt dize. (yani, dizedeki ilk karakter ile başlayıp, bulunan dizedeki ilk karakter hariç *`pszCharSet`* ). Dizede hiçbir karakter bulunamazsa dizenin tamamını döndürür *`pszCharSet`* .

### <a name="remarks"></a>Açıklamalar

`SpanExcluding` içindeki bir karakterin ilk örneğinden önceki tüm karakterleri ayıklar ve döndürür *`pszCharSet`* (diğer bir deyişle, öğesinden *`pszCharSet`* ve dizedeki karakter izleyen tüm karakterler döndürülmez). Dizede bir karakter *`pszCharSet`* bulunamazsa, `SpanExcluding` dizenin tamamını döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

## <a name="cstringtspanincluding"></a><a name="spanincluding"></a> `CStringT::SpanIncluding`

Tarafından tanımlanan karakter kümesindeki ilk karakterle başlayarak dizeden karakter ayıklar *`pszCharSet`* .

```cpp
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Parametreler

*`pszCharSet`*\
Bir karakter kümesi olarak yorumlanan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Dizedeki *`pszCharSet`* ilk karakterle başlayan ve içinde olmayan dizede bir karakter bulunduğunda biten dizedeki karakterleri içeren bir alt dize *`pszCharSet`* . `SpanIncluding` dizedeki ilk karakter belirtilen küme içinde değilse boş bir alt dize döndürür.

### <a name="remarks"></a>Açıklamalar

Dizenin ilk karakteri karakter kümesinde değilse `SpanIncluding` boş bir dize döndürür. Aksi takdirde, küme içindeki ardışık karakterlerin dizisini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

## <a name="cstringttokenize"></a><a name="tokenize"></a> `CStringT::Tokenize`

Hedef dizede bir sonraki belirteci bulur

```cpp
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>Parametreler

*`pszTokens`*\
Belirteç sınırlayıcıları içeren bir dize. Bu sınırlayıcıların sırası önemli değildir.

*`iStart`*\
Aramaya başlamak için sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

**`CStringT`** Geçerli belirteç değerini içeren nesne.

### <a name="remarks"></a>Açıklamalar

`Tokenize`İşlevi, hedef dizedeki bir sonraki belirteci bulur. *PszTokens* içindeki karakter kümesi, bulunamayan belirtecin olası sınırlayıcılarını belirtir. İşlevine yapılan her çağrıda `Tokenize` başlar *`iStart`* , önde gelen sınırlayıcıları atlar ve **`CStringT`** sonraki sınırlayıcı karaktere kadar olan karakterlerin dizesi olan geçerli belirteci içeren bir nesne döndürür. Değeri *`iStart`* bitiş sınırlayıcı karakteri izleyen konum olacak şekilde güncelleştirilir veya dizenin sonuna ulaşılırsa-1. Daha fazla belirteç, ' a bir dizi çağrı ile hedef dizenin geri kalanından ayrılabilir `Tokenize` ve bir *`iStart`* sonraki belirtecin nerede okunacağını izlemek için kullanılarak. Daha fazla belirteç kalmadığında, işlev boş bir dize döndürür ve *`iStart`* -1 olarak ayarlanır.

CRT simgeleştirin benzer işlevlerden farklı olarak [`strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l`](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md) , `Tokenize` hedef dizeyi değiştirmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

Bu örnekteki çıktı aşağıdaki gibidir:

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

## <a name="cstringttrim"></a><a name="trim"></a> `CStringT::Trim`

Dizeden baştaki ve sondaki karakterleri kırpar.

```cpp
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>Parametreler

*`chTarget`*\
Kırpılacak hedef karakter.

*`pszTargets`*\
Kırpılacak hedef karakterleri içeren bir dize işaretçisi. İçindeki karakterlerin tüm önde gelen ve sondaki oluşumları *`pszTargets`* **`CStringT`** nesnesinden kırpılır.

### <a name="return-value"></a>Dönüş Değeri

Kırpılan dizeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin önde gelen ve sondaki oluşumlarını kaldırır:

- Tarafından belirtilen karakter *`chTarget`* .

- Tarafından belirtilen dizede bulunan tüm karakterler *`pszTargets`* .

- Boşlu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

Bu örnekteki çıktı aşağıdaki gibidir:

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

## <a name="cstringttrimleft"></a><a name="trimleft"></a> `CStringT::TrimLeft`

Dizeden baştaki karakterleri kırpar.

```cpp
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>Parametreler

*`chTarget`*\
Kırpılacak hedef karakter.

*`pszTargets`*\
Kırpılacak hedef karakterleri içeren bir dize işaretçisi. İçindeki karakterlerin tüm önde gelen oluşumları *`pszTargets`* nesnesinden kırpılacak **`CStringT`** .

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan kırpılan dize.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin önde gelen ve sondaki oluşumlarını kaldırır:

- Tarafından belirtilen karakter *`chTarget`* .

- Tarafından belirtilen dizede bulunan tüm karakterler *`pszTargets`* .

- Boşlu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

## <a name="cstringttrimright"></a><a name="trimright"></a> `CStringT::TrimRight`

Dizeden sondaki karakterleri kırpar.

```cpp
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>Parametreler

*`chTarget`*\
Kırpılacak hedef karakter.

*`pszTargets`*\
Kırpılacak hedef karakterleri içeren bir dize işaretçisi. İçindeki tüm karakter oluşumları *`pszTargets`* nesnesinden kırpılacak **`CStringT`** .

### <a name="return-value"></a>Dönüş Değeri

**`CStringT`** Kırpılan dizeyi içeren nesneyi döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin sondaki oluşumlarını kaldırır:

- Tarafından belirtilen karakter *`chTarget`* .

- Tarafından belirtilen dizede bulunan tüm karakterler *`pszTargets`* .

- Boşlu.

`CStringT& TrimRight(XCHAR chTarget)`Sürüm bir karakter parametresini kabul eder ve dize verisinin sonundaki bu karakterin tüm kopyalarını kaldırır **`CStringT`** . Dizenin sonundan başlar ve önünde doğru çalışacaktır. Farklı bir karakter bulduğunda veya **`CStringT`** karakter verilerinden çalıştırıldığında duraklar.

`CStringT& TrimRight(PCXSTR pszTargets)`Sürüm, aranacak tüm farklı karakterleri içeren null ile sonlandırılmış bir dizeyi kabul eder. Nesne içindeki bu karakterlerin tüm kopyalarını kaldırır **`CStringT`** . Dizenin sonunda başlar ve önünde doğru çalışacaktır. Hedef dizede olmayan bir karakter bulduğunda veya **`CStringT`** karakter verilerinden çalıştırıldığında duraklar. Tüm hedef dizeyi sonundaki bir alt dizeyle eşleştirmeye çalışır **`CStringT`** .

`CStringT& TrimRight()`Sürüm parametre gerektirmez. Dizenin sonundaki sondaki boşluk karakterlerini kırpar **`CStringT`** . Boşluk karakterleri satır sonları, boşluklar veya sekmeler olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)\
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)\
[CSimpleStringT sınıfı](../../atl-mfc-shared/reference/csimplestringt-class.md)
