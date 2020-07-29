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
ms.openlocfilehash: 742dd016064ced1f43f54b6456d8d0ad840c2184
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219072"
---
# <a name="cstringt-class"></a>CStringT sınıfı

Bu sınıf bir nesneyi temsil eder `CStringT` .

## <a name="syntax"></a>Söz dizimi

```
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>Parametreler

*BaseType*<br/>
Dize sınıfının karakter türü. Aşağıdakilerden biri olabilir:

- **`char`**(ANSI karakter dizeleri için).

- **`wchar_t`**(Unicode karakter dizeleri için).

- TCHAR (hem ANSI hem de Unicode karakter dizeleri için).

*Stringnitelikler*<br/>
Dize sınıfının C çalışma zamanı (CRT) kitaplık desteğinin gerekip gerekmediğini ve dize kaynaklarının nerede olduğunu belirler. Aşağıdakilerden biri olabilir:

- **Strtrabktl< wchar_t** &#124; **`char`** &#124; **tchar, ChTraitsCRT< wchar_t** &#124; **`char`** &#124; **TCHAR > >**

   Sınıfı, CRT desteğinin yanı sıra `m_hInstResource` (uygulamanın modül sınıfının bir üyesi) tarafından belirtilen modüldeki kaynak dizeleri aramalarını gerektirir.

- **Strtralictl< wchar_t** &#124; **`char`** &#124; **tchar, chtraitsos< wchar_t** &#124; **`char`** &#124; **TCHAR > >**

   Sınıf, `m_hInstResource` (uygulamanın modül sınıfının bir üyesi) tarafından belirtilen MODÜLDE CRT desteği ve arama gerektirmez.

- **StrTraitMFC< wchar_t** &#124; **`char`** &#124; **tchar, ChTraitsCRT< wchar_t** &#124; **`char`** &#124; **TCHAR > >**

   Sınıfı CRT desteği gerektirir ve standart MFC arama algoritmasını kullanarak kaynak dizeleri arar.

- **StrTraitMFC< wchar_t** &#124; **`char`** &#124; **tchar, chtraitsos< wchar_t** &#124; **`char`** &#124; **TCHAR > >**

   Sınıfı, standart MFC arama algoritmasını kullanarak, CRT desteği gerektirmez ve kaynak dizeleri arar.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStringT:: CStringT](#cstringt)|`CStringT`Çeşitli yollarla bir nesne oluşturur.|
|[CStringT:: ~ CStringT](#_dtorcstringt)|Bir nesneyi yok eder `CStringT` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStringT:: AllocSysString](#allocsysstring)|Verilerden bir BSTR ayırır `CStringT` .|
|[CStringT:: Ansıtooem](#ansitooem)|ANSI karakter kümesinden OEM karakter kümesine yerinde dönüştürme yapar.|
|[CStringT:: AppendFormat](#appendformat)|Biçimlendirilen verileri varolan bir nesneye ekler `CStringT` .|
|[CStringT:: COLLATE](#collate)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarlı, yerel ayara özgü bilgiler kullanır).|
|[CStringT:: CollateNoCase](#collatenocase)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarsız, yerel ayara özgü bilgileri kullanır).|
|[CStringT:: Compare](#compare)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarlı).|
|[CStringT:: CompareNoCase](#comparenocase)|İki dizeyi karşılaştırır (büyük/küçük harfe duyarsız).|
|[CStringT::D Sil](#delete)|Dizeden bir karakter veya karakter siler.|
|[CStringT:: Find](#find)|Daha büyük bir dizenin içinde bir karakter veya alt dize bulur.|
|[CStringT:: FindOneOf](#findoneof)|Bir kümeden ilk eşleşen karakteri bulur.|
|[CStringT:: Format](#format)|Dizeyi olduğu gibi biçimlendirir `sprintf` .|
|[CStringT:: FormatMessage](#formatmessage)|Bir ileti dizesini biçimlendirir.|
|[CStringT:: FormatMessageV](#formatmessagev)|Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.|
|[CStringT:: FormatV](#formatv)|Dizeyi değişken bir bağımsız değişken listesi kullanarak biçimlendirir.|
|[CStringT:: GetEnvironmentVariable](#getenvironmentvariable)|Dizeyi belirtilen ortam değişkeninin değerine ayarlar.|
|[CStringT:: INSERT](#insert)|Dize içindeki verilen dizine tek bir karakter veya alt dize ekler.|
|[CStringT:: Left](#left)|Bir dizenin sol kısmını ayıklar.|
|[CStringT:: LoadString](#loadstring)|`CStringT`Bir Windows kaynağından varolan bir nesneyi yükler.|
|[CStringT:: MakeLower](#makelower)|Bu dizedeki tüm karakterleri küçük harfe dönüştürür.|
|[CStringT:: MakeReverse](#makereverse)|Dizeyi tersine çevirir.|
|[CStringT:: MakeUpper](#makeupper)|Bu dizedeki tüm karakterleri büyük harfli karakterlere dönüştürür.|
|[CStringT:: Mid](#mid)|Bir dizenin orta kısmını ayıklar.|
|[CStringT:: OemToAnsi](#oemtoansi)|OEM karakter kümesinden ANSI karakter kümesine yerinde dönüştürme yapar.|
|[CStringT:: Remove](#remove)|Bir dizeden belirtilen karakterleri kaldırır.|
|[CStringT:: Replace](#replace)|Belirtilen karakterleri diğer karakterlerle değiştirir.|
|[CStringT:: Smarfind](#reversefind)|Daha büyük bir dizenin içinde bir karakter bulur; uçtan başlar.|
|[CStringT:: Right](#right)|Bir dizenin sağ kısmını ayıklar.|
|[CStringT:: SetSysString](#setsysstring)|Varolan bir BSTR nesnesini bir nesneden verilerle ayarlar `CStringT` .|
|[CStringT:: Spanhariç tutma](#spanexcluding)|Tarafından tanımlanan karakter kümesinde olmayan, ilk karakterle başlayarak dizeden karakter ayıklar `pszCharSet` .|
|[CStringT:: Spandahil](#spanincluding)|Yalnızca bir küme içindeki karakterleri içeren bir alt dize ayıklar.|
|[CStringT:: tokenize](#tokenize)|Belirtilen belirteçleri bir hedef dizede ayıklar.|
|[CStringT:: trim](#trim)|Dizedeki tüm baştaki ve sondaki boşluk karakterlerini kırpar.|
|[CStringT:: kırıt sola](#trimleft)|Dizeden öndeki boşluk karakterlerini kırpar.|
|[CStringT:: kırma sağ](#trimright)|Dizeden sondaki boşluk karakterlerini kırpar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[CStringT:: operator =](#operator_eq)|Nesnesine yeni bir değer atar `CStringT` .|
|[CStringT:: operator +](#operator_add)|İki dizeyi veya bir karakteri ve dizeyi birleştirir.|
|[CStringT:: operator + =](#operator_add_eq)|Varolan bir dizenin sonuna yeni bir dize ekler.|
|[CStringT:: operator = =](#operator_eq_eq)|İki dizenin mantıksal olarak eşit olup olmadığını belirler.|
|[CStringT:: operator! =](#operator_neq)|İki dizenin mantıksal olarak eşit olup olmadığını belirler.|
|[CStringT:: işleci&lt;](#operator_lt)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha az olup olmadığını belirler.|
|[CStringT:: işleci&gt;](#operator_gt)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha büyük olup olmadığını belirler.|
|[CStringT:: işleci&lt;=](#operator_lt_eq)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden küçük veya ona eşit olup olmadığını belirler.|
|[CStringT:: işleci&gt;=](#operator_gt_eq)|İşlecin sol tarafındaki dizenin sağ taraftaki dizeden büyük veya ona eşit olup olmadığını belirler.|

## <a name="remarks"></a>Açıklamalar

`CStringT`[CSimpleStringT sınıfından](../../atl-mfc-shared/reference/csimplestringt-class.md)devralır. Karakter işleme, sıralama ve arama gibi gelişmiş özellikler tarafından uygulanır `CStringT` .

> [!NOTE]
> `CStringT`nesneler özel durum atma özelliğine sahiptir. Bu `CStringT` , herhangi bir nedenle bir nesne bellekten tükenmediğinde oluşur.

Bir `CStringT` nesne, değişken uzunlukta karakterlerden oluşur. `CStringT`Temel olarak benzer sözdizimini kullanarak işlevleri ve işleçleri sağlar. Birleştirme ve karşılaştırma işleçleri, Basitleştirilmiş bellek yönetimiyle birlikte `CStringT` nesnelerin sıradan karakter dizileri kullanmaktan daha kolay kullanılmasını sağlar.

> [!NOTE]
> Gömülü null karakterler içeren örnekler oluşturmak mümkün olsa da `CStringT` , bunun için önerilir. Katıştırılmış null karakterler içeren nesnelerde Yöntemler ve işleçler çağırma `CStringT` istenmeden sonuçlar verebilir.

Ve parametrelerinin farklı birleşimlerini kullanarak `BaseType` nesneler, `StringTraits` `CStringT` ATL kitaplıkları tarafından önceden tanımlanmış olan aşağıdaki türlerde gelebilir.

Bir ATL uygulamasında kullanıyorsanız:

`CString`, `CStringA` ve, `CStringW` MFC DLL 'den (MFC90.DLL) aktarılmış, hiçbir koşulda Kullanıcı dll 'lerinden aktarılmalıdır. Bu, `CStringT` tanımlanan çarpmasını engellemek için yapılır.

> [!NOTE]
> Kodunuz [CStringT kullanarak dize sınıflarını dışarı aktarma](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md)bölümünde açıklanan bağlayıcı hatalarının geçici çözümünü içeriyorsa, bu kodu kaldırmalısınız. Artık buna ihtiyacınız yoktur.

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

`CString`nesneler aşağıdaki özelliklere de sahiptir:

- `CStringT`nesneler, birleştirme işlemlerinin sonucu olarak büyüyebilir.

- `CStringT`nesneler "değer semantiğini" izler. Bir nesneyi bir `CStringT` dizenin işaretçisi olarak değil, gerçek bir dize olarak düşünün.

- `CStringT`İşlev bağımsız değişkenleri için ücretsiz olarak nesneleri kullanabilirsiniz `PCXSTR` .

- Dize arabellekleri için özel bellek yönetimi. Daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="cstringt-predefined-types"></a>CStringT önceden tanımlanmış türler

, `CStringT` Desteklenen karakter türünü ( [wchar_t](../../c-runtime-library/standard-types.md) veya [char](../../c-runtime-library/standard-types.md)) tanımlamak için bir şablon bağımsız değişkeni kullandığından, yöntem parametresi türleri her zaman karmaşık olabilir. Bu sorunu basitleştirmek için, bir dizi önceden tanımlanmış tür tanımlanmıştır ve sınıf boyunca kullanılır `CStringT` . Aşağıdaki tabloda çeşitli türler listelenmektedir:

|Ad|Açıklama|
|----------|-----------------|
|`XCHAR`|**`wchar_t`** Nesneyle aynı karakter türünde tek bir karakter (ya da **`char`** ) `CStringT` .|
|`YCHAR`|**`wchar_t`** **`char`** Nesneyle aynı karakter türüne sahip tek bir karakter (ya da) `CStringT` .|
|`PXSTR`|**`wchar_t`** **`char`** Nesneyle aynı karakter türüne sahip bir karakter dizesinin (ya da) işaretçisi `CStringT` .|
|`PYSTR`|**`wchar_t`** **`char`** Nesneyle aynı karakter türüne sahip bir karakter dizesinin (ya da ya da) bir işaretçisi `CStringT` .|
|`PCXSTR`|**`const`** **`wchar_t`** **`char`** Nesneyle aynı karakter türüne sahip bir karakter dizesinin (ya da) işaretçisi `CStringT` .|
|`PCYSTR`|**`const`** **`wchar_t`** **`char`** Nesneyle aynı karakter türüne sahip bir karakter dizesinin (ya da ya da) bir işaretçisi `CStringT` .|

> [!NOTE]
> Daha önce belgelenmemiş yöntemlerin (örneğin,) kullanıldığı kodun, `CString` `AssignCopy` aşağıdaki belgelenmiş Yöntemleri (veya gibi) kullanan kodla değiştirilmelidir `CStringT` `GetBuffer` `ReleaseBuffer` . Bu yöntemler öğesinden devralınır `CSimpleStringT` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>Gereksinimler

|Üst bilgi|Şunun için kullanın:|
|------------|-------------|
|CStringT. h|Yalnızca MFC dize nesneleri|
|atlstr. h|MFC olmayan dize nesneleri|

## <a name="cstringtallocsysstring"></a><a name="allocsysstring"></a>CStringT:: AllocSysString

BSTR türünde bir Otomasyon uyumlu dize ayırır ve `CStringT` Sonlandırıcı null karakteri de dahil olmak üzere nesnenin içeriğini buna kopyalar.

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

Aşağıdaki örnek öğesinin kullanımını gösterir `CStringT::AllocSysString` .

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

## <a name="cstringtansitooem"></a><a name="ansitooem"></a>CStringT:: Ansıtooem

Bu nesnedeki tüm karakterleri `CStringT` ANSI karakter KÜMESINDEN OEM karakter kümesine dönüştürür.

```cpp
void AnsiToOem();
```

### <a name="remarks"></a>Açıklamalar

_UNICODE tanımlanmışsa işlev kullanılamaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

## <a name="cstringtappendformat"></a><a name="appendformat"></a>CStringT:: AppendFormat

Biçimlendirilen verileri varolan bir nesneye ekler `CStringT` .

```cpp
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

Bu işlev, içinde bir dizi karakter ve değer biçimlendirir ve ekler `CStringT` . Her isteğe bağlı bağımsız değişken (varsa), *pszFormat* veya *nFormatID*tarafından tanımlanan dize kaynağından karşılık gelen biçim belirtimine göre dönüştürülür ve eklenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

## <a name="cstringtcollate"></a><a name="collate"></a>CStringT:: COLLATE

Genel metin işlevini kullanarak iki dizeyi karşılaştırır `_tcscoll` .

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, bu `CStringT` nesne *PSZ*'den küçükse 0 < veya bu `CStringT` nesne *psz*'den büyükse 0 >.

### <a name="remarks"></a>Açıklamalar

`_tcscoll`TCHAR içinde tanımlanan genel metin işlevi. H, `strcoll` `wcscoll` `_mbscoll` derleme zamanında tanımlanan karakter kümesine bağlı olarak, ya da ile eşlenir. Her işlev, kullanılmakta olan kod sayfasına göre dizelerin büyük/küçük harfe duyarlı bir karşılaştırmasını gerçekleştirir. Daha fazla bilgi için bkz. [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

## <a name="cstringtcollatenocase"></a><a name="collatenocase"></a>CStringT:: CollateNoCase

Genel metin işlevini kullanarak iki dizeyi karşılaştırır `_tcscoll` .

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır (büyük/küçük harf yok sayılıyor) <, bu `CStringT` nesne *PSZ* 'den küçükse (durum yoksayılıyor) veya bu `CStringT` nesne *PSZ* 'den büyükse (büyük/küçük harf yok sayılıyor) 0 >.

### <a name="remarks"></a>Açıklamalar

`_tcscoll`TCHAR içinde tanımlanan genel metin işlevi. H, `stricoll` `wcsicoll` `_mbsicoll` derleme zamanında tanımlanan karakter kümesine bağlı olarak, ya da ile eşlenir. Her işlev, kullanılmakta olan kod sayfasına göre dizelerin büyük/küçük harf duyarsız bir karşılaştırmasını yapar. Daha fazla bilgi için bkz. [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

## <a name="cstringtcompare"></a><a name="compare"></a>CStringT:: Compare

İki dizeyi karşılaştırır (büyük/küçük harfe duyarlı).

```
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, bu `CStringT` nesne *PSZ*'den küçükse 0 < veya bu `CStringT` nesne *psz*'den büyükse 0 >.

### <a name="remarks"></a>Açıklamalar

`_tcscmp`TCHAR içinde tanımlanan genel metin işlevi. H, `strcmp` `wcscmp` `_mbscmp` derleme zamanında tanımlanan karakter kümesine bağlı olarak, ya da ile eşlenir. Her işlev, dizelerin büyük küçük harfe duyarlı bir karşılaştırmasını gerçekleştirir ve yerel ayarından etkilenmez. Daha fazla bilgi için bkz. [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).

Dize gömülü null değerler içeriyorsa, karşılaştırma amaçları doğrultusunda dizenin ilk gömülü null karakterde kesilme olarak kabul edilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CStringT::Compare` .

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

## <a name="cstringtcomparenocase"></a><a name="comparenocase"></a>CStringT:: CompareNoCase

İki dizeyi karşılaştırır (büyük/küçük harfe duyarsız).

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır (büyük/küçük harf yok sayılıyor) <, bu `CStringT` nesne *PSZ* 'den küçükse (durum yoksayılıyor) veya bu `CStringT` nesne *PSZ* 'den büyükse (büyük/küçük harf yok sayılıyor) 0 >.

### <a name="remarks"></a>Açıklamalar

`_tcsicmp`TCHAR içinde tanımlanan genel metin işlevi. H, `_stricmp` `_wcsicmp` `_mbsicmp` derleme zamanında tanımlanan karakter kümesine bağlı olarak ya da veya ile eşlenir. Her işlev, dizelerin büyük/küçük harf duyarsız bir karşılaştırmasını yapar. Karşılaştırma, yerel ayarın LC_CTYPE göre değişir ancak LC_COLLATE. Daha fazla bilgi için bkz. [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

## <a name="cstringtcstringt"></a><a name="cstringt"></a>CStringT:: CStringT

Bir `CStringT` nesnesi oluşturur.

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
Bu nesneye kopyalanacak null ile sonlandırılmış bir dize `CStringT` .

*pStringMgr*<br/>
Nesne için bellek Yöneticisi işaretçisi `CStringT` . Ve için bellek yönetimi hakkında daha fazla bilgi için `IAtlStringMgr` `CStringT` bkz. [CStringT ile bellek yönetimi](../../atl-mfc-shared/memory-management-with-cstringt.md).

*strSrc*<br/>
`CStringT`Bu nesneye Kopyalanacak varolan bir nesne `CStringT` . Ve hakkında daha fazla bilgi için `CThisString` `CThisSimpleString` , açıklamalar bölümüne bakın.

*varSrc*<br/>
Bu nesneye kopyalanacak bir değişken nesne `CStringT` .

*BaseType*<br/>
Dize sınıfının karakter türü. Aşağıdakilerden biri olabilir:

**`char`**(ANSI karakter dizeleri için).

**`wchar_t`**(Unicode karakter dizeleri için).

TCHAR (hem ANSI hem de Unicode karakter dizeleri için).

*bMFCDLL*<br/>
Projenin bir MFC DLL (TRUE) olup olmadığını belirten Boole değeri (FALSE).

*SystemString*<br/>
Olmalıdır `System::String` ve projenin/clrile derlenmesi gerekir.

*Pstrıng*<br/>
Bir nesne için tanıtıcı `CStringT` .

### <a name="remarks"></a>Açıklamalar

Oluşturucular giriş verilerini yeni ayrılmış depolamaya kopyalayacağından, bellek özel durumlarının sonuç olabileceğini bilmelisiniz. Bu oluşturucuların bazılarının dönüştürme işlevleri olarak davrandığına unutmayın. Bu, örneğin, bir nesnenin beklenildiği bir LPTSTR değerini değiştirmenize olanak sağlar `CStringT` .

- `CStringT`( `LPCSTR` `lpsz` ): Bir `CStringT` ANSI dizesinden Unicode oluşturur. Bu oluşturucuyu, aşağıdaki örnekte gösterildiği gibi bir dize kaynağını yüklemek için de kullanabilirsiniz.

- `CStringT(``LPCWSTR` `lpsz` ): Bir `CStringT` Unicode dizesinden bir oluşturur.

- `CStringT`( `const unsigned char*` `psz` ): Bir `CStringT` işaretçisinden için bir işaretçisi oluşturmanıza izin verir **`unsigned char`** .

> [!NOTE]
> ANSI ve Unicode dizeleri arasında örtük dize dönüştürmeyi kapatmak için _CSTRING_DISABLE_NARROW_WIDE_CONVERSION makrosunu tanımlayın. Makro, dönüştürmeyi destekleyen derleme oluşturucularından hariç tutar.

*StrSrc* parametresinin bir ya da nesne olabileceğini unutmayın `CStringT` `CThisSimpleString` . İçin `CStringT` , varsayılan örneklerinden birini ( `CString` , `CStringA` , veya) kullanın `CStringW` ; için `CThisSimpleString` bir **`this`** işaretçi kullanın. `CThisSimpleString`sınıfından daha az yerleşik işlevselliğe sahip daha küçük bir dize sınıfı olan [CSimpleStringT sınıfının](../../atl-mfc-shared/reference/csimplestringt-class.md)bir örneğini bildirir `CStringT` .

Aşırı yükleme işleci bir `CSimpleStringT<>&()` `CStringT` bildirimden bir nesne oluşturur `CSimpleStringT` .

> [!NOTE]
> Gömülü null karakterler içeren örnekler oluşturmak mümkün olsa da `CStringT` , bunun için önerilir. Katıştırılmış null karakterler içeren nesnelerde Yöntemler ve işleçler çağırma `CStringT` istenmeden sonuçlar verebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

## <a name="cstringtcstringt"></a><a name="_dtorcstringt"></a>CStringT:: ~ CStringT

Nesneyi yok eder `CStringT` .

```
~CStringT() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok eder `CStringT` .

## <a name="cstringtdelete"></a><a name="delete"></a>CStringT::D Sil

Verilen dizindeki karakterle başlayan bir dizeden bir karakter veya karakter siler.

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
Silinecek nesnedeki ilk karakterin sıfır tabanlı dizini `CStringT` .

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

## <a name="cstringtfind"></a><a name="find"></a>CStringT:: Find

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

Bu `CStringT` nesnedeki, istenen alt dize veya karakter bulunmazsa,-1 ile eşleşen ilk karakterin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

İşlev, hem tek karakterleri (çalışma zamanı işlevine benzer şekilde) hem de `strchr` dizeleri (şuna benzer şekilde) kabul etmek için aşırı yüklenmiştir `strstr` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

## <a name="cstringtfindoneof"></a><a name="findoneof"></a>CStringT:: FindOneOf

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

## <a name="cstringtformat"></a><a name="format"></a>CStringT:: Format

Biçimli verileri `CStringT` , [Sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) verileri C stili karakter dizisine biçimlendiren aynı şekilde yazar.

```cpp
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

Bu işlev, içindeki bir dizi karakter ve değeri biçimlendirir ve depolar `CStringT` . Her isteğe bağlı bağımsız değişken (varsa), *pszFormat* veya *nFormatID*tarafından tanımlanan dize kaynağından karşılık gelen biçim belirtimine göre dönüştürülür ve çıktı.

Dize nesnesinin kendisi için bir parametre olarak sunulursa çağrı başarısız olur `Format` . Örneğin, aşağıdaki kod öngörülemeyen sonuçlara neden olur:

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

Daha fazla bilgi için bkz. [Biçim belirtimi sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

## <a name="cstringtformatmessage"></a><a name="formatmessage"></a>CStringT:: FormatMessage

Bir ileti dizesini biçimlendirir.

```cpp
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

İşlev, giriş olarak bir ileti tanımı gerektirir. İleti tanımı *pszFormat* tarafından veya *nFormatID*tarafından tanımlanan dize kaynağından belirlenir. İşlevi, `CStringT` istenen katıştırılmış ekleme dizilerini işlemek için, biçimli ileti metnini nesnesine kopyalar.

> [!NOTE]
> `FormatMessage`Yeni biçimlendirilen dize için sistem belleği ayırmaya çalışır. Bu deneme başarısız olursa, otomatik olarak bir bellek özel durumu oluşturulur.

Her ekleme, *pszFormat* veya *nFormatID* parametresini izleyen karşılık gelen bir parametreye sahip olmalıdır. İleti metni içinde, iletiyi dinamik olarak biçimlendirmek için birkaç kaçış dizisi desteklenir. Daha fazla bilgi için Windows SDK Windows [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) işlevine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

## <a name="cstringtformatmessagev"></a><a name="formatmessagev"></a>CStringT:: FormatMessageV

Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.

```cpp
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçim denetimi dizesini işaret eder. Bu, ekleme ve biçimlendirme için taranır. Biçim dizesi, `printf` parametrelerin rastgele bir sıraya eklenmesine izin verdiği sürece, çalışma zamanı işlev stili biçim dizelerine benzerdir.

*pArgList*<br/>
Bağımsız değişken listesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

İşlev, giriş olarak *pszFormat*tarafından belirlenen bir ileti tanımı gerektirir. İşlevi, `CStringT` istenen katıştırılmış ekleme dizilerini işlemek için biçimli ileti metnini ve bağımsız değişkenlerin değişken listesini nesnesine kopyalar.

> [!NOTE]
> `FormatMessageV`Yeni biçimlendirilen dize için sistem belleği ayırmayı deneyen [CStringT:: FormatMessage](#formatmessage)' ı çağırır. Bu deneme başarısız olursa, otomatik olarak bir bellek özel durumu oluşturulur.

Daha fazla bilgi için Windows SDK Windows [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) işlevine bakın.

## <a name="cstringtformatv"></a><a name="formatv"></a>CStringT:: FormatV

Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.

```cpp
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçim denetimi dizesini işaret eder. Bu, ekleme ve biçimlendirme için taranır. Biçim dizesi, `printf` parametrelerin rastgele bir sıraya eklenmesine izin verdiği sürece, çalışma zamanı işlev stili biçim dizelerine benzerdir.

*args*<br/>
Bağımsız değişken listesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Biçimli bir dize ve bağımsız değişkenlerin değişken listesini `CStringT` , `vsprintf_s` verileri C stili karakter dizisine biçimlendiren şekilde biçimlendirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

## <a name="cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a>CStringT:: GetEnvironmentVariable

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

## <a name="cstringtinsert"></a><a name="insert"></a>CStringT:: INSERT

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

## <a name="cstringtleft"></a><a name="left"></a>CStringT:: Left

Bu nesneden en soldaki *nCount* karakterlerini ayıklar `CStringT` ve ayıklanan alt dizenin bir kopyasını döndürür.

```
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>Parametreler

*nCount*<br/>
Bu nesneden Ayıklanacak karakter sayısı `CStringT` .

### <a name="return-value"></a>Dönüş Değeri

`CStringT`Belirtilen karakter aralığının bir kopyasını içeren nesne. Döndürülen `CStringT` nesne boş olabilir.

### <a name="remarks"></a>Açıklamalar

*NCount* dize uzunluğunu aşarsa, tüm dize ayıklanır. `Left`, temel `Left` işleve benzerdir.

Çok baytlı karakter kümeleri (MBCS) için *nCount* her 8 bit sırayı bir karakter olarak değerlendirir, bu nedenle *nCount* , çok baytlık karakterlerin sayısını ikiye çarparak döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

## <a name="cstringtloadstring"></a><a name="loadstring"></a>CStringT:: LoadString

*NID*tarafından tanımlanan bir Windows dize kaynağını varolan bir `CStringT` nesneye okur.

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

## <a name="cstringtmakelower"></a><a name="makelower"></a>CStringT:: MakeLower

`CStringT`Nesneyi küçük harfli bir dizeye dönüştürür.

```
CStringT& MakeLower();
```

### <a name="return-value"></a>Dönüş Değeri

Elde edilen küçük harfli dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

## <a name="cstringtmakereverse"></a><a name="makereverse"></a>CStringT:: MakeReverse

Nesnedeki karakterlerin sırasını tersine çevirir `CStringT` .

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>Dönüş Değeri

Elde edilen ters dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

## <a name="cstringtmakeupper"></a><a name="makeupper"></a>CStringT:: MakeUpper

`CStringT`Nesneyi büyük bir dizeye dönüştürür.

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan büyük dize.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

## <a name="cstringtmid"></a><a name="mid"></a>CStringT:: Mid

*nCount* `CStringT` *Ifırst* (sıfır tabanlı) konumundan başlayarak bu nesneden nCount karakter uzunluğunda bir alt dize ayıklar.

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>Parametreler

*ıfırst*<br/>
Bu `CStringT` nesnedeki, ayıklanan alt dizeye dahil edilecek ilk karakterin sıfır tabanlı dizini.

*nCount*<br/>
Bu nesneden Ayıklanacak karakter sayısı `CStringT` . Bu parametre sağlanmazsa, dizenin geri kalanı ayıklanır.

### <a name="return-value"></a>Dönüş Değeri

`CStringT`Belirtilen karakter aralığının bir kopyasını içeren nesne. Döndürülen `CStringT` nesnenin boş olabileceğini unutmayın.

### <a name="remarks"></a>Açıklamalar

İşlevi ayıklanan alt dizenin bir kopyasını döndürür. `Mid`, temel PARÇAAL işlevine benzerdir (temel olan dizinler tek tabanlı olur hariç).

Çok baytlı karakter kümeleri (MBCS) için *nCount* her 8 bit karaktere başvurur; diğer bir deyişle, bir çok baytlı karakter içindeki bir lider ve sondaki bayt iki karakter olarak sayılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

## <a name="cstringtoemtoansi"></a><a name="oemtoansi"></a>CStringT:: OemToAnsi

Bu nesnedeki tüm karakterleri `CStringT` OEM karakter KÜMESINDEN ANSI karakter kümesine dönüştürür.

```cpp
void OemToAnsi();
```

### <a name="remarks"></a>Açıklamalar

_UNICODE tanımlanmışsa bu işlev kullanılamaz.

### <a name="example"></a>Örnek

[CStringT:: Ansıtooem](#ansitooem)örneğine bakın.

## <a name="cstringtoperator-"></a><a name="operator_eq"></a>CStringT:: operator =

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
`CStringT`Bu dizeye atanacak bir.

*üstbilgisine*<br/>
Bir `CThisSimpleString` nesneye başvuru.

*bMFCDLL*<br/>
Projenin bir MFC DLL olup olmadığını belirten bir Boole değeri.

*BaseType*<br/>
Dize temel türü.

*l*<br/>
Bu dizeye atanacak bir değişken nesne.

*denetleyebilirsiniz*<br/>
Dizeye atanacak bir ANSI veya Unicode karakteri.

*pszSrc*<br/>
Atanmakta olan özgün dizeye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Atama işleci başka bir `CStringT` nesneyi, bir karakter işaretçisini veya tek bir karakteri kabul eder. Yeni depolama alanı ayrılabileceği için bu işleci her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın.

Hakkında bilgi için `CThisSimpleString` [CStringT:: CStringT](#cstringt)konusunun açıklamalar bölümüne bakın.

> [!NOTE]
> Gömülü null karakterler içeren örnekler oluşturmak mümkün olsa da `CStringT` , bunun için önerilir. Katıştırılmış null karakterler içeren nesnelerde Yöntemler ve işleçler çağırma `CStringT` istenmeden sonuçlar verebilir.

## <a name="cstringtoperator-"></a><a name="operator_add"></a>CStringT:: operator +

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
Bir `CStringT` dize veya karakterle birleştirmek için.

*str2*<br/>
Bir `CStringT` dize veya karakterle birleştirmek için.

*psz1*<br/>
Bir dize veya karakterle birleştirmek için null ile sonlandırılmış bir dize işaretçisi.

*psz2*<br/>
Dize veya karakterle birleştirilecek dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

İşlevin yedi aşırı yükleme biçimi vardır `CStringT::operator+` . İlk sürüm, varolan iki `CStringT` nesneyi birleştirir. Sonraki iki, bir `CStringT` nesneyi ve null ile sonlandırılmış dizeyi birleştirir. Sonraki iki bir `CStringT` nesne ve bır ANSI karakteri birleştirir. Son iki, bir `CStringT` nesneyi ve bir Unicode karakterini birleştirir.

> [!NOTE]
> Gömülü null karakterler içeren örnekler oluşturmak mümkün olsa da `CStringT` , bunun için önerilir. Katıştırılmış null karakterler içeren nesnelerde Yöntemler ve işleçler çağırma `CStringT` istenmeden sonuçlar verebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_add_eq"></a>CStringT:: operator + =

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
Bir `CThisSimpleString` nesneye başvuru.

*bMFCDLL*<br/>
Projenin bir MFC DLL olup olmadığını belirten bir Boole değeri.

*BaseType*<br/>
Dize temel türü.

*l*<br/>
Bu dizeyi birleştirmek için bir değişken nesne.

*denetleyebilirsiniz*<br/>
Bir dizeyle birleştirilecek ANSI veya Unicode karakteri.

*pszSrc*<br/>
Art arda eklenen orijinal dizeye yönelik bir işaretçi.

*strSrc*<br/>
`CStringT`Bu dizeyi birleştirmek için bir.

### <a name="remarks"></a>Açıklamalar

İşleç başka bir `CStringT` nesneyi, bir karakter işaretçisini veya tek bir karakteri kabul eder. Bu nesneye eklenen karakterler için yeni depolama alanı ayrılabileceği için, bu birleştirme işlecini her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın `CStringT` .

Hakkında bilgi için `CThisSimpleString` [CStringT:: CStringT](#cstringt)konusunun açıklamalar bölümüne bakın.

> [!NOTE]
> Gömülü null karakterler içeren örnekler oluşturmak mümkün olsa da `CStringT` , bunun için önerilir. Katıştırılmış null karakterler içeren nesnelerde Yöntemler ve işleçler çağırma `CStringT` istenmeden sonuçlar verebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_eq_eq"></a>CStringT:: operator = =

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
Bir `CStringT` karşılaştırma için.

*str2*<br/>
Bir `CStringT` karşılaştırma için.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir dizenin veya karakterin sağ taraftaki bir dizeye veya karaktere eşit olup olmadığını sınar ve doğru ya da yanlış değerlerini uygun bir şekilde döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_neq"></a>CStringT:: operator! =

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
Bir `CStringT` karşılaştırma için.

*str2*<br/>
Bir `CStringT` karşılaştırma için.

*psz1*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

*psz2*<br/>
Karşılaştırma için null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir dize veya karakter sağ taraftaki bir dizeye veya karaktere eşit değilse sınar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt"></a>CStringT:: işleci&lt;

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha az olup olmadığını belirler.

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Bir `CStringT` karşılaştırma için.

*str2*<br/>
Bir `CStringT` karşılaştırma için.

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

## <a name="cstringtoperator-gt"></a><a name="operator_gt"></a>CStringT:: işleci&gt;

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden daha büyük olup olmadığını belirler.

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Bir `CStringT` karşılaştırma için.

*str2*<br/>
Bir `CStringT` karşılaştırma için.

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

## <a name="cstringtoperator-lt"></a><a name="operator_lt_eq"></a>CStringT:: işleci&lt;=

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden küçük veya ona eşit olup olmadığını belirler.

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Bir `CStringT` karşılaştırma için.

*str2*<br/>
Bir `CStringT` karşılaştırma için.

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

## <a name="cstringtoperator-gt"></a><a name="operator_gt_eq"></a>CStringT:: işleci&gt;=

İşlecin sol tarafındaki dizenin sağ taraftaki dizeden büyük veya ona eşit olup olmadığını belirler.

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Bir `CStringT` karşılaştırma için.

*str2*<br/>
Bir `CStringT` karşılaştırma için.

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

## <a name="cstringtremove"></a><a name="remove"></a>CStringT:: Remove

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

## <a name="cstringtreplace"></a><a name="replace"></a>CStringT:: Replace

Öğesinin iki sürümü vardır `Replace` . İlk sürüm, bir alt dizenin bir veya daha fazla kopyasını başka bir alt dize kullanarak değiştirir. Her iki alt dize de null ile sonlandırılır. İkinci sürüm, bir karakterin bir veya daha fazla kopyasını başka bir karakter kullanarak değiştirir. Her iki sürüm de ' de depolanan karakter verilerinde çalışır `CStringT` .

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

`Replace`*pszNew* ve *pszOld* aynı uzunlukta olmadığından ve eski alt dizenin birkaç kopyası yeni bir tane olarak değiştirilebildiğinden, dize uzunluğunu değiştirebilir. İşlev, büyük/küçük harfe duyarlı bir eşleşme gerçekleştirir.

Örnek örnekleri `CStringT` `CString` , ve ' dir `CStringA` `CStringW` .

İçin `CStringA` , `Replace` ANSI veya çok BAYTLı (MBCS) karakterlerle birlikte kullanılır. İçin `CStringW` , `Replace` geniş karakterlerle işe yarar.

İçin `CString` , karakter veri türü, aşağıdaki tablodaki sabitlerin tanımlı olup olmadığına bağlı olarak, derleme zamanında seçilir.

|Tanımlı sabit|Karakter veri türü|
|----------------------|-------------------------|
|_UNICODE|Geniş karakterler|
|_MBCS|Çok baytlı karakterler|
|Hiçbiri|Tek baytlık karakterler|
|Her İkisi|Tanımlayan|

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

## <a name="cstringtreversefind"></a><a name="reversefind"></a>CStringT:: Smarfind

Bu `CStringT` nesneyi bir karakterin son eşleşmesi için arar.

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*<br/>
Aranacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Bu nesnedeki, istenen karakterle eşleşen son karakterin sıfır tabanlı dizini `CStringT` veya karakter bulunamazsa-1.

### <a name="remarks"></a>Açıklamalar

İşlevi, çalışma zamanı işlevine benzer `strrchr` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

## <a name="cstringtright"></a><a name="right"></a>CStringT:: Right

Bu nesneden en son (yani en sağdaki) *Nsayı* karakterini ayıklar `CStringT` ve ayıklanan alt dizenin bir kopyasını döndürür.

```
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>Parametreler

*nCount*<br/>
Bu nesneden Ayıklanacak karakter sayısı `CStringT` .

### <a name="return-value"></a>Dönüş Değeri

`CStringT`Belirtilen karakter aralığının bir kopyasını içeren nesne. Döndürülen `CStringT` nesnenin boş olabileceğini unutmayın.

### <a name="remarks"></a>Açıklamalar

*NCount* dize uzunluğunu aşarsa, tüm dize ayıklanır. `Right`, temel `Right` işleve benzerdir (temel içindeki dizinler sıfır tabanlı olur hariç).

Çok baytlı karakter kümeleri (MBCS) için *nCount* her 8 bit karaktere başvurur; diğer bir deyişle, bir çok baytlı karakter içindeki bir lider ve sondaki bayt iki karakter olarak sayılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

## <a name="cstringtsetsysstring"></a><a name="setsysstring"></a>CStringT:: SetSysString

, *Pbstr* tarafından Işaret edilen BSTR 'yi yeniden KONUMLANDıRıR ve `CStringT` null karakteri de dahil olmak üzere nesnenin içeriğini buna kopyalar.

```
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>Parametreler

*pbstr*<br/>
Karakter dizesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yeni dize.

### <a name="remarks"></a>Açıklamalar

Nesnenin içeriğine bağlı olarak `CStringT` , *pbstr* tarafından başvurulan BSTR 'nin değeri değişebilir. `CMemoryException`Yeterli bellek yoksa işlev bir oluşturur.

Bu işlev genellikle otomasyon için başvuruya göre geçirilen dizelerin değerini değiştirmek için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

## <a name="cstringtspanexcluding"></a><a name="spanexcluding"></a>CStringT:: Spanhariç tutma

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

`SpanExcluding`*pszCharSet* 'ten bir karakterin ilk örneğinden önceki tüm karakterleri ayıklar ve döndürür (diğer bir deyişle, *pszCharSet* ve dizedeki izleyen tüm karakterler döndürülmez). Dizede *pszCharSet* öğesinden bir karakter bulunamazsa, `SpanExcluding` tüm dizeyi döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

## <a name="cstringtspanincluding"></a><a name="spanincluding"></a>CStringT:: Spandahil

Dizeden, *pszCharSet*tarafından tanımlanan karakter kümesindeki ilk karakterle başlayarak karakterleri ayıklar.

```
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Parametreler

*pszCharSet*<br/>
Bir karakter kümesi olarak yorumlanan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Dizedeki ilk karakterle başlayan ve *pszCharSet*içinde olmayan dizede bir karakter bulunduğunda biten, *pszCharSet*içindeki dizedeki karakterleri içeren bir alt dize. `SpanIncluding`dizedeki ilk karakter belirtilen küme içinde değilse boş alt dizeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Dizenin ilk karakteri karakter kümesinde değilse, `SpanIncluding` boş bir dize döndürür. Aksi takdirde, küme içindeki ardışık karakterlerin dizisini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

## <a name="cstringttokenize"></a><a name="tokenize"></a>CStringT:: tokenize

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

`CStringT`Geçerli belirteç değerini içeren nesne.

### <a name="remarks"></a>Açıklamalar

`Tokenize`İşlevi, hedef dizedeki bir sonraki belirteci bulur. *PszTokens* içindeki karakter kümesi, bulunamayan belirtecin olası sınırlayıcılarını belirtir. İşleve yapılan her çağrıda, `Tokenize` *ısbaþlade*başlatılır, önde gelen sınırlayıcılar atlar ve `CStringT` sonraki sınırlayıcı karaktere kadar olan karakterlerin dizesi olan geçerli belirteci içeren bir nesne döndürür. *Isbaşlangıç* değeri bitiş sınırlayıcı karakteri izleyen konum olacak şekilde güncelleştirilir veya dizenin sonuna ulaşılırsa-1. Daha fazla belirteç, ' a bir dizi çağrı ile hedef dizenin geri kalanından ayrılabilir. Bu, bir `Tokenize` sonraki belirtecin nerede okunacağını izlemek Için *ısbaşlangıç* kullanılarak. Daha fazla belirteç yoksa, işlev boş bir dize döndürür ve *ısbaşlangıç* -1 olarak ayarlanır.

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

## <a name="cstringttrim"></a><a name="trim"></a>CStringT:: trim

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
Kırpılacak hedef karakterleri içeren bir dize işaretçisi. *PszTarget* 'daki karakterlerin tüm önde gelen ve sondaki oluşumları nesnesinden kırpılacak `CStringT` .

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

## <a name="cstringttrimleft"></a><a name="trimleft"></a>CStringT:: kırıt sola

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
Kırpılacak hedef karakterleri içeren bir dize işaretçisi. *PszTarget* 'daki karakterlerin tüm önde gelen oluşumları nesnesinden kırpılacak `CStringT` .

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan kırpılan dize.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin önde gelen ve sondaki oluşumlarını kaldırır:

- *ChTarget*tarafından belirtilen karakter.

- *PszTargets*tarafından belirtilen dizedeki tüm karakterler bulundu.

- Boşlu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

## <a name="cstringttrimright"></a><a name="trimright"></a>CStringT:: kırma sağ

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
Kırpılacak hedef karakterleri içeren bir dize işaretçisi. *PszTarget* içindeki karakterlerin tüm sondaki oluşumları `CStringT` nesnesinden kırpılır.

### <a name="return-value"></a>Dönüş Değeri

`CStringT`Kırpılan dizeyi içeren nesneyi döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin sondaki oluşumlarını kaldırır:

- *ChTarget*tarafından belirtilen karakter.

- *PszTargets*tarafından belirtilen dizedeki tüm karakterler bulundu.

- Boşlu.

`CStringT& TrimRight(XCHAR chTarget)`Sürüm bir karakter parametresini kabul eder ve dize verisinin sonundaki bu karakterin tüm kopyalarını kaldırır `CStringT` . Dizenin sonundan başlar ve önünde doğru çalışacaktır. Farklı bir karakter bulduğunda veya `CSTringT` karakter verilerinden çalıştırıldığında duraklar.

`CStringT& TrimRight(PCXSTR pszTargets)`Sürüm, aranacak tüm farklı karakterleri içeren null ile sonlandırılmış bir dizeyi kabul eder. Nesne içindeki bu karakterlerin tüm kopyalarını kaldırır `CStringT` . Dizenin sonunda başlar ve önünde doğru çalışacaktır. Hedef dizede olmayan bir karakter bulduğunda veya `CStringT` karakter verilerinden çalıştırıldığında duraklar. Tüm hedef dizeyi sonundaki bir alt dizeyle eşleştirmeye çalışmaz `CStringT` .

`CStringT& TrimRight()`Sürüm parametre gerektirmez. Dizenin sonundaki sondaki boşluk karakterlerini kırpar `CStringT` . Boşluk karakterleri satır sonları, boşluklar veya sekmeler olabilir.

-

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[CSimpleStringT sınıfı](../../atl-mfc-shared/reference/csimplestringt-class.md)
