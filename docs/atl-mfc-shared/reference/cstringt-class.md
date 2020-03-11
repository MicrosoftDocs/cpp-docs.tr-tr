---
title: CStringT sınıfı
ms.date: 03/27/2019
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
ms.openlocfilehash: a411ed54a73a0dee49ebbd9ccacbd7c6f8e69ca5
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856319"
---
# <a name="cstringt-class"></a>CStringT sınıfı

Bu sınıf bir `CStringT` nesnesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>Parametreler

*BaseType*<br/>
Dize sınıfının karakter türü. Aşağıdakilerden biri olabilir:

- **char** (ANSI karakter dizeleri için).

- **wchar_t** (Unicode karakter dizeleri için).

- TCHAR (hem ANSI hem de Unicode karakter dizeleri için).

*Stringnitelikler*<br/>
Dize sınıfının C çalışma zamanı (CRT) kitaplık desteğinin gerekip gerekmediğini ve dize kaynaklarının nerede olduğunu belirler. Aşağıdakilerden biri olabilir:

- **Strtralictl < wchar_t** &#124; **char** &#124; **tchar, ChTraitsCRT < wchar_t** &#124; **char** &#124; **TCHAR > >**

   Sınıfı, CRT desteği gerektirir ve `m_hInstResource` (uygulamanın modül sınıfının bir üyesi) tarafından belirtilen modülde kaynak dizeleri arar.

- **Strtralictl < wchar_t** &#124; **char** &#124; **tchar, chtraitsos < wchar_t** &#124; **char** &#124; **TCHAR > >**

   Sınıf, `m_hInstResource` (uygulamanın modül sınıfının bir üyesi) tarafından belirtilen modülde CRT desteği ve arama gerektirmez.

- **StrTraitMFC < wchar_t** &#124; **char** &#124; **tchar, ChTraitsCRT < wchar_t** &#124; **char** &#124; **TCHAR > >**

   Sınıfı CRT desteği gerektirir ve standart MFC arama algoritmasını kullanarak kaynak dizeleri arar.

- **StrTraitMFC < wchar_t** &#124; **char** &#124; **tchar, chtraitsos < wchar_t** &#124; **char** &#124; **TCHAR > >**

   Sınıfı, standart MFC arama algoritmasını kullanarak, CRT desteği gerektirmez ve kaynak dizeleri arar.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CStringT:: CStringT](#cstringt)|Çeşitli yollarla `CStringT` nesnesi oluşturur.|
|[CStringT:: ~ CStringT](#_dtorcstringt)|`CStringT` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStringT:: AllocSysString](#allocsysstring)|`CStringT` verilerinden bir BSTR ayırır.|
|[CStringT:: Ansıtooem](#ansitooem)|ANSI karakter kümesinden OEM karakter kümesine yerinde dönüştürme yapar.|
|[CStringT:: AppendFormat](#appendformat)|Biçimlendirilen verileri varolan bir `CStringT` nesnesine ekler.|
|[CStringT:: COLLATE](#collate)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarlı, yerel ayara özgü bilgiler kullanır).|
|[CStringT:: CollateNoCase](#collatenocase)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarsız, yerel ayara özgü bilgileri kullanır).|
|[CStringT:: Compare](#compare)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarlı).|
|[CStringT:: CompareNoCase](#comparenocase)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarsız).|
|[CStringT::D Sil](#delete)|Dizeden bir karakter veya karakter siler.|
|[CStringT:: Find](#find)|Daha büyük bir dizenin içinde bir karakter veya alt dize bulur.|
|[CStringT:: FindOneOf](#findoneof)|Bir kümeden ilk eşleşen karakteri bulur.|
|[CStringT:: Format](#format)|Dizeyi `sprintf` olarak biçimlendirir.|
|[CStringT:: FormatMessage](#formatmessage)|Bir ileti dizesini biçimlendirir.|
|[CStringT:: FormatMessageV](#formatmessagev)|Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.|
|[CStringT:: FormatV](#formatv)|Dizeyi değişken bir bağımsız değişken listesi kullanarak biçimlendirir.|
|[CStringT:: GetEnvironmentVariable](#getenvironmentvariable)|Dizeyi belirtilen ortam değişkeninin değerine ayarlar.|
|[CStringT:: INSERT](#insert)|Dize içindeki verilen dizine tek bir karakter veya alt dize ekler.|
|[CStringT:: Left](#left)|Bir dizenin sol kısmını ayıklar.|
|[CStringT:: LoadString](#loadstring)|Varolan bir `CStringT` nesnesini bir Windows kaynağından yükler.|
|[CStringT:: MakeLower](#makelower)|Bu dizedeki tüm karakterleri küçük harfe dönüştürür.|
|[CStringT:: MakeReverse](#makereverse)|Dizeyi tersine çevirir.|
|[CStringT:: MakeUpper](#makeupper)|Bu dizedeki tüm karakterleri büyük harfli karakterlere dönüştürür.|
|[CStringT:: Mid](#mid)|Bir dizenin orta kısmını ayıklar.|
|[CStringT:: OemToAnsi](#oemtoansi)|OEM karakter kümesinden ANSI karakter kümesine yerinde dönüştürme yapar.|
|[CStringT:: Remove](#remove)|Bir dizeden belirtilen karakterleri kaldırır.|
|[CStringT:: Replace](#replace)|Belirtilen karakterleri diğer karakterlerle değiştirir.|
|[CStringT:: Smarfind](#reversefind)|Daha büyük bir dizenin içinde bir karakter bulur; uçtan başlar.|
|[CStringT:: Right](#right)|Bir dizenin sağ kısmını ayıklar.|
|[CStringT:: SetSysString](#setsysstring)|Varolan bir BSTR nesnesini `CStringT` nesnesinden verilerle ayarlar.|
|[CStringT:: Spanhariç tutma](#spanexcluding)|`pszCharSet`tarafından tanımlanan karakter kümesinde olmayan, ilk karakterle başlayarak dizeden karakter ayıklar.|
|[CStringT:: Spandahil](#spanincluding)|Yalnızca bir küme içindeki karakterleri içeren bir alt dize ayıklar.|
|[CStringT:: tokenize](#tokenize)|Belirtilen belirteçleri bir hedef dizede ayıklar.|
|[CStringT:: trim](#trim)|Dizedeki tüm baştaki ve sondaki boşluk karakterlerini kırpar.|
|[CStringT:: kırıt sola](#trimleft)|Dizeden öndeki boşluk karakterlerini kırpar.|
|[CStringT:: kırma sağ](#trimright)|Dizeden sondaki boşluk karakterlerini kırpar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[CStringT:: operator =](#operator_eq)|`CStringT` nesnesine yeni bir değer atar.|
|[CStringT:: operator +](#operator_add)|İki dizeyi veya bir karakteri ve dizeyi birleştirir.|
|[CStringT:: operator + =](#operator_add_eq)|Varolan bir dizenin sonuna yeni bir dize ekler.|
|[CStringT:: operator = =](#operator_eq_eq)|İki dizenin mantıksal olarak eşit olup olmadığını belirler.|
|[CStringT:: operator! =](#operator_neq)|İki dizenin mantıksal olarak eşit olup olmadığını belirler.|
|[CStringT:: operator &lt;](#operator_lt)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha az olup olmadığını belirler.|
|[CStringT:: operator &gt;](#operator_gt)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha büyük olup olmadığını belirler.|
|[CStringT:: operator &lt;=](#operator_lt_eq)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden küçük veya ona eşit olup olmadığını belirler.|
|[CStringT:: operator &gt;=](#operator_gt_eq)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden büyük veya ona eşit olup olmadığını belirler.|

## <a name="remarks"></a>Açıklamalar

`CStringT` [CSimpleStringT sınıfından](../../atl-mfc-shared/reference/csimplestringt-class.md)devralır. Karakter işleme, sıralama ve arama gibi gelişmiş özellikler `CStringT`tarafından uygulanır.

> [!NOTE]
> `CStringT` nesneler özel durumlar atma özelliğine sahiptir. Bu, bir `CStringT` nesnesi herhangi bir nedenden dolayı bellekten tükenmediğinde oluşur.

`CStringT` nesnesi, değişken uzunlukta karakterlerden oluşur. `CStringT`, temel olarak benzer sözdizimini kullanarak işlevler ve işleçler sağlar. Birleştirme ve karşılaştırma işleçleri, Basitleştirilmiş bellek yönetimiyle birlikte `CStringT` nesneleri sıradan karakter dizileri kullanmaktan daha kolay hale getirir.

> [!NOTE]
>  Gömülü null karakterleri içeren `CStringT` örnekleri oluşturmak mümkün olsa da, bunun için önerilir. Katıştırılmış null karakterler içeren `CStringT` nesneler üzerinde Yöntemler ve işleçler çağırma istenmeden sonuçlar verebilir.

`BaseType` ve `StringTraits` parametrelerinin farklı birleşimlerini kullanarak `CStringT` nesneleri, ATL kitaplıkları tarafından önceden tanımlanmış olan aşağıdaki türlerde gelebilir.

Bir ATL uygulamasında kullanıyorsanız:

`CString`, `CStringA`ve `CStringW` MFC DLL 'sinden (MFC90) verilir. DLL), hiçbir şekilde Kullanıcı dll 'lerden değildir. Bu, `CStringT` tanımlanmış olarak çarpmasını engellemek için yapılır.

> [!NOTE]
>  Kodunuz [CStringT kullanarak dize sınıflarını dışarı aktarma](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md)bölümünde açıklanan bağlayıcı hatalarının geçici çözümünü içeriyorsa, bu kodu kaldırmalısınız. Artık buna ihtiyacınız yoktur.

Aşağıdaki dize türleri MFC tabanlı uygulamalar içinde kullanılabilir:

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CStringA`|CRT desteği olan bir ANSI karakter türü dizesi.|
|`CStringW`|CRT desteği olan bir Unicode karakter türü dizesi.|
|`CString`|Yalnızca CRT desteğiyle birlikte ANSI ve Unicode karakter türleri.|

Aşağıdaki dize türleri ATL_CSTRING_NO_CRT tanımlı projelerde kullanılabilir:

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CAtlStringA`|CRT desteği olmayan bir ANSI karakter türü dizesi.|
|`CAtlStringW`|CRT desteği olmayan bir Unicode karakter türü dizesi.|
|`CAtlString`|CRT desteği olmayan ANSI ve Unicode karakter türleri.|

Aşağıdaki dize türleri ATL_CSTRING_NO_CRT tanımlı olmayan projelerde kullanılabilir:

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CAtlStringA`|CRT desteği olan bir ANSI karakter türü dizesi.|
|`CAtlStringW`|CRT desteği olan bir Unicode karakter türü dizesi.|
|`CAtlString`|Yalnızca CRT desteğiyle birlikte ANSI ve Unicode karakter türleri.|

`CString` nesneler aşağıdaki özelliklere de sahiptir:

- `CStringT` nesneler, birleştirme işlemlerinin sonucu olarak büyüyebilir.

- `CStringT` nesneler "değer semantiğini" izler. Bir `CStringT` nesnesini bir dizenin işaretçisi olarak değil, gerçek bir dize olarak düşünün.

- `PCXSTR` işlevi bağımsız değişkenleri için `CStringT` nesneleri ücretsiz olarak kullanabilirsiniz.

- Dize arabellekleri için özel bellek yönetimi. Daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="cstringt-predefined-types"></a>CStringT önceden tanımlanmış türler

`CStringT`, desteklenen karakter türünü ( [wchar_t](../../c-runtime-library/standard-types.md) ya da [char](../../c-runtime-library/standard-types.md)) tanımlamak için bir şablon bağımsız değişkeni kullandığından, yöntem parametre türleri her zaman karmaşık olabilir. Bu sorunu basitleştirmek için, `CStringT` sınıfında bir dizi önceden tanımlanmış tür tanımlanmıştır ve kullanılır. Aşağıdaki tabloda çeşitli türler listelenmektedir:

|Adı|Açıklama|
|----------|-----------------|
|`XCHAR`|`CStringT` nesnesiyle aynı karakter türüne sahip tek bir karakter ( **wchar_t** veya **char**).|
|`YCHAR`|`CStringT` nesnesi olarak karşıt karakter türüne sahip tek bir karakter ( **wchar_t** veya **char**).|
|`PXSTR`|`CStringT` nesnesiyle aynı karakter türüne sahip bir karakter dizesinin ( **wchar_t** veya **char**) bir işaretçisi.|
|`PYSTR`|Bir karakter dizesinin ( **wchar_t** veya **char**) bir işaretçisi, `CStringT` nesnesi olarak karşıt karakter türü.|
|`PCXSTR`|`CStringT` nesnesiyle aynı karakter türüne sahip bir **const** karakter dizesinin ( **wchar_t** veya **char**) bir işaretçisi.|
|`PCYSTR`|Bir **const** karakter dizesinin ( **wchar_t** veya **char**) bir işaretçisi, `CStringT` nesnesi olarak karşıt karakter türü.|

> [!NOTE]
>  Daha önce belgelenmemiş `CString` yöntemlerin (`AssignCopy`gibi) kullandığı kod, aşağıdaki belgelenen `CStringT` yöntemleri kullanan kodla değiştirilmelidir (örneğin `GetBuffer` veya `ReleaseBuffer`). Bu yöntemler `CSimpleStringT`devralınır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>Gereksinimler

|Üst bilgi|Kullanım amacı|
|------------|-------------|
|CStringT. h|Yalnızca MFC dize nesneleri|
|atlstr. h|MFC olmayan dize nesneleri|

##  <a name="allocsysstring"></a>CStringT:: AllocSysString

BSTR türünde bir Otomasyon uyumlu dize ayırır ve sonlandırma null karakteri dahil `CStringT` nesnesinin içeriğini buna kopyalar.

```
BSTR AllocSysString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan dize.

### <a name="remarks"></a>Açıklamalar

MFC programlarında, yetersiz bellek varsa bir [CMemoryException sınıfı](../../mfc/reference/cmemoryexception-class.md) oluşturulur. ATL programlarında bir [CAtlException](../../atl/reference/catlexception-class.md) atılır. Bu işlev, genellikle otomasyon için dizeler döndürmek üzere kullanılır.

Genellikle, bu dize bir COM işlevine [in] parametresi olarak geçiriltiyse, bu durumda çağıranın dizeyi serbest bırakma işlemi gerekir. Bu, Windows SDK açıklandığı gibi [SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)kullanılarak yapılabilir. Daha fazla bilgi için bkz. [BIR BSTR Için bellek ayırma ve serbest bırakma](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).

Windows 'daki OLE ayırma işlevleri hakkında daha fazla bilgi için Windows SDK [SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) bölümüne bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CStringT::AllocSysString`kullanımını gösterir.

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

##  <a name="ansitooem"></a>CStringT:: Ansıtooem

Bu `CStringT` nesnesindeki tüm karakterleri ANSI karakter kümesinden OEM karakter kümesine dönüştürür.

```
void AnsiToOem();
```

### <a name="remarks"></a>Açıklamalar

_UNICODE tanımlanmışsa işlev kullanılamaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

##  <a name="appendformat"></a>CStringT:: AppendFormat

Biçimlendirilen verileri varolan bir `CStringT` nesnesine ekler.

```
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçim denetimi dizesi.

*nFormatID*<br/>
Biçim denetimi dizesini içeren dize kaynak tanımlayıcısı.

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `CStringT`bir dizi karakter ve değeri biçimlendirir ve ekler. Her isteğe bağlı bağımsız değişken (varsa), *pszFormat* veya *nFormatID*tarafından tanımlanan dize kaynağından karşılık gelen biçim belirtimine göre dönüştürülür ve eklenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

##  <a name="collate"></a>CStringT:: COLLATE

`_tcscoll`genel metin işlevini kullanarak iki dizeyi karşılaştırır.

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, bu `CStringT` nesne *PSZ*'den küçükse 0 < veya bu `CStringT` nesnesi *PSZ*'den büyükse 0 >.

### <a name="remarks"></a>Açıklamalar

TCHAR içinde tanımlanan genel metin işlevi `_tcscoll`. H, derleme zamanında tanımlanan karakter kümesine bağlı olarak `strcoll`, `wcscoll`veya `_mbscoll`eşlenir. Her işlev, kullanılmakta olan kod sayfasına göre dizelerin büyük/küçük harfe duyarlı bir karşılaştırmasını gerçekleştirir. Daha fazla bilgi için bkz. [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

##  <a name="collatenocase"></a>CStringT:: CollateNoCase

`_tcscoll`genel metin işlevini kullanarak iki dizeyi karşılaştırır.

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır (büyük/küçük harf yok sayılıyor) <, bu `CStringT` nesnesi *PSZ* 'den küçükse (büyük/küçük harf yok sayılıyor) veya bu `CStringT` nesnesi *PSZ* 'den büyükse (büyük/küçük harf yok sayılıyor) 0 >.

### <a name="remarks"></a>Açıklamalar

TCHAR içinde tanımlanan genel metin işlevi `_tcscoll`. H, derleme zamanında tanımlanan karakter kümesine bağlı olarak `stricoll`, `wcsicoll`veya `_mbsicoll`eşlenir. Her işlev, kullanılmakta olan kod sayfasına göre dizelerin büyük/küçük harf duyarsız bir karşılaştırmasını yapar. Daha fazla bilgi için bkz. [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

##  <a name="compare"></a>CStringT:: Compare

İki dizeyi karşılaştırır (büyük/küçük harfe duyarlı).

```
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, bu `CStringT` nesne *PSZ*'den küçükse 0 < veya bu `CStringT` nesnesi *PSZ*'den büyükse 0 >.

### <a name="remarks"></a>Açıklamalar

TCHAR içinde tanımlanan genel metin işlevi `_tcscmp`. H, derleme zamanında tanımlanan karakter kümesine bağlı olarak `strcmp`, `wcscmp`veya `_mbscmp`eşlenir. Her işlev, dizelerin büyük küçük harfe duyarlı bir karşılaştırmasını gerçekleştirir ve yerel ayarından etkilenmez. Daha fazla bilgi için bkz. [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).

Dize gömülü null değerler içeriyorsa, karşılaştırma amaçları doğrultusunda dizenin ilk gömülü null karakterde kesilme olarak kabul edilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CStringT::Compare`kullanımını gösterir.

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

##  <a name="comparenocase"></a>CStringT:: CompareNoCase

İki dizeyi karşılaştırır (büyük/küçük harfe duyarsız).

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır (büyük/küçük harf yok sayılıyor) <, bu `CStringT` nesnesi *PSZ* 'den küçükse (büyük/küçük harf yok sayılıyor) veya bu `CStringT` nesnesi *PSZ* 'den büyükse (büyük/küçük harf yok sayılıyor) 0 >.

### <a name="remarks"></a>Açıklamalar

TCHAR içinde tanımlanan genel metin işlevi `_tcsicmp`. H, derleme zamanında tanımlanan karakter kümesine bağlı olarak `_stricmp`, `_wcsicmp` veya `_mbsicmp`eşlenir. Her işlev, dizelerin büyük/küçük harf duyarsız bir karşılaştırmasını yapar. Karşılaştırma, yerel ayarın LC_CTYPE göre değişir ancak LC_COLLATE. Daha fazla bilgi için bkz. [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

##  <a name="cstringt"></a>CStringT:: CStringT

`CStringT` nesnesi oluşturur.

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

*PCH*<br/>
Null ile Sonlandırılmamış, *nLength*uzunluklu bir karakter dizisine yönelik bir işaretçi.

*nLength*<br/>
*PCH*içindeki karakter sayısının sayısı.

*denetleyebilirsiniz*<br/>
Tek bir karakter.

*pszSrc*<br/>
Bu `CStringT` nesnesine kopyalanacak null ile sonlandırılmış bir dize.

*pStringMgr*<br/>
`CStringT` nesnesi için bellek Yöneticisi işaretçisi. `CStringT`için `IAtlStringMgr` ve bellek yönetimi hakkında daha fazla bilgi için bkz. [CStringT Ile bellek yönetimi](../../atl-mfc-shared/memory-management-with-cstringt.md).

*strSrc*<br/>
Bu `CStringT` nesnesine Kopyalanacak varolan bir `CStringT` nesnesi. `CThisString` ve `CThisSimpleString`hakkında daha fazla bilgi için, açıklamalar bölümüne bakın.

*varSrc*<br/>
Bu `CStringT` nesnesine kopyalanacak bir değişken nesne.

*BaseType*<br/>
Dize sınıfının karakter türü. Aşağıdakilerden biri olabilir:

**char** (ANSI karakter dizeleri için).

**wchar_t** (Unicode karakter dizeleri için).

TCHAR (hem ANSI hem de Unicode karakter dizeleri için).

*bMFCDLL*<br/>
Projenin bir MFC DLL (TRUE) olup olmadığını belirten Boole değeri (FALSE).

*SystemString*<br/>
`System::String`olmalıdır ve projenin/clrile derlenmesi gerekir.

*Pstrıng*<br/>
`CStringT` nesne için tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Oluşturucular giriş verilerini yeni ayrılmış depolamaya kopyalayacağından, bellek özel durumlarının sonuç olabileceğini bilmelisiniz. Bu oluşturucuların bazılarının dönüştürme işlevleri olarak davrandığına unutmayın. Bu, örneğin bir `CStringT` nesnenin beklenildiği bir LPTSTR değerini değiştirmenize olanak sağlar.

- `CStringT`(`LPCSTR` `lpsz`): bir ANSI dizesinden Unicode `CStringT` oluşturur. Bu oluşturucuyu, aşağıdaki örnekte gösterildiği gibi bir dize kaynağını yüklemek için de kullanabilirsiniz.

- `CStringT(` `LPCWSTR` `lpsz`): Unicode dizesinden bir `CStringT` oluşturur.

- `CStringT`(`const unsigned char*` `psz`): **işaretsiz char**işaretçisinden bir `CStringT` oluşturmanıza izin verir.

> [!NOTE]
>  ANSI ve Unicode dizeleri arasında örtük dize dönüştürmeyi kapatmak için _CSTRING_DISABLE_NARROW_WIDE_CONVERSION makrosunu tanımlayın. Makro, dönüştürmeyi destekleyen derleme oluşturucularından hariç tutar.

*StrSrc* parametresinin bir `CStringT` ya da `CThisSimpleString` nesnesi olabileceğini unutmayın. `CStringT`için, varsayılan örneklerinden birini (`CString`, `CStringA`veya `CStringW`) kullanın; `CThisSimpleString`için **Bu** işaretçiyi kullanın. `CThisSimpleString`, `CStringT` sınıfından daha az yerleşik işlevselliğe sahip daha küçük bir dize sınıfı olan [CSimpleStringT sınıfının](../../atl-mfc-shared/reference/csimplestringt-class.md)bir örneğini bildirir.

Aşırı yükleme işleci `CSimpleStringT<>&()` `CSimpleStringT` bildiriminden bir `CStringT` nesnesi oluşturur.

> [!NOTE]
>  Gömülü null karakterleri içeren `CStringT` örnekleri oluşturmak mümkün olsa da, bunun için önerilir. Katıştırılmış null karakterler içeren `CStringT` nesneler üzerinde Yöntemler ve işleçler çağırma istenmeden sonuçlar verebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

##  <a name="_dtorcstringt"></a>CStringT:: ~ CStringT

`CStringT` nesnesini yok eder.

```
~CStringT() throw();
```

### <a name="remarks"></a>Açıklamalar

`CStringT` nesnesini yok eder.

##  <a name="delete"></a>CStringT::D Sil

Verilen dizindeki karakterle başlayan bir dizeden bir karakter veya karakter siler.

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
Silinecek `CStringT` nesnesindeki ilk karakterin sıfır tabanlı dizini.

*nCount*<br/>
Kaldırılacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen dizenin uzunluğu.

### <a name="remarks"></a>Açıklamalar

*NCount* dizeden uzunsa, dizenin geri kalanı kaldırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

##  <a name="find"></a>CStringT:: Find

Bu dizeyi bir karakter veya alt dizenin ilk eşleşmesi için arar.

```
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>Parametreler

*pszSub*<br/>
Aranacak alt dize.

*Isdan Başlat*<br/>
Aramaya başlamak için dizedeki karakterin dizini veya baştan başlamak için 0.

*denetleyebilirsiniz*<br/>
Aranacak tek bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Bu `CStringT` nesnesindeki, istenen alt dize veya karakterlerle eşleşen ilk karakterin sıfır tabanlı dizini; alt dize veya karakter bulunamazsa-1.

### <a name="remarks"></a>Açıklamalar

İşlev, tek karakterleri (çalışma zamanı işlevi `strchr`benzer) ve dizeleriyle (`strstr`benzer şekilde) kabul etmek için aşırı yüklenmiştir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

##  <a name="findoneof"></a>CStringT:: FindOneOf

Bu dizeyi, *pszCharSet*içinde bulunan herhangi bir karakterle eşleşen ilk karakter için arar.

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>Parametreler

*pszCharSet*<br/>
Eşleştirme için karakter içeren dize.

### <a name="return-value"></a>Dönüş Değeri

Bu dizedeki, *pszCharSet*içinde de olan ilk karakterin sıfır tabanlı dizini. -1 eşleşme yoksa.

### <a name="remarks"></a>Açıklamalar

*PszCharSet*içindeki tüm karakterlerin ilk oluşumunu bulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

##  <a name="format"></a>CStringT:: Format

Biçimli verileri bir `CStringT`, [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) verileri C stili bir karakter dizisine biçimlendiren aynı şekilde yazar.

```
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>Parametreler

*nFormatID*<br/>
Biçim denetimi dizesini içeren dize kaynak tanımlayıcısı.

*pszFormat*<br/>
Biçim denetimi dizesi.

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `CStringT`bir dizi karakter ve değeri biçimlendirir ve depolar. Her isteğe bağlı bağımsız değişken (varsa), *pszFormat* veya *nFormatID*tarafından tanımlanan dize kaynağından karşılık gelen biçim belirtimine göre dönüştürülür ve çıktı.

Dize nesnesinin kendisi `Format`bir parametre olarak sunulursa çağrı başarısız olur. Örneğin, aşağıdaki kod öngörülemeyen sonuçlara neden olur:

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

Daha fazla bilgi için bkz. [Biçim belirtimi sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

##  <a name="formatmessage"></a>CStringT:: FormatMessage

Bir ileti dizesini biçimlendirir.

```
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>Parametreler

*nFormatID*<br/>
Biçimlendirilmemiş ileti metnini içeren dize kaynak tanımlayıcısı.

*pszFormat*<br/>
Biçim denetimi dizesini işaret eder. Bu, ekleme ve biçimlendirme için taranır. Biçim dizesi, parametrelerin rastgele bir sıraya eklenmesine izin verdiğinden, çalışma zamanı işlevine *printf*stili biçim dizelerine benzer.

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

İşlev, giriş olarak bir ileti tanımı gerektirir. İleti tanımı *pszFormat* tarafından veya *nFormatID*tarafından tanımlanan dize kaynağından belirlenir. İşlevi, istenen katıştırılmış ekleme dizilerini işlemek için, biçimli ileti metnini `CStringT` nesnesine kopyalar.

> [!NOTE]
> `FormatMessage`, yeni biçimlendirilen dize için sistem belleği ayırmaya çalışır. Bu deneme başarısız olursa, otomatik olarak bir bellek özel durumu oluşturulur.

Her ekleme, *pszFormat* veya *nFormatID* parametresini izleyen karşılık gelen bir parametreye sahip olmalıdır. İleti metni içinde, iletiyi dinamik olarak biçimlendirmek için birkaç kaçış dizisi desteklenir. Daha fazla bilgi için Windows SDK Windows [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) işlevine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

##  <a name="formatmessagev"></a>CStringT:: FormatMessageV

Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.

```
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçim denetimi dizesini işaret eder. Bu, ekleme ve biçimlendirme için taranır. Biçim dizesi, parametrelerin rastgele bir sıraya eklenmesine izin verdiğinden, çalışma zamanı işlevine `printf`stili biçim dizelerine benzer.

*pArgList*<br/>
Bağımsız değişken listesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

İşlev, giriş olarak *pszFormat*tarafından belirlenen bir ileti tanımı gerektirir. İşlevi, istenen katıştırılmış ekleme dizilerini işlemek için, biçimli ileti metnini ve bağımsız değişkenlerin değişken listesini `CStringT` nesnesine kopyalar.

> [!NOTE]
> `FormatMessageV`, yeni biçimlendirilen dize için sistem belleği ayırmayı deneyen [CStringT:: FormatMessage](#formatmessage)' ı çağırır. Bu deneme başarısız olursa, otomatik olarak bir bellek özel durumu oluşturulur.

Daha fazla bilgi için Windows SDK Windows [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) işlevine bakın.

##  <a name="formatv"></a>CStringT:: FormatV

Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.

```
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçim denetimi dizesini işaret eder. Bu, ekleme ve biçimlendirme için taranır. Biçim dizesi, parametrelerin rastgele bir sıraya eklenmesine izin verdiğinden, çalışma zamanı işlevine `printf`stili biçim dizelerine benzer.

*args*<br/>
Bağımsız değişken listesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Biçimli bir dize ve bir `CStringT` dize bağımsız değişken listesini, `vsprintf_s` verileri C stili bir karakter dizisine biçimlendiren aynı şekilde yazar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

##  <a name="getenvironmentvariable"></a>CStringT:: GetEnvironmentVariable

Dizeyi belirtilen ortam değişkeninin değerine ayarlar.

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>Parametreler

*pszVar*<br/>
Ortam değişkenini belirten, null ile sonlandırılmış bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çağıran işlemin ortam bloğundan belirtilen değişkenin değerini alır. Değer, null ile sonlandırılmış bir karakter dizesi biçiminde olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

##  <a name="insert"></a>CStringT:: INSERT

Dize içindeki verilen dizine tek bir karakter veya alt dize ekler.

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
Ekleme gerçekleşmeden önceki karakterin dizini.

*PSZ*<br/>
Eklenecek alt dizeye yönelik bir işaretçi.

*denetleyebilirsiniz*<br/>
Eklenecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen dizenin uzunluğu.

### <a name="remarks"></a>Açıklamalar

*IIndex* parametresi, karakter veya alt dize için yer açmak üzere taşınacak ilk karakteri tanımlar. *NIndex* sıfırsa, ekleme dizenin tamamının önüne gelir. *NIndex* , dizenin uzunluğundan daha yüksekse, işlev mevcut dizeyi ve *ya da* *PSZ*tarafından belirtilen yeni malzemeyi birleştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

##  <a name="left"></a>CStringT:: Left

Bu `CStringT` nesnesinden en soldaki *nCount* karakterlerini ayıklar ve ayıklanan alt dizenin bir kopyasını döndürür.

```
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>Parametreler

*nCount*<br/>
Bu `CStringT` nesnesinden Ayıklanacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen karakter aralığının bir kopyasını içeren `CStringT` nesnesi. Döndürülen `CStringT` nesnesi boş olabilir.

### <a name="remarks"></a>Açıklamalar

*NCount* dize uzunluğunu aşarsa, tüm dize ayıklanır. `Left`, temel `Left` işlevine benzer.

Çok baytlı karakter kümeleri (MBCS) için *nCount* her 8 bit sırayı bir karakter olarak değerlendirir, bu nedenle *nCount* , çok baytlık karakterlerin sayısını ikiye çarparak döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

##  <a name="loadstring"></a>CStringT:: LoadString

*NID*tarafından tanımlanan bir Windows dize kaynağını varolan bir `CStringT` nesnesine okur.

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Modülün örneğine yönelik bir tanıtıcı.

*NID*<br/>
Bir Windows dize kaynak KIMLIĞI.

*Wlanguageıd*<br/>
Dize kaynağının dili.

### <a name="return-value"></a>Dönüş Değeri

Kaynak yükü başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen dil (*wLanguage*) kullanarak belirtilen modülden (*HINSTANCE*) dize kaynağını (*NID*) yükler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

##  <a name="makelower"></a>CStringT:: MakeLower

`CStringT` nesnesini küçük harfli bir dizeye dönüştürür.

```
CStringT& MakeLower();
```

### <a name="return-value"></a>Dönüş Değeri

Elde edilen küçük harfli dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

##  <a name="makereverse"></a>CStringT:: MakeReverse

`CStringT` nesnesindeki karakterlerin sırasını tersine çevirir.

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>Dönüş Değeri

Elde edilen ters dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

##  <a name="makeupper"></a>CStringT:: MakeUpper

`CStringT` nesnesini büyük bir dizeye dönüştürür.

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan büyük dize.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

##  <a name="mid"></a>CStringT:: Mid

*Iırtst* (sıfır tabanlı) konumundan başlayarak bu `CStringT` nesnesinden *nCount* karakter uzunluğunda bir alt dize ayıklar.

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>Parametreler

*ıfırst*<br/>
Bu `CStringT` nesnesindeki, ayıklanan alt dizeye dahil edilecek ilk karakterin sıfır tabanlı dizini.

*nCount*<br/>
Bu `CStringT` nesnesinden Ayıklanacak karakter sayısı. Bu parametre sağlanmazsa, dizenin geri kalanı ayıklanır.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen karakter aralığının bir kopyasını içeren `CStringT` nesnesi. Döndürülen `CStringT` nesnesinin boş olabileceğini unutmayın.

### <a name="remarks"></a>Açıklamalar

İşlevi ayıklanan alt dizenin bir kopyasını döndürür. `Mid`, temel PARÇAAL işlevine benzer (temel olan dizinlerin tek tabanlı olması dışında).

Çok baytlı karakter kümeleri (MBCS) için *nCount* her 8 bit karaktere başvurur; diğer bir deyişle, bir çok baytlı karakter içindeki bir lider ve sondaki bayt iki karakter olarak sayılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

##  <a name="oemtoansi"></a>CStringT:: OemToAnsi

Bu `CStringT` nesnesindeki tüm karakterleri OEM karakter kümesinden ANSI karakter kümesine dönüştürür.

```
void OemToAnsi();
```

### <a name="remarks"></a>Açıklamalar

_UNICODE tanımlanmışsa bu işlev kullanılamaz.

### <a name="example"></a>Örnek

[CStringT:: Ansıtooem](#ansitooem)örneğine bakın.

##  <a name="operator_eq"></a>CStringT:: operator =

Dizeye yeni bir değer atar.

```
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

*strSrc*<br/>
Bu dizeye atanacak bir `CStringT`.

*üstbilgisine*<br/>
`CThisSimpleString` nesnesine bir başvuru.

*bMFCDLL*<br/>
Projenin bir MFC DLL olup olmadığını belirten bir Boole değeri.

*BaseType*<br/>
Dize temel türü.

*var*<br/>
Bu dizeye atanacak bir değişken nesne.

*denetleyebilirsiniz*<br/>
Dizeye atanacak bir ANSI veya Unicode karakteri.

*pszSrc*<br/>
Atanmakta olan özgün dizeye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Atama işleci başka bir `CStringT` nesnesini, bir karakter işaretçisini veya tek bir karakteri kabul eder. Yeni depolama alanı ayrılabileceği için bu işleci her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın.

`CThisSimpleString`hakkında bilgi için [CStringT:: CStringT](#cstringt)konusunun açıklamalar bölümüne bakın.

> [!NOTE]
> Gömülü null karakterleri içeren `CStringT` örnekleri oluşturmak mümkün olsa da, bunun için önerilir. Katıştırılmış null karakterler içeren `CStringT` nesneler üzerinde Yöntemler ve işleçler çağırma istenmeden sonuçlar verebilir.

##  <a name="operator_add"></a>CStringT:: operator +

İki dizeyi veya bir karakteri ve dizeyi birleştirir.

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

*CH1*<br/>
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*CH2*<br/>
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*str1*<br/>
Bir dize veya karakterle birleştirmek için bir `CStringT`.

*str2*<br/>
Bir dize veya karakterle birleştirmek için bir `CStringT`.

*psz1*<br/>
Bir dize veya karakterle birleştirmek için null ile sonlandırılmış bir dize işaretçisi.

*psz2*<br/>
Dize veya karakterle birleştirilecek dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CStringT::operator+` işlevinin yedi aşırı yükleme biçimi vardır. İlk sürüm, var olan iki `CStringT` nesnesini birleştirir. Sonraki iki, bir `CStringT` nesnesini ve null ile sonlandırılmış dizeyi birleştirir. Sonraki iki, bir `CStringT` nesnesi ve bir ANSI karakteri birleştirir. Son iki, bir `CStringT` nesnesi ve bir Unicode karakteri birleştirir.

> [!NOTE]
>  Gömülü null karakterleri içeren `CStringT` örnekleri oluşturmak mümkün olsa da, bunun için önerilir. Katıştırılmış null karakterler içeren `CStringT` nesneler üzerinde Yöntemler ve işleçler çağırma istenmeden sonuçlar verebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

##  <a name="operator_add_eq"></a>CStringT:: operator + =

Dizenin sonundaki karakterleri birleştirir.

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

*üstbilgisine*<br/>
`CThisSimpleString` nesnesine bir başvuru.

*bMFCDLL*<br/>
Projenin bir MFC DLL olup olmadığını belirten bir Boole değeri.

*BaseType*<br/>
Dize temel türü.

*var*<br/>
Bu dizeyi birleştirmek için bir değişken nesne.

*denetleyebilirsiniz*<br/>
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*pszSrc*<br/>
Art arda eklenen orijinal dizeye yönelik bir işaretçi.

*strSrc*<br/>
Bu dizeyi birleştirmek için bir `CStringT`.

### <a name="remarks"></a>Açıklamalar

İşleç başka bir `CStringT` nesnesini, bir karakter işaretçisini veya tek bir karakteri kabul eder. Bu `CStringT` nesnesine eklenen karakterler için yeni depolama alanı ayrılabileceği için, bu birleştirme işlecini her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın.

`CThisSimpleString`hakkında bilgi için [CStringT:: CStringT](#cstringt)konusunun açıklamalar bölümüne bakın.

> [!NOTE]
>  Gömülü null karakterleri içeren `CStringT` örnekleri oluşturmak mümkün olsa da, bunun için önerilir. Katıştırılmış null karakterler içeren `CStringT` nesneler üzerinde Yöntemler ve işleçler çağırma istenmeden sonuçlar verebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

##  <a name="operator_eq_eq"></a>CStringT:: operator = =

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

*CH1*<br/>
Karşılaştırma için bir ANSI veya Unicode karakteri.

*CH2*<br/>
Karşılaştırma için bir ANSI veya Unicode karakteri.

*str1*<br/>
Karşılaştırma için bir `CStringT`.

*str2*<br/>
Karşılaştırma için bir `CStringT`.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir dizenin veya karakterin sağ taraftaki bir dizeye veya karaktere eşit olup olmadığını sınar ve doğru ya da yanlış değerlerini uygun bir şekilde döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

##  <a name="operator_neq"></a>CStringT:: operator! =

İki dizenin mantıksal olarak eşit olup olmadığını belirler.

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

*CH1*<br/>
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*CH2*<br/>
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*str1*<br/>
Karşılaştırma için bir `CStringT`.

*str2*<br/>
Karşılaştırma için bir `CStringT`.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir dize veya karakter sağ taraftaki bir dizeye veya karaktere eşit değilse sınar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

##  <a name="operator_lt"></a>CStringT:: operator &lt;

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha az olup olmadığını belirler.

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırma için bir `CStringT`.

*str2*<br/>
Karşılaştırma için bir `CStringT`.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgrafik karşılaştırması, şu kadar karakter olarak karakter:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karaktere sahip olduğunu ve bu nedenle dizelerin eşit olduğunu bulduğunu bulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

##  <a name="operator_gt"></a>CStringT:: operator &gt;

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha büyük olup olmadığını belirler.

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırma için bir `CStringT`.

*str2*<br/>
Karşılaştırma için bir `CStringT`.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgrafik karşılaştırması, şu kadar karakter olarak karakter:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karakter içerdiğinden, dizelerin eşit olduğundan emin olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

##  <a name="operator_lt_eq"></a>CStringT:: operator &lt;=

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden küçük veya ona eşit olup olmadığını belirler.

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırma için bir `CStringT`.

*str2*<br/>
Karşılaştırma için bir `CStringT`.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgrafik karşılaştırması, şu kadar karakter olarak karakter:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karakter içerdiğinden, dizelerin eşit olduğundan emin olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

##  <a name="operator_gt_eq"></a>CStringT:: operator &gt;=

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden büyük veya ona eşit olup olmadığını belirler.

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırma için bir `CStringT`.

*str2*<br/>
Karşılaştırma için bir `CStringT`.

*psz1*<br/>
Karşılaştırma için bir dizeye yönelik işaretçi.

*psz2*<br/>
Karşılaştırma için bir dizeye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgrafik karşılaştırması, şu kadar karakter olarak karakter:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karakter içerdiğinden, dizelerin eşit olduğundan emin olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

##  <a name="remove"></a>CStringT:: Remove

Belirtilen karakterin tüm örneklerini dizeden kaldırır.

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>Parametreler

*chRemove*<br/>
Dizeden kaldırılacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Dizeden kaldırılan karakter sayısı. Dize değiştirilmediyseniz sıfır.

### <a name="remarks"></a>Açıklamalar

Karakter için karşılaştırmalar büyük/küçük harfe duyarlıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

##  <a name="replace"></a>CStringT:: Replace

`Replace`iki sürümü vardır. İlk sürüm, bir alt dizenin bir veya daha fazla kopyasını başka bir alt dize kullanarak değiştirir. Her iki alt dize de null ile sonlandırılır. İkinci sürüm, bir karakterin bir veya daha fazla kopyasını başka bir karakter kullanarak değiştirir. Her iki sürüm de `CStringT`depolanan karakter verilerinde çalışır.

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>Parametreler

*pszOld*<br/>
*PszNew*ile değiştirilmelidir, null ile sonlandırılmış bir dize işaretçisi.

*pszNew*<br/>
*PszOld*'ın yerini alan null ile sonlandırılmış bir dize işaretçisi.

*chOld*<br/>
*Yeni*ile değiştirildiği karakter.

*chNew*<br/>
*ChOld*değiştirme karakteri.

### <a name="return-value"></a>Dönüş Değeri

Karakter veya alt dizenin değiştirilen örneklerinin sayısını veya dize değiştirilmediyse sıfır değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`Replace` *pszNew* ve *pszOld* aynı uzunlukta olmadığından ve eski alt dizenin birkaç kopyası yeni bir tane olarak değiştirilebildiğinden, dize uzunluğunu değiştirebilir. İşlev, büyük/küçük harfe duyarlı bir eşleşme gerçekleştirir.

`CStringT` örneklerine örnek olarak `CString`, `CStringA`ve `CStringW`verilebilir.

`CStringA`için `Replace` ANSI veya çok baytlı (MBCS) karakterleriyle çalışmaktadır. `CStringW`için, `Replace` geniş karakterlerle birlikte kullanılabilir.

`CString`için, karakter veri türü, aşağıdaki tablodaki sabitlerin tanımlanıp tanımlanmayacağı konusunda, derleme zamanında seçilir.

|Tanımlı sabit|Karakter veri türü|
|----------------------|-------------------------|
|_UNICODE|Geniş karakterler|
|_MBCS|Çok baytlı karakterler|
|Hiçbiri|Tek baytlık karakterler|
|Her ikisi de|Tanımlanmadı|

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

##  <a name="reversefind"></a>CStringT:: Smarfind

Bu `CStringT` nesnesini bir karakterin son eşleşmesi için arar.

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*<br/>
Aranacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Bu `CStringT` nesnesindeki, istenen karakterle eşleşen son karakterin sıfır tabanlı dizini veya karakter bulunamazsa-1.

### <a name="remarks"></a>Açıklamalar

İşlev, `strrchr`çalışma zamanı işlevine benzer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

##  <a name="right"></a>CStringT:: Right

Bu `CStringT` nesnesinden en son (en sağdaki) *Nsayı* karakterini ayıklar ve ayıklanan alt dizenin bir kopyasını döndürür.

```
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>Parametreler

*nCount*<br/>
Bu `CStringT` nesnesinden Ayıklanacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen karakter aralığının bir kopyasını içeren `CStringT` nesnesi. Döndürülen `CStringT` nesnesinin boş olabileceğini unutmayın.

### <a name="remarks"></a>Açıklamalar

*NCount* dize uzunluğunu aşarsa, tüm dize ayıklanır. `Right`, temel `Right` işlevine benzerdir (temel içindeki dizinlerin sıfır tabanlı olması dışında).

Çok baytlı karakter kümeleri (MBCS) için *nCount* her 8 bit karaktere başvurur; diğer bir deyişle, bir çok baytlı karakter içindeki bir lider ve sondaki bayt iki karakter olarak sayılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

##  <a name="setsysstring"></a>CStringT:: SetSysString

, *Pbstr* tarafından Işaret edilen BSTR 'yi yeniden KONUMLANDıRıR ve null karakter dahil `CStringT` nesnesinin içeriğini buna kopyalar.

```
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>Parametreler

*pbstr*<br/>
Karakter dizesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yeni dize.

### <a name="remarks"></a>Açıklamalar

`CStringT` nesnesinin içeriğine bağlı olarak, *pbstr* tarafından başvurulan BSTR 'nin değeri değişebilir. Yetersiz bellek varsa işlevi bir `CMemoryException` oluşturur.

Bu işlev genellikle otomasyon için başvuruya göre geçirilen dizelerin değerini değiştirmek için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

##  <a name="spanexcluding"></a>CStringT:: Spanhariç tutma

İlk karakterle başlayarak, *pszCharSet*tarafından tanımlanan karakter kümesinde olmayan karakterleri dizeden ayıklar.

```
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Parametreler

*pszCharSet*<br/>
Bir karakter kümesi olarak yorumlanan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Dizedeki ilk karakterle başlayan ve pszCharSet içinde olan dizedeki ilk karakterle *biten (yani* , dizedeki ilk karakterle başlayan, ancak *pszCharSet*bulunan dizedeki ilk karakteri hariç), *pszCharSet*içinde olmayan karakter içeren bir alt dize... Dizede *pszCharSet* içinde hiçbir karakter bulunamazsa, dizenin tamamını döndürür.

### <a name="remarks"></a>Açıklamalar

`SpanExcluding`, *pszCharSet* 'ten bir karakterin ilk örneğinden önceki tüm karakterleri ayıklar ve döndürür (diğer bir deyişle, *pszCharSet* karakteri ve dizedeki izleyen tüm karakterler döndürülmez). Dizede *pszCharSet* öğesinden bir karakter bulunmazsa `SpanExcluding` tüm dizeyi döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

##  <a name="spanincluding"></a>CStringT:: Spandahil

Dizeden, *pszCharSet*tarafından tanımlanan karakter kümesindeki ilk karakterle başlayarak karakterleri ayıklar.

```
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Parametreler

*pszCharSet*<br/>
Bir karakter kümesi olarak yorumlanan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Dizedeki ilk karakterle başlayan ve *pszCharSet*içinde olmayan dizede bir karakter bulunduğunda biten, *pszCharSet*içindeki dizedeki karakterleri içeren bir alt dize. `SpanIncluding` dizedeki ilk karakter belirtilen küme içinde değilse boş bir alt dize döndürür.

### <a name="remarks"></a>Açıklamalar

Dizenin ilk karakteri karakter kümesinde değilse, `SpanIncluding` boş bir dize döndürür. Aksi takdirde, küme içindeki ardışık karakterlerin dizisini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

##  <a name="tokenize"></a>CStringT:: tokenize

Hedef dizede bir sonraki belirteci bulur

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>Parametreler

*pszTokens*<br/>
Belirteç sınırlayıcıları içeren bir dize. Bu sınırlayıcıların sırası önemli değildir.

*Isdan Başlat*<br/>
Aramaya başlamak için sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Geçerli belirteç değerini içeren `CStringT` nesnesi.

### <a name="remarks"></a>Açıklamalar

`Tokenize` işlevi, hedef dizedeki bir sonraki belirteci bulur. *PszTokens* içindeki karakter kümesi, bulunamayan belirtecin olası sınırlayıcılarını belirtir. `Tokenize` her bir çağrıda, işlev *ısbaşlangıç*' de başlar, önde gelen sınırlayıcıları atlar ve sonraki sınırlayıcı karaktere kadar olan karakterlerin dizesi olan geçerli belirteci içeren bir `CStringT` nesnesi döndürür. *Isbaşlangıç* değeri bitiş sınırlayıcı karakteri izleyen konum olacak şekilde güncelleştirilir veya dizenin sonuna ulaşılırsa-1. Daha fazla belirteç, hedef dizenin geri kalanından, `Tokenize`bir dizi çağrı tarafından parçalanarak, sıradaki belirtecin nerede okunacağını izlemek için *ısbaşlangıç* kullanılarak. Daha fazla belirteç yoksa, işlev boş bir dize döndürür ve *ısbaşlangıç* -1 olarak ayarlanır.

[Strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)gibi CRT simgeleştirin işlevlerinin aksine, `Tokenize` hedef dizeyi değiştirmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>Açıklamalar

Bu örnekteki çıktı aşağıdaki gibidir:

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

##  <a name="trim"></a>CStringT:: trim

Dizeden baştaki ve sondaki karakterleri kırpar.

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>Parametreler

*chTarget*<br/>
Kırpılacak hedef karakter.

*pszTargets*<br/>
Kırpılacak hedef karakterleri içeren bir dize işaretçisi. *PszTarget* 'daki karakterlerin tüm önde gelen ve sondaki oluşumları `CStringT` nesnesinden kırpılacak.

### <a name="return-value"></a>Dönüş Değeri

Kırpılan dizeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin önde gelen ve sondaki oluşumlarını kaldırır:

- *ChTarget*tarafından belirtilen karakter.

- *PszTargets*tarafından belirtilen dizedeki tüm karakterler bulundu.

- Boşlu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>Açıklamalar

Bu örnekteki çıktı aşağıdaki gibidir:

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

##  <a name="trimleft"></a>CStringT:: kırıt sola

Dizeden baştaki karakterleri kırpar.

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>Parametreler

*chTarget*<br/>
Kırpılacak hedef karakter.

*pszTargets*<br/>
Kırpılacak hedef karakterleri içeren bir dize işaretçisi. *PszTarget* 'daki karakterlerin tüm önde gelen oluşumları `CStringT` nesnesinden kırpılacak.

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan kırpılan dize.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin önde gelen ve sondaki oluşumlarını kaldırır:

- *ChTarget*tarafından belirtilen karakter.

- *PszTargets*tarafından belirtilen dizedeki tüm karakterler bulundu.

- Boşlu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

##  <a name="trimright"></a>CStringT:: kırma sağ

Dizeden sondaki karakterleri kırpar.

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>Parametreler

*chTarget*<br/>
Kırpılacak hedef karakter.

*pszTargets*<br/>
Kırpılacak hedef karakterleri içeren bir dize işaretçisi. *PszTarget* 'daki karakterlerin tüm sondaki oluşumları `CStringT` nesnesinden kırpılacak.

### <a name="return-value"></a>Dönüş Değeri

Kırpılan dizeyi içeren `CStringT` nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin sondaki oluşumlarını kaldırır:

- *ChTarget*tarafından belirtilen karakter.

- *PszTargets*tarafından belirtilen dizedeki tüm karakterler bulundu.

- Boşlu.

`CStringT& TrimRight(XCHAR chTarget)` sürümü bir karakter parametresini kabul eder ve bu karakterin tüm kopyalarını `CStringT` dize verilerinin sonundan kaldırır. Dizenin sonundan başlar ve önünde doğru çalışacaktır. Farklı bir karakter bulduğunda ya da `CSTringT` karakter verilerinden biterse duraklar.

`CStringT& TrimRight(PCXSTR pszTargets)` sürümü, aranacak tüm farklı karakterleri içeren null ile sonlandırılmış bir dizeyi kabul eder. `CStringT` nesnesindeki bu karakterlerin tüm kopyalarını kaldırır. Dizenin sonunda başlar ve önünde doğru çalışacaktır. Hedef dizede olmayan bir karakter bulduğunda veya `CStringT` karakter verilerinden biterse duraklar. Hedef dizenin tamamını, `CStringT`sonundaki bir alt dizeyle eşleştirmeye çalışmaz.

`CStringT& TrimRight()` sürüm parametre gerektirmez. `CStringT` dizesinin sonundaki sondaki boşluk karakterlerini kırpar. Boşluk karakterleri satır sonları, boşluklar veya sekmeler olabilir.

-

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[CSimpleStringT Sınıfı](../../atl-mfc-shared/reference/csimplestringt-class.md)
