---
title: CStringT sınıfı
ms.date: 10/18/2018
f1_keywords:
- CStringT
- ATLSTR/ATL::CStringT
- ATLSTR/ATL::CStringT::CStringT
- ATLSTR/ATL::CStringT::AllocSysString
- ATLSTR/ATL::CStringT::AnsiToOem
- ATLSTR/ATL::CStringT::AppendFormat
- ATLSTR/ATL::CStringT::Collate
- ATLSTR/ATL::CStringT::CollateNoCase
- ATLSTR/ATL::CStringT::Compare
- ATLSTR/ATL::CStringT::CompareNoCase
- ATLSTR/ATL::CStringT::Delete
- ATLSTR/ATL::CStringT::Find
- ATLSTR/ATL::CStringT::FindOneOf
- ATLSTR/ATL::CStringT::Format
- ATLSTR/ATL::CStringT::FormatMessage
- ATLSTR/ATL::CStringT::FormatMessageV
- ATLSTR/ATL::CStringT::FormatV
- ATLSTR/ATL::CStringT::GetEnvironmentVariable
- ATLSTR/ATL::CStringT::Insert
- ATLSTR/ATL::CStringT::Left
- ATLSTR/ATL::CStringT::LoadString
- ATLSTR/ATL::CStringT::MakeLower
- ATLSTR/ATL::CStringT::MakeReverse
- ATLSTR/ATL::CStringT::MakeUpper
- ATLSTR/ATL::CStringT::Mid
- ATLSTR/ATL::CStringT::OemToAnsi
- ATLSTR/ATL::CStringT::Remove
- ATLSTR/ATL::CStringT::Replace
- ATLSTR/ATL::CStringT::ReverseFind
- ATLSTR/ATL::CStringT::Right
- ATLSTR/ATL::CStringT::SetSysString
- ATLSTR/ATL::CStringT::SpanExcluding
- ATLSTR/ATL::CStringT::SpanIncluding
- ATLSTR/ATL::CStringT::Tokenize
- ATLSTR/ATL::CStringT::Trim
- ATLSTR/ATL::CStringT::TrimLeft
- ATLSTR/ATL::CStringT::TrimRight
- CSTRINGT/CStringT
- CSTRINGT/CStringT::CStringT
- CSTRINGT/CStringT::AllocSysString
- CSTRINGT/CStringT::AnsiToOem
- CSTRINGT/CStringT::AppendFormat
- CSTRINGT/CStringT::Collate
- CSTRINGT/CStringT::CollateNoCase
- CSTRINGT/CStringT::Compare
- CSTRINGT/CStringT::CompareNoCase
- CSTRINGT/CStringT::Delete
- CSTRINGT/CStringT::Find
- CSTRINGT/CStringT::FindOneOf
- CSTRINGT/CStringT::Format
- CSTRINGT/CStringT::FormatMessage
- CSTRINGT/CStringT::FormatMessageV
- CSTRINGT/CStringT::FormatV
- CSTRINGT/CStringT::GetEnvironmentVariable
- CSTRINGT/CStringT::Insert
- CSTRINGT/CStringT::Left
- CSTRINGT/CStringT::LoadString
- CSTRINGT/CStringT::MakeLower
- CSTRINGT/CStringT::MakeReverse
- CSTRINGT/CStringT::MakeUpper
- CSTRINGT/CStringT::Mid
- CSTRINGT/CStringT::OemToAnsi
- CSTRINGT/CStringT::Remove
- CSTRINGT/CStringT::Replace
- CSTRINGT/CStringT::ReverseFind
- CSTRINGT/CStringT::Right
- CSTRINGT/CStringT::SetSysString
- CSTRINGT/CStringT::SpanExcluding
- CSTRINGT/CStringT::SpanIncluding
- CSTRINGT/CStringT::Tokenize
- CSTRINGT/CStringT::Trim
- CSTRINGT/CStringT::TrimLeft
- CSTRINGT/CStringT::TrimRight
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
ms.openlocfilehash: 9566830de4d3af8f34e8efa5e5ef468acae1fba5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750877"
---
# <a name="cstringt-class"></a>CStringT sınıfı

Bu sınıfın temsil ettiği bir `CStringT` nesne.

## <a name="syntax"></a>Sözdizimi

```
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>Parametreler

*BaseType*<br/>
Dize sınıfı karakter türü. Aşağıdakilerden biri olabilir:

- **char** (için ANSI karakter dizeleri).

- **wchar_t** (için Unicode karakter dizeleri).

- TCHAR (için ANSI hem Unicode karakter dizeleri).

*StringTraits*<br/>
Dize sınıfı C çalışma zamanı (CRT) kitaplığı desteğiyle ve dize kaynakları bulunduğu yere gerekip gerekmediğini belirler. Aşağıdakilerden biri olabilir:

- **StrTraitATL < wchar_t** &#124; **char** &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; **char** &#124;  **TCHAR >>**

   CRT desteği ve kaynak dizeleri tarafından belirtilen modüldeki arar sınıfı gerektirir `m_hInstResource` (uygulamanın modül sınıfının üyesi).

- **StrTraitATL < wchar_t** &#124; **char** &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; **char** &#124;  **TCHAR >>**

   Sınıfı, CRT desteği ve kaynak dizeleri tarafından belirtilen modüldeki arar gerektirmez `m_hInstResource` (uygulamanın modül sınıfının üyesi).

- **StrTraitMFC < wchar_t** &#124; **char** &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; **char** &#124;  **TCHAR >>**

   Sınıfı, CRT desteği ve kaynak dizeleri standart MFC arama algoritması kullanarak arar gerektirir.

- **StrTraitMFC< wchar_t** &#124; **char** &#124; **TCHAR, ChTraitsOS< wchar_t** &#124; **char** &#124; **TCHAR > >**

   Sınıfı, CRT desteği ve kaynak dizeleri standart MFC arama algoritması kullanarak arar gerektirmez.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStringT::CStringT](#cstringt)|Oluşturur bir `CStringT` çeşitli şekillerde nesne.|
|[CStringT:: ~ CStringT](#_dtorcstringt)|Yok eder bir `CStringT` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStringT::AllocSysString](#allocsysstring)|BSTR öğesinden ayırır `CStringT` veri.|
|[CStringT::AnsiToOem](#ansitooem)|ANSI karakter OEM karakter kümesine bir yerinde dönüştürme yapar.|
|[CStringT::AppendFormat](#appendformat)|Varolan bir biçimlendirilmiş veriler ekler `CStringT` nesne.|
|[CStringT::Collate](#collate)|(Çalışması önemli, yerel ayara özgü bilgileri kullanır) iki dizeyi karşılaştırır.|
|[CStringT::CollateNoCase](#collatenocase)|(/ Küçük harfe duyarlı durumda, yerel ayara özgü bilgileri kullanır) iki dizeyi karşılaştırır.|
|[CStringT::Compare](#compare)|(Büyük/küçük harfe duyarlı) iki dizeyi karşılaştırır.|
|[CStringT::CompareNoCase](#comparenocase)|(Büyük küçük harfe duyarlı) iki dizeyi karşılaştırır.|
|[CStringT::Delete](#delete)|Bir karakteri veya karakterleri bir dizeden siler.|
|[CStringT::Find](#find)|Bir karakter veya daha büyük bir dize içinde alt dizeyi bulur.|
|[CStringT::FindOneOf](#findoneof)|Kümesinden eşleşen ilk karakteri bulur.|
|[CStringT::Format](#format)|Dize olarak biçimlendirir `sprintf` yapar.|
|[CStringT::FormatMessage](#formatmessage)|Bir ileti dizesi olarak biçimlendirir.|
|[CStringT::FormatMessageV](#formatmessagev)|Değişken bağımsız değişken listesini kullanarak bir ileti dizesi olarak biçimlendirir.|
|[CStringT::FormatV](#formatv)|Bağımsız değişken listesini kullanarak dize olarak biçimlendirir.|
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Dize değeri olarak belirtilen ortam değişkenini ayarlar.|
|[CStringT::Insert](#insert)|Tek bir karakter veya bir alt dizeyi dizenin içinde belirtilen dizini ekler.|
|[CStringT::Left](#left)|Bir dizenin sol bölümü ayıklar.|
|[CStringT::LoadString](#loadstring)|Mevcut bir yükler `CStringT` Windows Kaynak nesne.|
|[CStringT::MakeLower](#makelower)|Tüm karakterleri bu dizedeki karakterlerin küçük harfe dönüştürür.|
|[CStringT::MakeReverse](#makereverse)|Dize tersine çevirir.|
|[CStringT::MakeUpper](#makeupper)|Tüm karakterleri bu dizedeki karakterlerin büyük harfe dönüştürür.|
|[CStringT::Mid](#mid)|Bir dizenin ortadaki bölüm ayıklar.|
|[CStringT::OemToAnsi](#oemtoansi)|OEM karakter ANSI karakter kümesine kümesindeki bir yerinde dönüştürme yapar.|
|[CStringT::Remove](#remove)|Karakterleri bir dizeden kaldırır gösterilir.|
|[CStringT::Replace](#replace)|Diğer karakterler karakterlerle değiştirir gösterilir.|
|[CStringT::ReverseFind](#reversefind)|Bir karakter daha büyük bir dize içinde bulur; Son'dan başlar.|
|[CStringT::Right](#right)|Bir dize sağ bölümünü ayıklar.|
|[CStringT::SetSysString](#setsysstring)|Mevcut bir BSTR nesnesi verilerle ayarlar bir `CStringT` nesne.|
|[CStringT::SpanExcluding](#spanexcluding)|Karakter dizesinden tarafından tanımlanan karakter kümesine olmayan ilk karakter'ile başlayan ayıklar `pszCharSet`.|
|[CStringT::SpanIncluding](#spanincluding)|Yalnızca bir küme içindeki karakterleri içeren bir alt dizeyi ayıklar.|
|[CStringT::Tokenize](#tokenize)|Ayıklar belirteçleri hedef dizesi içinde belirtilmiş.|
|[CStringT::Trim](#trim)|Dize değerinden tüm öndeki ve sondaki boşluk karakterleri kırpar.|
|[CStringT::TrimLeft](#trimleft)|Baştaki boşluk dizesi kırpar.|
|[CStringT::TrimRight](#trimright)|Sondaki boşluk karakterlerini dize kırpar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Yeni bir değer atar bir `CStringT` nesne.|
|[CStringT::operator +](#operator_add)|İki dizeyi veya bir karakter ve dize art arda ekler.|
|[CStringT::operator +=](#operator_add_eq)|Yeni bir dize sonuna kadar varolan bir dizeyi art arda ekler.|
|[CStringT::operator ==](#operator_eq_eq)|İki dizeyi mantıksal olarak eşit olup olmadığını belirler.|
|[CStringT::operator! =](#operator_neq)|İki dizenin eşit değilse mantıksal olarak belirler.|
|[CStringT::operator &lt;](#operator_lt)|Dize işlecinin sol tarafındaki küçüktür için olup olmadığını belirler. sağ tarafta bir dize.|
|[CStringT::operator &gt;](#operator_gt)|İşlecin sol tarafındaki dize dizesine işlecin sağ tarafındaki büyük olup olmadığını belirler.|
|[CStringT::operator &lt;=](#operator_lt_eq)|İşlecin sol tarafındaki dize ya da dize işlecin sağ tarafındaki eşit olup olmadığını belirler.|
|[CStringT::operator &gt;=](#operator_gt_eq)|Dize işlecinin sol tarafındaki büyük veya işlecin sağ tarafındaki bir dizeye eşit olup olmadığını belirler.|

## <a name="remarks"></a>Açıklamalar

`CStringT` devralınan [CSimpleStringT sınıfı](../../atl-mfc-shared/reference/csimplestringt-class.md). Karakter işleme, sıralama ve arama gibi gelişmiş özellikler tarafından uygulanır `CStringT`.

> [!NOTE]
> `CStringT` özel durum oluşturma Yeteneğin sahip nesneleridir. Böyle olduğunda bir `CStringT` nesneyi bellek yetersiz herhangi bir nedenle çalıştırır.

A `CStringT` nesnesi bir karakterden değişken uzunluklu dizi oluşur. `CStringT` İşlevler ve işleçler, temel benzer bir sözdizimi kullanarak sağlar. Birleştirme ve Karşılaştırma işleçleri altında Basitleştirilmiş bellek yönetimi, `CStringT` nesneleri normal karakter dizileri kullanmak daha kolay.

> [!NOTE]
>  Oluşturmak mümkün olsa da `CStringT` gömülü null karakterleri içeren örnekleri, karşı öneririz. Yöntemleri ve işleçleri çağırma `CStringT` gömülü null karakterleri içeren nesneleri, istenmeyen sonuçlar üretebilir.

Farklı birleşimleri kullanarak `BaseType` ve `StringTraits` parametreleri `CStringT` gelen olan aşağıdaki türleri olan önceden tanımlanmış ATL kitaplığı tarafından nesneleri.

ATL uygulamada kullanıyorsanız:

`CString`, `CStringA`, ve `CStringW` MFC DLL (MFC90. verilir DLL), hiçbir zaman kullanıcıdan DLL'ler. Bunu önlemek için yapılır `CStringT` gelen birden çok kez tanımlanmış.

> [!NOTE]
>  Kodunuzu açıklanan bağlayıcı hatalar için geçici çözüm içeriyorsa [dize sınıflarını kullanarak CStringT verme](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md), kodun kaldırmanız gerekir. Artık gerekli değildir.

MFC tabanlı uygulamalar içinde aşağıdaki dize türleri kullanılabilir:

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CStringA`|Bir ANSI karakter dizesi CRT desteğiyle yazın.|
|`CStringW`|Bir Unicode karakter dizesi CRT desteğiyle yazın.|
|`CString`|CRT desteğiyle hem ANSI ve Unicode karakter türleri.|

Aşağıdaki dize türleri ATL_CSTRING_NO_CRT tanımlandığı projelerinde kullanılabilir:

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CAtlStringA`|Bir ANSI karakter dizesi CRT desteği olmadan yazın.|
|`CAtlStringW`|Bir Unicode karakter dizesi CRT desteği olmadan yazın.|
|`CAtlString`|CRT desteği olmadan hem ANSI ve Unicode karakter türleri.|

Aşağıdaki dize türleri ATL_CSTRING_NO_CRT değil tanımlandığı projelerinde kullanılabilir:

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CAtlStringA`|Bir ANSI karakter dizesi CRT desteğiyle yazın.|
|`CAtlStringW`|Bir Unicode karakter dizesi CRT desteğiyle yazın.|
|`CAtlString`|CRT desteğiyle hem ANSI ve Unicode karakter türleri.|

`CString` nesneleri ayrıca aşağıdaki özelliklere sahiptir:

- `CStringT` nesneleri birleştirme işlemleri sonucu olarak büyüyebilir.

- `CStringT` "semantiği değeri" nesneleri izleyin Düşünün bir `CStringT` gerçek bir dize olarak, bir dizeye bir işaretçi olarak değil bir nesne.

- Özgürce değiştirebildiği `CStringT` için nesneleri `PCXSTR` işlev bağımsız değişkenleri.

- Dize arabellek için özel bellek yönetimi. Daha fazla bilgi için [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="cstringt-predefined-types"></a>CStringT türleri önceden tanımlanmıştır.

Çünkü `CStringT` karakter türünü tanımlamak için bir şablon bağımsız değişkeni'ni kullanır (ya da [wchar_t](../../c-runtime-library/standard-types.md) veya [char](../../c-runtime-library/standard-types.md)) desteklenen yöntem parametre türleriyle bazen karmaşık olabilir. Bu sorunu basitleştirmek için önceden tanımlanmış türler kümesi tanımlanır ve genelinde kullanılan `CStringT` sınıfı. Aşağıdaki tabloda, çeşitli türleri listeler:

|Ad|Açıklama|
|----------|-----------------|
|`XCHAR`|Tek bir karakter (ya da **wchar_t** veya **char**) aynı karakter türü ile `CStringT` nesne.|
|`YCHAR`|Tek bir karakter (ya da **wchar_t** veya **char**) karşı karakter türü ile `CStringT` nesne.|
|`PXSTR`|Bir karakter dizesine bir işaretçi (ya da **wchar_t** veya **char**) aynı karakter türü ile `CStringT` nesne.|
|`PYSTR`|Bir karakter dizesine bir işaretçi (ya da **wchar_t** veya **char**) karşı karakter türü ile `CStringT` nesne.|
|`PCXSTR`|Bir işaretçi bir **const** karakter dizesi (ya da **wchar_t** veya **char**) aynı karakter türü ile `CStringT` nesne.|
|`PCYSTR`|Bir işaretçi bir **const** karakter dizesi (ya da **wchar_t** veya **char**) karşı karakter türü ile `CStringT` nesne.|

> [!NOTE]
>  Daha önce belgelenmemiş yöntemlerini kullanan kod `CString` (gibi `AssignCopy`) aşağıdaki belgelenmiş yöntemlerini kullanan kod ile değiştirilmelidir `CStringT` (gibi `GetBuffer` veya `ReleaseBuffer`). Bu yöntemler devralındığı `CSimpleStringT`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>Gereksinimler

|Üstbilgi|Kullanım için|
|------------|-------------|
|cstringt.h|Dize yalnızca MFC nesneleri|
|yönelik baskılamayı kaldırma|MFC olmayan dize nesnesi|

##  <a name="allocsysstring"></a>  CStringT::AllocSysString

Bir otomasyon uyumlu dize türü BSTR ayırır ve içeriğini kopyalar `CStringT` sondaki null karakter de dahil olmak üzere, nesneye.

```
BSTR AllocSysString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan dize.

### <a name="remarks"></a>Açıklamalar

MFC programlarda bir [CMemoryException sınıfı](../../mfc/reference/cmemoryexception-class.md) yetersiz bellek varsa oluşturulur. ATL programlarda bir [CAtlException](../../atl/reference/catlexception-class.md) oluşturulur. Bu işlev, normalde dizeleri için Otomasyon döndürmek için kullanılır.

Yaygın olarak, bu dize bir COM işlevine geçirilirse bir [] parametresi, ardından bu gerektirir çağıran dize boş. Bu kullanarak yapılabilir [SysFreeString](/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)Windows SDK içinde açıklandığı gibi. Daha fazla bilgi için [Allocating ve BSTR için bellek serbest bırakma](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).

Windows OLE ayırma işlevleri hakkında daha fazla bilgi için bkz. [SysAllocString](/windows/desktop/api/oleauto/nf-oleauto-sysallocstring) Windows SDK.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CStringT::AllocSysString`.

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

##  <a name="ansitooem"></a>  CStringT::AnsiToOem

Bu tüm karakterleri dönüştürür `CStringT` OEM karakter kümesine ANSI karakter nesne.

```
void AnsiToOem();
```

### <a name="remarks"></a>Açıklamalar

_UNICODE tanımlanmış olması durumunda, işlevi kullanılamaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

##  <a name="appendformat"></a>  CStringT::AppendFormat

Varolan bir biçimlendirilmiş veriler ekler `CStringT` nesne.

```
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Bir biçim denetimi dizesi.

*nFormatID*<br/>
Biçim Denetimi dizesi içeren dize kaynak kimliği.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

Bu işlev biçimlendirir ve bir dizi karakter ve değerlerini ekler `CStringT`. Her isteğe bağlı bağımsız değişken (varsa) dönüştürülür ve karşılık gelen kapsamındaki biçim belirtimine göre eklenen *pszFormat* veya dize kaynağı tarafından tanımlanan *nFormatID*.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

##  <a name="collate"></a>  CStringT::Collate

Genel metin işlevi kullanarak iki dizeyi karşılaştırır `_tcscoll`.

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*psz*<br/>
Karşılaştırma için kullanılan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, < 0 bu `CStringT` nesne küçüktür *psz*, veya > 0 bu `CStringT` nesnedir büyüktür *psz*.

### <a name="remarks"></a>Açıklamalar

Genel metin işlevi `_tcscoll`, TCHAR içinde tanımlanır. H, ya da eşler `strcoll`, `wcscoll`, veya `_mbscoll`derleme zamanında tanımlanan karakter kümesine bağlı olarak. Her işlev büyük küçük harfe duyarlı bir karşılaştırma dizeler kod sayfasına göre şu anda kullanımda gerçekleştirir. Daha fazla bilgi için [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

##  <a name="collatenocase"></a>  CStringT::CollateNoCase

Genel metin işlevi kullanarak iki dizeyi karşılaştırır `_tcscoll`.

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*psz*<br/>
Karşılaştırma için kullanılan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeleri ise sıfır özdeş (göz ardı harf), < 0 bu `CStringT` nesne küçüktür *psz* (çalışması yoksayar) veya > 0 bu `CStringT` nesnedir büyüktür *psz* (çalışması yoksayar).

### <a name="remarks"></a>Açıklamalar

Genel metin işlevi `_tcscoll`, TCHAR içinde tanımlanır. H, ya da eşler `stricoll`, `wcsicoll`, veya `_mbsicoll`derleme zamanında tanımlanan karakter kümesine bağlı olarak. Her işlev, şu anda kod sayfasına göre dizeleri büyük küçük harf duyarsız bir karşılaştırma gerçekleştirir. Daha fazla bilgi için [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

##  <a name="compare"></a>  CStringT::Compare

(Büyük/küçük harfe duyarlı) iki dizeyi karşılaştırır.

```
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>Parametreler

*psz*<br/>
Karşılaştırma için kullanılan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, < 0 bu `CStringT` nesne küçüktür *psz*, veya > 0 bu `CStringT` nesnedir büyüktür *psz*.

### <a name="remarks"></a>Açıklamalar

Genel metin işlevi `_tcscmp`, TCHAR içinde tanımlanır. H, ya da eşler `strcmp`, `wcscmp`, veya `_mbscmp`derleme zamanında tanımlanan karakter kümesine bağlı olarak. Her işlev, dizenin büyük küçük harfe duyarlı bir karşılaştırma gerçekleştirir ve yerel ayar tarafından etkilenmez. Daha fazla bilgi için [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).

Dize gömülü null değerler içeriyorsa, karşılaştırma dizesi gömülü null karakter: kesilecek olduğu düşünülerek hesaplanır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CStringT::Compare`.

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

##  <a name="comparenocase"></a>  CStringT::CompareNoCase

(Büyük küçük harfe duyarlı) iki dizeyi karşılaştırır.

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*psz*<br/>
Karşılaştırma için kullanılan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır (çalışması yoksayar) < bu değilse 0 `CStringT` nesne küçüktür *psz* (çalışması yoksayar) veya > Bu değilse 0 `CStringT` nesnedir büyüktür *psz* (çalışması yoksayar).

### <a name="remarks"></a>Açıklamalar

Genel metin işlevi `_tcsicmp`, TCHAR içinde tanımlanır. H, ya da eşler `_stricmp`, `_wcsicmp` veya `_mbsicmp`derleme zamanında tanımlanan karakter kümesine bağlı olarak. Her işlev, dizenin büyük küçük harf duyarsız bir karşılaştırma gerçekleştirir. Karşılaştırma, yerel ayar ancak değil LC_COLLATE LC_CTYPE yönüyle üzerinde bağlıdır. Daha fazla bilgi için [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

##  <a name="cstringt"></a>  CStringT::CStringT

Oluşturur bir `CStringT` nesne.

```
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

*pch*<br/>
Karakter uzunlukta bir dizi işaretçi *nLength*, boş sonlandırılmış.

*nLength*<br/>
Karakter sayısını *pch*.

*ch*<br/>
Tek bir karakter.

*pszSrc*<br/>
Null ile sonlandırılmış bir dize bu kopyalanacak `CStringT` nesne.

*pStringMgr*<br/>
Bellek Yöneticisi için bir işaretçiye `CStringT` nesne. Daha fazla bilgi için `IAtlStringMgr` ve bellek yönetimi için `CStringT`, bkz: [CStringT ile bellek yönetimi](../../atl-mfc-shared/memory-management-with-cstringt.md).

*strSrc*<br/>
Mevcut bir `CStringT` bu kopyalanacak nesne `CStringT` nesne. Daha fazla bilgi için `CThisString` ve `CThisSimpleString`, Açıklamalar bölümüne bakın.

*varSrc*<br/>
Bu kopyalanacak bir VARIANT nesnesi `CStringT` nesne.

*BaseType*<br/>
Dize sınıfı karakter türü. Aşağıdakilerden biri olabilir:

**char** (için ANSI karakter dizeleri).

**wchar_t** (için Unicode karakter dizeleri).

TCHAR (için ANSI hem Unicode karakter dizeleri).

*bMFCDLL*<br/>
Proje bir MFC DLL (TRUE) olup olmadığını belirten bir Boole değeri (FALSE).

*SystemString*<br/>
Olmalıdır `System::String`, ve proje/CLR ile derlenmiş olmalıdır.

*pString*<br/>
İçin bir tanıtıcı bir `CStringT` nesne.

### <a name="remarks"></a>Açıklamalar

Oluşturucular girdi verilerini yeni ayrılan depolama alanına kopyalayın çünkü farkında olmalıdır, bellek, özel durumlar neden olabilir. Bu oluşturucular bazıları dönüştürme işlevleri davranan unutmayın. Bu sayede, örneğin, bir LPTSTR yerine burada bir `CStringT` nesne bekleniyor.

- `CStringT`( `LPCSTR` `lpsz` ): Bir Unicode yapıları `CStringT` ANSI dizesinden. Bu oluşturucu, aşağıdaki örnekte gösterildiği gibi bir dize kaynağı yüklemek için de kullanabilirsiniz.

- `CStringT(` `LPCWSTR` `lpsz` ): Oluşturur bir `CStringT` bir Unicode dize değerinden.

- `CStringT`( `const unsigned char*` `psz` ): Oluşturulacağını sağlar bir `CStringT` işaretçisine **imzasız char**.

> [!NOTE]
>  Dizeleri ANSI ve Unicode arasında örtük dize dönüştürme devre dışı bırakmak üzere _CSTRING_DISABLE_NARROW_WIDE_CONVERSION makro tanımlayın. Makro dönüştürme desteği derleme oluşturucular dışlar.

Unutmayın *strSrc* parametresi ya da olabilir bir `CStringT` veya `CThisSimpleString` nesne. İçin `CStringT`, kendi varsayılan örneklemeleri birini kullanın (`CString`, `CStringA`, veya `CStringW`); `CThisSimpleString`, kullanan bir **bu** işaretçi. `CThisSimpleString` örneğini bildirir [CSimpleStringT sınıfı](../../atl-mfc-shared/reference/csimplestringt-class.md), daha az yerleşik işlevlerle daha küçük bir dize sınıf `CStringT` sınıfı.

İşlecini `CSimpleStringT<>&()` oluşturan bir `CStringT` nesnesinden bir `CSimpleStringT` bildirimi.

> [!NOTE]
>  Oluşturmak mümkün olsa da `CStringT` gömülü null karakterleri içeren örnekleri, karşı öneririz. Yöntemleri ve işleçleri çağırma `CStringT` gömülü null karakterleri içeren nesneleri, istenmeyen sonuçlar üretebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

##  <a name="_dtorcstringt"></a>  CStringT:: ~ CStringT

Yok eder `CStringT` nesne.

```
~CStringT() throw();
```

### <a name="remarks"></a>Açıklamalar

Yok eder `CStringT` nesne.

##  <a name="delete"></a>  CStringT::Delete

Bir karakteri veya karakterleri bir dizeden belirtilen dizindeki karakteri ile başlayan siler.

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>Parametreler

*İIndex*<br/>
İlk karakter, sıfır tabanlı dizini `CStringT` silmek için nesne.

*nCount*<br/>
Kaldırılacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen dizenin uzunluğu.

### <a name="remarks"></a>Açıklamalar

Varsa *nCount* dize, dize geri kalanını kaldırılacak daha uzun.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

##  <a name="find"></a>  CStringT::Find

Bu dize için bir karakter veya alt dizenin ilk eşleşme arar.

```
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>Parametreler

*pszSub*<br/>
Aranacak alt dize.

*iStart*<br/>
Arama kullanmaya başlamak için dize veya baştan başlamanız için 0 karakter dizini.

*ch*<br/>
Aranacak tek bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Bu ilk karakterin sıfır tabanlı dizini `CStringT` nesnesini, istenen alt dize veya karakter ile eşleşir; bir alt dize veya karakter bulunmazsa -1.

### <a name="remarks"></a>Açıklamalar

İşlevin hem tek karakterleri kabul etmek için aşırı yüklenmiş (çalışma zamanı işlevine benzer `strchr`) ve dizeleri (benzer şekilde `strstr`).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

##  <a name="findoneof"></a>  CStringT::FindOneOf

Bu dize içindeki herhangi bir karakterle eşleşen ilk karakter için arar *pszCharSet*.

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>Parametreler

*pszCharSet*<br/>
Eşleşen karakterler içeren dize.

### <a name="return-value"></a>Dönüş Değeri

De erişilebilir bu dizedeki ilk karakter sıfır tabanlı dizini *pszCharSet*; eşleşme yoksa -1.

### <a name="remarks"></a>Açıklamalar

İlk karakterleri oluşumunu bulur *pszCharSet*.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

##  <a name="format"></a>  CStringT::Format

Biçimlendirilmiş verileri Yazar bir `CStringT` aynı şekilde [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) veri C stili karakter dizisi olarak biçimlendirir.

```
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>Parametreler

*nFormatID*<br/>
Biçim Denetimi dizesi içeren dize kaynak kimliği.

*pszFormat*<br/>
Bir biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

Bu işlev biçimlendirir ve bir dizi karakter ve değerlerini depolar `CStringT`. Her isteğe bağlı bağımsız değişken (varsa) dönüştürülür ve karşılık gelen kapsamındaki biçim belirtimine göre çıkışı *pszFormat* veya dize kaynağı tarafından tanımlanan *nFormatID*.

Dize nesnesi bir parametre olarak sunulan çağrı başarısız olur `Format`. Örneğin, aşağıdaki kod, öngörülemeyen sonuçlara neden olur:

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

Daha fazla bilgi için [biçim belirtim Sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

##  <a name="formatmessage"></a>  CStringT::FormatMessage

Bir ileti dizesi olarak biçimlendirir.

```
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>Parametreler

*nFormatID*<br/>
Biçimlendirilmemiş ileti metni içeren dize kaynak kimliği.

*pszFormat*<br/>
Biçim Denetimi dizesi işaret eder. Ekler için taranır ve uygun şekilde biçimlendirilmiş. Çalışma zamanı işlevine benzer bir biçim dizesi *printf*-stil biçim dizeleri dışında bir rastgele sırayla eklenecek parametre sağlar.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

İşlevi, giriş olarak bir ileti tanımı gerektirir. İleti tanımı tarafından belirlenen *pszFormat* veya dize kaynağı tarafından tanımlanan *nFormatID*. Biçimlendirilmiş ileti metni işlevi kopyalar `CStringT` herhangi katıştırılmış işleme nesnesi, dizileri istediyseniz Ekle.

> [!NOTE]
> `FormatMessage` Yeni bir biçimlendirilmiş dize için sistem belleği ayırmaya çalışır. Bu girişim başarısız olursa, bir bellek özel durumu otomatik olarak oluşturulur.

Her INSERT karşılık gelen bir parametre aşağıdaki olmalıdır *pszFormat* veya *nFormatID* parametresi. İleti metni içinde ileti dinamik olarak biçimlendirmek için çeşitli kaçış dizileri desteklenir. Daha fazla bilgi için bkz. Windows [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) Windows SDK'sında işlev.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

##  <a name="formatmessagev"></a>  CStringT::FormatMessageV

Değişken bağımsız değişken listesini kullanarak bir ileti dizesi olarak biçimlendirir.

```
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçim Denetimi dizesi işaret eder. Ekler için taranır ve uygun şekilde biçimlendirilmiş. Çalışma zamanı işlevine benzer bir biçim dizesi `printf`-stil biçim dizeleri dışında bir rastgele sırayla eklenecek parametre sağlar.

*pArgList*<br/>
Bağımsız değişkenler listesine işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevi, giriş olarak bir ileti tanımı gerektirir tarafından belirlenen *pszFormat*. Biçimlendirilmiş ileti metni ve bağımsız değişken listesi işlevi kopyalar `CStringT` herhangi katıştırılmış işleme nesnesi, dizileri istediyseniz Ekle.

> [!NOTE]
> `FormatMessageV` çağrıları [CStringT::FormatMessage](#formatmessage), yeni biçimlendirilmiş dize için sistem belleği ayırmaya çalışır. Bu girişim başarısız olursa, bir bellek özel durumu otomatik olarak oluşturulur.

Daha fazla bilgi için bkz. Windows [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) Windows SDK'sında işlev.

##  <a name="formatv"></a>  CStringT::FormatV

Değişken bağımsız değişken listesini kullanarak bir ileti dizesi olarak biçimlendirir.

```
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçim Denetimi dizesi işaret eder. Ekler için taranır ve uygun şekilde biçimlendirilmiş. Çalışma zamanı işlevine benzer bir biçim dizesi `printf`-stil biçim dizeleri dışında bir rastgele sırayla eklenecek parametre sağlar.

*bağımsız değişken*<br/>
Bağımsız değişkenler listesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken listesini ve biçimlendirilmiş bir dize yazar bir `CStringT` aynı dize biçimi `vsprintf_s` veri C stili karakter dizisi olarak biçimlendirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

##  <a name="getenvironmentvariable"></a>  CStringT::GetEnvironmentVariable

Dize değeri olarak belirtilen ortam değişkenini ayarlar.

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>Parametreler

*pszVar*<br/>
Belirtir ortam değişkeninin null ile sonlandırılmış bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen değişkenin değerini çağırma işleminin ortam bloğundan alır. Değeri null ile sonlandırılmış bir dize karakter biçimindedir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

##  <a name="insert"></a>  CStringT::Insert

Tek bir karakter veya bir alt dizeyi dizenin içinde belirtilen dizini ekler.

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>Parametreler

*İIndex*<br/>
Önce ekleme yer alacak karakter dizini.

*psz*<br/>
Eklenecek alt dize işaretçisi.

*ch*<br/>
Eklenecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen dizenin uzunluğu.

### <a name="remarks"></a>Açıklamalar

*İIndex* parametresi karakter veya alt dize yer taşınacak ilk karakter tanımlar. Varsa *nIndex* ekleme dizenin tamamını önce ortaya çıkar sıfırdır. Varsa *nIndex* mevcut dize işlevi dizenin uzunluğunu birleştirir ve yeni malzeme ya da sağlanan daha büyük olduğu *ch* veya *psz*.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

##  <a name="left"></a>  CStringT::Left

En soldaki *nCount* bu karakterleri `CStringT` nesne ve çıkartılan alt dizenin bir kopyasını döndürür.

```
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>Parametreler

*nCount*<br/>
Ayıklanacak karakter sayısı `CStringT` nesne.

### <a name="return-value"></a>Dönüş Değeri

A `CStringT` belirtilen karakter aralığının bir kopyasını içeren nesne. Döndürülen `CStringT` nesnesi boş olabilir.

### <a name="remarks"></a>Açıklamalar

Varsa *nCount* dize uzunluğunu aşarsa, ardından tüm dize ayıklanır. `Left` Temel benzer `Left` işlevi.

Çok baytlı karakter kümeleri (MBCS) için *nCount* her 8-bit sırayı bir karakter olarak değerlendirir. böylece *nCount* iki ile çarpılmış çok baytlı karakter sayısını döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

##  <a name="loadstring"></a>  CStringT::LoadString

Okur ile tanımlanan bir Windows dize kaynağı *nID*, mevcut bir uygulamasına `CStringT` nesne.

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Modülün örneği için bir tanıtıcı.

*nID*<br/>
Bir Windows dize kaynak kimliği

*wLanguageID*<br/>
Dize kaynağının dili.

### <a name="return-value"></a>Dönüş Değeri

Kaynak yükleme başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Dize kaynağını yükler (*nID*) belirtilen modülündeki (*HINSTANCE*) belirtilen dili kullanarak (*wLanguage*).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

##  <a name="makelower"></a>  CStringT::MakeLower

Dönüştürür `CStringT` küçük harf dize nesnesine.

```
CStringT& MakeLower();
```

### <a name="return-value"></a>Dönüş Değeri

Sonuçta elde edilen küçük harf dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

##  <a name="makereverse"></a>  CStringT::MakeReverse

İçindeki karakterlerin sırasını tersine çevirir `CStringT` nesne.

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>Dönüş Değeri

Sonuç dizesi ters.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

##  <a name="makeupper"></a>  CStringT::MakeUpper

Dönüştürür `CStringT` büyük bir dize nesnesi.

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>Dönüş Değeri

Sonuç büyük harf dizesi.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

##  <a name="mid"></a>  CStringT::Mid

Bir dizenin uzunluğu ayıklar *nCount* bu karakterler `CStringT` konumunda başlayan nesnenin *iFirst* (sıfır tabanlı).

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>Parametreler

*iFirst*<br/>
Bu ilk karakterin sıfır tabanlı dizini `CStringT` ve çıkartılan alt dizenin içinde bulunan nesne.

*nCount*<br/>
Ayıklanacak karakter sayısı `CStringT` nesne. Ardından bu parametre sağlanmazsa, geri kalanında dize ayıklanır.

### <a name="return-value"></a>Dönüş Değeri

A `CStringT` belirtilen karakter aralığının bir kopyasını içeren nesne. Unutmayın döndürülen `CStringT` nesnesi boş olabilir.

### <a name="remarks"></a>Açıklamalar

İşlev ve çıkartılan alt dizenin bir kopyasını döndürür. `Mid` (temel dizinlerde tabanlı) temel Mid işlevine benzer.

Çok baytlı karakter kümeleri (MBCS) için *nCount* her 8-bit karakter; diğer bir deyişle, bir ön ve baytlık bir çok baytlı karakter iki karakter olarak sayılır ifade eder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

##  <a name="oemtoansi"></a>  CStringT::OemToAnsi

Bu tüm karakterleri dönüştürür `CStringT` OEM karakter ANSI karakter kümesine kümesindeki nesne.

```
void OemToAnsi();
```

### <a name="remarks"></a>Açıklamalar

_UNICODE tanımlanmış olması durumunda, bu işlev kullanılamıyor.

### <a name="example"></a>Örnek

Örneğin bakın [CStringT::AnsiToOem](#ansitooem).

##  <a name="operator_add"></a>  CStringT::operator +

İki dizeyi veya bir karakter ve dize art arda ekler.

```
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```

### <a name="parameters"></a>Parametreler

*ch1*<br/>
Bir dize ile birleştirmek için bir ANSI veya Unicode karakter.

*Ch2*<br/>
Bir dize ile birleştirmek için bir ANSI veya Unicode karakter.

*str1*<br/>
A `CStringT` bir dize veya karakter ile birleştirilecek.

*str2*<br/>
A `CStringT` bir dize veya karakter ile birleştirilecek.

*psz1*<br/>
Bir dize veya karakter ile birleştirmek için null ile sonlandırılmış dizeye bir işaretçi.

*psz2*<br/>
Bir dize veya karakter ile birleştirmek için bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Yedi aşırı yük biçimleri vardır `CStringT::operator+` işlevi. İlk sürüm iki varolan art arda ekler `CStringT` nesneleri. Sonraki iki Birleştir bir `CStringT` nesnesi ve bir null ile sonlandırılmış dize. Sonraki iki Birleştir bir `CStringT` nesnesi ve bir ANSI karakter. Son iki Birleştir bir `CStringT` nesnesi ve bir Unicode karakter.

> [!NOTE]
>  Oluşturmak mümkün olsa da `CStringT` gömülü null karakterleri içeren örnekleri, karşı öneririz. Yöntemleri ve işleçleri çağırma `CStringT` gömülü null karakterleri içeren nesneleri, istenmeyen sonuçlar üretebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

##  <a name="operator_add_eq"></a>  CStringT::operator +=

Dizenin sonuna karakterler art arda ekler.

```
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

*str*<br/>
Bir başvuru bir `CThisSimpleString` nesne.

*bMFCDLL*<br/>
Proje MFC DLL olup olmadığını belirten bir Boole değeri.

*BaseType*<br/>
Dize temel türü.

*var*<br/>
Bu dizeye bitiştirmek için bir VARIANT nesnesi.

*ch*<br/>
Bir dize ile birleştirmek için bir ANSI veya Unicode karakter.

*pszSrc*<br/>
Birleştirilmiş özgün dizeye yönelik işaretçi.

*strSrc*<br/>
A `CStringT` Bu dizeye bitiştirmek için.

### <a name="remarks"></a>Açıklamalar

Başka bir işleç kabul `CStringT` nesnesi, bir karakter işaretçisi veya tek bir karakter. Bilmeniz gereken özel durumlar için bu eklenen karakter için yeni depolama ayrılmış olduğundan, bu birleştirme işleci kullandığınızda meydana gelebilir belleğin `CStringT` nesne.

Hakkında bilgi için `CThisSimpleString`, Açıklamalar bölümüne bakın [CStringT::CStringT](#cstringt).

> [!NOTE]
>  Oluşturmak mümkün olsa da `CStringT` gömülü null karakterleri içeren örnekleri, karşı öneririz. Yöntemleri ve işleçleri çağırma `CStringT` gömülü null karakterleri içeren nesneleri, istenmeyen sonuçlar üretebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

##  <a name="operator_eq_eq"></a>  CStringT::operator ==

İki dizenin mantıksal olarak eşit olup olmadığını belirler.

```
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>Parametreler

*ch1*<br/>
Karşılaştırma için bir ANSI veya Unicode karakter.

*Ch2*<br/>
Karşılaştırma için bir ANSI veya Unicode karakter.

*str1*<br/>
A `CStringT` karşılaştırma için.

*str2*<br/>
A `CStringT` karşılaştırma için.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış dizeye bir işaretçi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış dizeye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir dize veya karakter sol tarafındaki bir dize veya karakter işlecin sağ tarafındaki eşittir ve TRUE veya false değerini uygun döndürür olup olmadığını sınar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

##  <a name="operator_neq"></a>  CStringT::operator! =

İki dizenin eşit olup mantıksal olarak olup olmadığını belirler.

```
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>Parametreler

*ch1*<br/>
Bir dize ile birleştirmek için bir ANSI veya Unicode karakter.

*Ch2*<br/>
Bir dize ile birleştirmek için bir ANSI veya Unicode karakter.

*str1*<br/>
A `CStringT` karşılaştırma için.

*str2*<br/>
A `CStringT` karşılaştırma için.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış dizeye bir işaretçi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış dizeye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir dize veya karakter sol tarafındaki bir dize veya karakter işlecin sağ tarafındaki eşit olup olmadığını sınar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

##  <a name="operator_lt"></a>  CStringT::operator &lt;

İşlecin sol tarafındaki dizeyi dizenin sağ tarafındaki küçüktür olup olmadığını belirler.

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
A `CStringT` karşılaştırma için.

*str2*<br/>
A `CStringT` karşılaştırma için.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış dizeye bir işaretçi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış dizeye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Lexicographical karşılaştırma dizeleri, karakter kadar arasında:

- İki karşılık gelen karakterler eşit bulur ve bunların karşılaştırma sonucu dizeleri arasındaki Karşılaştırmanın sonucu olarak alınır.

- Hiçbir inequalities bulur, ancak bir dizeye uzun dize değerinden karakterlerden diğer ve kısa dize olarak kabul edilir daha fazlasına sahip.

- Bu, hiçbir inequalities ve aynı sayıda karakter dizelerine sahipsiniz ve bu nedenle dizelerin eşit olup bulur bulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

##  <a name="operator_gt"></a>  CStringT::operator &gt;

İşlecin sol tarafındaki dizeyi dizenin sağ tarafındaki büyük olup olmadığını belirler.

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
A `CStringT` karşılaştırma için.

*str2*<br/>
A `CStringT` karşılaştırma için.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış dizeye bir işaretçi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış dizeye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Lexicographical karşılaştırma dizeleri, karakter kadar arasında:

- İki karşılık gelen karakterler eşit bulur ve bunların karşılaştırma sonucu dizeleri arasındaki Karşılaştırmanın sonucu olarak alınır.

- Hiçbir inequalities bulur, ancak bir dizeye uzun dize değerinden karakterlerden diğer ve kısa dize olarak kabul edilir daha fazlasına sahip.

- Bulduğu hiçbir inequalities ve dizeler eşit olacak şekilde aynı sayıda karakter dizeleri olduğunu bulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

##  <a name="operator_lt_eq"></a>  CStringT::operator &lt;=

İşlecin sol tarafındaki dize ya da dize işlecin sağ tarafındaki eşit olup olmadığını belirler.

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
A `CStringT` karşılaştırma için.

*str2*<br/>
A `CStringT` karşılaştırma için.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış dizeye bir işaretçi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış dizeye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Lexicographical karşılaştırma dizeleri, karakter kadar arasında:

- İki karşılık gelen karakterler eşit bulur ve bunların karşılaştırma sonucu dizeleri arasındaki Karşılaştırmanın sonucu olarak alınır.

- Hiçbir inequalities bulur, ancak bir dizeye uzun dize değerinden karakterlerden diğer ve kısa dize olarak kabul edilir daha fazlasına sahip.

- Bulduğu hiçbir inequalities ve dizeler eşit olacak şekilde aynı sayıda karakter dizeleri olduğunu bulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

##  <a name="operator_gt_eq"></a>  CStringT::operator &gt;=

İşlecin sol tarafındaki dize değerinden büyük veya işlecin sağ tarafındaki bir dizeye eşit olup olmadığını belirler.

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
A `CStringT` karşılaştırma için.

*str2*<br/>
A `CStringT` karşılaştırma için.

*psz1*<br/>
Karşılaştırma için bir dize işaretçisi.

*psz2*<br/>
Karşılaştırma için bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Lexicographical karşılaştırma dizeleri, karakter kadar arasında:

- İki karşılık gelen karakterler eşit bulur ve bunların karşılaştırma sonucu dizeleri arasındaki Karşılaştırmanın sonucu olarak alınır.

- Hiçbir inequalities bulur, ancak bir dizeye uzun dize değerinden karakterlerden diğer ve kısa dize olarak kabul edilir daha fazlasına sahip.

- Bulduğu hiçbir inequalities ve dizeler eşit olacak şekilde aynı sayıda karakter dizeleri olduğunu bulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

##  <a name="remove"></a>  CStringT::Remove

Belirtilen karakterin tüm örneklerini dizeden kaldırır.

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>Parametreler

*chRemove*<br/>
Bir dizeden kaldırılacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Karakter sayısı dizeden kaldırıldı. Sıfır dize değiştirilmez.

### <a name="remarks"></a>Açıklamalar

Karakter karşılaştırma büyük/küçük harfe duyarlıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

##  <a name="replace"></a>  CStringT::Replace

İki sürümü vardır `Replace`. İlk sürüm, başka bir alt dizesi kullanarak bir alt dizenin bir veya daha fazla kopyasını değiştirir. Her iki alt dize null ile sonlandırılmış. Dosyanın ikinci sürümü, başka bir karakter kullanarak bir karakteri bir veya daha fazla kopyasını değiştirir. Her iki sürümü depolanan karakter verileri çalışan `CStringT`.

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>Parametreler

*pszOld*<br/>
Değiştirilmesi için null ile sonlandırılmış dizeye bir işaretçi *pszNew*.

*pszNew*<br/>
Yerini alan bir null ile sonlandırılmış dizeye bir işaretçi *pszOld*.

*chOld*<br/>
Karakter değiştirilmesi *chNew*.

*chNew*<br/>
Değiştirme karakteri *chOld*.

### <a name="return-value"></a>Dönüş Değeri

Dize değişmez karakter veya alt ya da sıfır değiştirilen örnek sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

`Replace` dize uzunluğu nedeniyle değiştirebilirsiniz *pszNew* ve *pszOld* aynı uzunlukta olması gerekmez ve eski alt dizenin çok sayıda kopya için yeni bir tane değiştirilebilir. İşlevi, büyük küçük harfe duyarlı bir eşleşme gerçekleştirir.

Örnekleri `CStringT` örnekleri `CString`, `CStringA`, ve `CStringW`.

İçin `CStringA`, `Replace` ANSI veya çok baytlı (MBCS) karakteri ile çalışır. İçin `CStringW`, `Replace` geniş karakterler ile çalışır.

İçin `CString`, karakter veri türü, aşağıdaki tabloda sabitlerle tanımlanan göre derleme zamanında belirlenir.

|Tanımlanan sabiti|Karakter veri türü|
|----------------------|-------------------------|
|_UNICODE|Geniş karakterler|
|_MBCS|Çok baytlı karakter|
|Ne|Tek baytlı karakter|
|Her ikisi de|Tanımlanmadı|

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

##  <a name="reversefind"></a>  CStringT::ReverseFind

Bu arar `CStringT` son eşleşmenin bir karakter için nesne.

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>Parametreler

*ch*<br/>
Aranacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Bu son karakter sıfır tabanlı dizini `CStringT` karakter bulunmazsa, istenen karakter veya -1 ile eşleşen bir nesne.

### <a name="remarks"></a>Açıklamalar

İşlev çalışma zamanı işlevine benzer `strrchr`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

##  <a name="right"></a>  CStringT::Right

Son ayıklar (diğer bir deyişle, en sağdaki) *nCount* bu karakterleri `CStringT` nesne ve çıkartılan alt dizenin bir kopyasını döndürür.

```
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>Parametreler

*nCount*<br/>
Ayıklanacak karakter sayısı `CStringT` nesne.

### <a name="return-value"></a>Dönüş Değeri

A `CStringT` belirtilen karakter aralığının bir kopyasını içeren nesne. Unutmayın döndürülen `CStringT` nesnesi boş olabilir.

### <a name="remarks"></a>Açıklamalar

Varsa *nCount* dize uzunluğunu aşarsa, ardından tüm dize ayıklanır. `Right` Temel benzer `Right` (Basic dizinler sıfır tabanlıdır, dışında) işlev.

Çok baytlı karakter kümeleri (MBCS) için *nCount* her 8-bit karakter; diğer bir deyişle, bir ön ve baytlık bir çok baytlı karakter iki karakter olarak sayılır ifade eder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

##  <a name="setsysstring"></a>  CStringT::SetSysString

İşaret ettiği BSTR yeniden tahsis ederse *pbstr* ve içeriğini kopyalar `CStringT` NULL karakteri de dahil olmak üzere, nesneye.

```
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>Parametreler

*pbstr*<br/>
Bir karakter dizesine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir dize.

### <a name="remarks"></a>Açıklamalar

İçeriğine bağlı olarak `CStringT` nesnesi, değeri tarafından başvurulan BSTR *pbstr* değiştirebilirsiniz. İşlevin bir `CMemoryException` yetersiz bellek varsa.

Bu işlev, normalde Otomasyon için başvuruya göre geçirilen dize değeri değiştirmek için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

##  <a name="spanexcluding"></a>  CStringT::SpanExcluding

Karakter dizesinden tarafından tanımlanan karakter kümesine olmayan ilk karakter'ile başlayan ayıklar *pszCharSet*.

```
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Parametreler

*pszCharSet*<br/>
Bir dize karakter kümesi yorumlanır.

### <a name="return-value"></a>Dönüş Değeri

Dize olmayan karakter içeren bir alt dizenin *pszCharSet*, dizenin ilk karakteri ile başlayan ve de erişilebilir bir dizede bulunan ilk karakteri ile biten *pszCharSet* (diğer bir deyişle, ilk karakter dizesi ve kadar ancak hariç, bulunan dizenin ilk karakteri ile başlayan *pszCharSet*). Hiçbir karakteri, dizenin tamamını döndürür *pszCharSet* dizesinde bulunamadı.

### <a name="remarks"></a>Açıklamalar

`SpanExcluding` ayıklar ve bir karakterin ilk geçtiği önceki tüm karakterleri döndürür *pszCharSet* (diğer bir deyişle, karakter *pszCharSet* ve tüm karakterleri dizesinde aşağıdaki değildir döndürülen). Hiçbir karakter varsa *pszCharSet* dizesinde sonra bulunan `SpanExcluding` tüm dizeyi döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

##  <a name="spanincluding"></a>  CStringT::SpanIncluding

Karakter dizesinden tarafından tanımlanan karakter kümesine bulunan ilk karakteri ile başlayan ayıklar *pszCharSet*.

```
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Parametreler

*pszCharSet*<br/>
Bir dize karakter kümesi yorumlanır.

### <a name="return-value"></a>Dönüş Değeri

Bulunan dizenin karakter içeren bir alt dizesi *pszCharSet*, dizenin ilk karakteri ile başlayan ve kullanımda olmayan dizesindeki bir karakter bulunduğunda bitiş *pszCharSet*. `SpanIncluding` ilk karakterin dizede belirtilen kümede değilse boş bir alt dizeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Dizenin ilk karakteri karakter kümesinde ardından değilse `SpanIncluding` boş bir dize döndürür. Aksi takdirde, bir dizi kümededir ardışık karakteri döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

##  <a name="tokenize"></a>  CStringT::Tokenize

Hedef dizesi içinde sonraki belirteç bulur

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>Parametreler

*pszTokens*<br/>
Belirteç ayırıcılar içeren bir dize. Bu sınırlayıcı sırası önemli değildir.

*iStart*<br/>
Aramaya başlamak için sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

A `CStringT` geçerli belirteç değeri içeren nesne.

### <a name="remarks"></a>Açıklamalar

`Tokenize` İşlevi hedef dizesi içinde sonraki belirtece bulur. Karakter kümesi *pszTokens* bulunma belirtecin olası sınırlayıcılar belirtir. Her çağrıda `Tokenize` işlevi başlar *iStart*, önde gelen sınırlayıcılar atlar ve döndüren bir `CStringT` sonraki sınırlayıcı karakteri en fazla karakter dizesi geçerli belirteç içeren nesne. Değerini *iStart* dizenin bitiminden ulaştıysanız bitiş sınırlayıcı karakter veya -1 Aşağıdaki konum olacak şekilde güncelleştirildi. Daha fazla belirteçleri, hedef dizenin geri kalanı dışında bir dizi çağrıda tarafından bölünebilir `Tokenize`kullanarak *iStart* sonraki belirteçtir okumak için dize nerede izlemek için. Başka belirteç olduğunda işlev boş bir dize döndürür ve *iStart* -1 olarak ayarlanır.

CRT işlevleri gibi simgeleştirin [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` hedef dizesi değiştirmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>Açıklamalar

Bu örnek çıktısı aşağıdaki gibidir:

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

##  <a name="trim"></a>  CStringT::Trim

Baştaki ve sondaki karakterler dizesinden kırpar.

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>Parametreler

*chTarget*<br/>
Kırpılmış olması için hedef karakter.

*pszTargets*<br/>
Kırpılmış olması için hedef karakterleri içeren bir dize işaretçisi. Tüm öndeki ve sondaki karakterler oluşumunu *pszTarget* gelen kırpılacak `CStringT` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bölünen dize döndürür.

### <a name="remarks"></a>Açıklamalar

Tüm öndeki ve sondaki aşağıdakilerden birini kaldırır:

- Tarafından belirtilen karakter *chTarget*.

- Tarafından belirtilen dizede bulunan tüm karakter *pszTargets*.

- Boşluk.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>Açıklamalar

Bu örnek çıktısı aşağıdaki gibidir:

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

##  <a name="trimleft"></a>  CStringT::TrimLeft

Dizeden baştaki kırpar.

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>Parametreler

*chTarget*<br/>
Kırpılmış olması için hedef karakter.

*pszTargets*<br/>
Kırpılmış olması için hedef karakterleri içeren bir dize işaretçisi. Karakter önde gelen tüm oluşumlarını *pszTarget* gelen kırpılacak `CStringT` nesne.

### <a name="return-value"></a>Dönüş Değeri

Sonuçta elde edilen bölünen dize.

### <a name="remarks"></a>Açıklamalar

Tüm öndeki ve sondaki aşağıdakilerden birini kaldırır:

- Tarafından belirtilen karakter *chTarget*.

- Tarafından belirtilen dizede bulunan tüm karakter *pszTargets*.

- Boşluk.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

##  <a name="trimright"></a>  CStringT::TrimRight

Sondaki karakterler dizesinden kırpar.

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>Parametreler

*chTarget*<br/>
Kırpılmış olması için hedef karakter.

*pszTargets*<br/>
Kırpılmış olması için hedef karakterleri içeren bir dize işaretçisi. Tüm karakterleri oluşumunu sondaki *pszTarget* gelen kırpılacak `CStringT` nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `CStringT` bölünen dize içeren nesne.

### <a name="remarks"></a>Açıklamalar

Sondaki aşağıdakilerden birini oluşumlarını kaldırır:

- Tarafından belirtilen karakter *chTarget*.

- Tarafından belirtilen dizede bulunan tüm karakter *pszTargets*.

- Boşluk.

`CStringT& TrimRight(XCHAR chTarget)` Sürümü bir karakter parametresini kabul edip bu karakteri tüm kopyalarını sonundan başlayarak kaldırır `CStringT` dize verileri. Bu dizenin sonundan başlar ve öne doğru çalışır. Farklı bir karakter bulduğunda ya da zaman durdurur `CSTringT` karakter verileri dışında çalışır.

`CStringT& TrimRight(PCXSTR pszTargets)` Sürümü aramak için farklı tüm karakterleri içeren null ile sonlandırılmış bir dize kabul eder. Tüm kopyalarını karakterleri kaldırır `CStringT` nesne. Bu dizenin sonunda başlar ve öne doğru çalışır. Hedef dizesi içinde olmayan bir karakter bulduğunda ya da zaman durdurur `CStringT` karakter verileri dışında çalışır. Bir alt dizenin sonunda, tüm hedef dizeye eşleşecek şekilde denemez `CStringT`.

`CStringT& TrimRight()` Parametresiz sürümünü gerektirir. Sondaki boşluk karakterlerini sonundaki kırpar `CStringT` dize. Boşluk karakterler satır sonu, boşluk veya sekme olabilir.

-

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[CSimpleStringT Sınıfı](../../atl-mfc-shared/reference/csimplestringt-class.md)
