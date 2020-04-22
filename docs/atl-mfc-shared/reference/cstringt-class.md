---
title: CStringT Sınıfı
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
ms.openlocfilehash: 8fcce4c426cd99785d34dc080f238cc78cdfee36
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746715"
---
# <a name="cstringt-class"></a>CStringT Sınıfı

Bu sınıf `CStringT` bir nesneyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>Parametreler

*BaseType*<br/>
String sınıfının karakter türü. Aşağıdakilerden biri olabilir:

- **char** (ANSI karakter dizeleri için).

- **wchar_t** (Unicode karakter dizeleri için).

- TCHAR (hem ANSI hem de Unicode karakter dizeleri için).

*Yaylı Çalgılar Özellikleri*<br/>
Dize sınıfının C Run-Time (CRT) Kitaplığı desteğine ihtiyacı olup olmadığını ve dize kaynaklarının nerede bulunduğunu belirler. Aşağıdakilerden biri olabilir:

- **StrTraitATL< &#124;** **char** &#124; **TCHAR, ChTraitsCRT< wchar_t** &#124; **char** &#124; **TCHAR > >** wchar_t &#124;

   Sınıf CRT desteği gerektirir ve (uygulamanın modül sınıfının bir üyesi) tarafından `m_hInstResource` belirtilen modüldeki kaynak dizeleri arar.

- **StrTraitATL< wchar_t< &#124;** **char** &#124; **TCHAR, ChTraitsOS< wchar_t** &#124; **char** &#124; **TCHAR > >**

   Sınıf CRT desteği gerektirmez ve (uygulamanın modül sınıfının `m_hInstResource` bir üyesi) tarafından belirtilen modüldeki kaynak dizeleri arar.

- **StrTraitMFC< wchar_t &#124;** **char** &#124; **TCHAR, ChTraitsCRT< wchar_t** &#124; **char** &#124; **TCHAR > >**

   Sınıf CRT desteği gerektirir ve standart MFC arama algoritmasını kullanarak kaynak dizeleri arar.

- **StrTraitMFC< wchar_t<** &#124; **char** &#124; **TCHAR, ChTraitsOS< wchar_t** wchar_t **&#124; char** &#124; **TCHAR > >**

   Sınıf CRT desteği gerektirmez ve standart MFC arama algoritmasını kullanarak kaynak dizeleri arar.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CStringT::CStringT](#cstringt)|Bir `CStringT` nesneyi çeşitli şekillerde inşa eder.|
|[CStringT::~CStringT](#_dtorcstringt)|Bir `CStringT` nesneyi yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStringT::AllocSysString](#allocsysstring)|Verilerden `CStringT` bir BSTR ayırır.|
|[CStringT::AnsiToOem](#ansitooem)|ANSI karakter kümesinden OEM karakter kümesine yerinde dönüştürme yapar.|
|[CStringT::AppendFormat](#appendformat)|Varolan `CStringT` bir nesneye biçimlendirilmiş verileri ekler.|
|[CStringT::Harmanlama](#collate)|İki dizeyi karşılaştırır (büyük/küçük harf duyarlı, yerel bilgilere özgü bilgileri kullanır).|
|[CStringT::CollateNoCase](#collatenocase)|İki dizeyi karşılaştırır (büyük/küçük harf duyarsız, yerel bilgilere özgü bilgileri kullanır).|
|[CStringT::Karşılaştır](#compare)|İki dizeyi karşılaştırır (büyük/küçük harf duyarlı).|
|[Cstringt::CompareNoCase](#comparenocase)|İki dize (büyük/küçük harf duyarsız) karşılaştırır.|
|[CStringT::Delete](#delete)|Bir dizedeki bir karakteri veya karakteri siler.|
|[CStringT::Bul](#find)|Daha büyük bir dize içinde bir karakter veya alt dize bulur.|
|[Cstringt::Findoneof](#findoneof)|Bir kümedeki ilk eşleşen karakteri bulur.|
|[CStringT::Biçim](#format)|Dizeyi olduğu `sprintf` gibi biçimlendirin.|
|[CStringT::BiçimMesajı](#formatmessage)|İleti dizelerini biçimlendirin.|
|[CStringT::BiçimMessageV](#formatmessagev)|Değişken bağımsız değişken listesi kullanarak ileti dizelerini biçimlendirin.|
|[CStringT::BiçimV](#formatv)|Değişken bir bağımsız değişken bağımsız değişken listesini kullanarak dizeyi biçimlendirin.|
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Dizeyi belirtilen ortam değişkeninin değerine ayarlar.|
|[CStringT::Ekle](#insert)|Dize içinde verilen dizine tek bir karakter veya bir alt dize ekler.|
|[CStringT::Sol](#left)|Bir dizenin sol kısmını ayıklar.|
|[CStringT::LoadString](#loadstring)|Varolan `CStringT` bir nesneyi Bir Windows kaynağından yükler.|
|[CStringT::MakeLower](#makelower)|Bu dizedeki tüm karakterleri küçük karakterlere dönüştürür.|
|[CStringT::Ters Yapma](#makereverse)|Dize tersine çevirir.|
|[CStringT::Makyaj](#makeupper)|Bu dizedeki tüm karakterleri büyük harf karakterlerine dönüştürür.|
|[CStringT::Orta](#mid)|Bir dizenin orta kısmını ayıklar.|
|[CStringT::OemToAnsi](#oemtoansi)|OEM karakter kümesinden ANSI karakter kümesine yerinde dönüştürme yapar.|
|[CStringT::Kaldır](#remove)|Belirtilen karakterleri bir dizeden kaldırır.|
|[CStringT::Değiştir](#replace)|Belirtilen karakterleri diğer karakterlerle değiştirir.|
|[CStringT::ReverseFind](#reversefind)|Daha büyük bir dize içinde bir karakter bulur; sonundan başlar.|
|[CStringT::Sağ](#right)|Bir dizenin sağ kısmını ayıklar.|
|[CStringT::SetSysString](#setsysstring)|Varolan bir BSTR nesnesini `CStringT` bir nesneden gelen verilerle ayarlar.|
|[CStringT::SpanExcluding](#spanexcluding)|İlk karakterden başlayarak, tanımlanan karakter `pszCharSet`kümesinde olmayan karakterleri dizeden özler.|
|[CStringT::SpanIncluding](#spanincluding)|Yalnızca bir kümedeki karakterleri içeren bir alt dize ayıklar.|
|[CStringT::Tokenize](#tokenize)|Hedef dizesinde belirtilen belirteçleri ayıklar.|
|[CStringT::Kırpma](#trim)|Dizedeki tüm önde gelen ve sondaki beyaz uzay karakterlerini kırpar.|
|[CStringT::TrimLeft](#trimleft)|Dizedeki önde gelen beyaz uzay karakterlerini kırpar.|
|[CStringT::Trimright](#trimright)|Dizedeki beyaz boşluk karakterlerini kırpar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[CStringT::işleç =](#operator_eq)|Nesneye yeni bir `CStringT` değer atar.|
|[CStringT::operatör +](#operator_add)|İki dize veya bir karakter ve bir dize birleştirir.|
|[CStringT::işleç +=](#operator_add_eq)|Varolan bir dize sonuna yeni bir dize concatenates.|
|[CStringT::işleç ==](#operator_eq_eq)|İki dize mantıksal olarak eşit olup olmadığını belirler.|
|[CStringT::işleç !=](#operator_neq)|İki dize mantıksal olarak eşit değilse belirler.|
|[CStringT::işleç&lt;](#operator_lt)|İşleticinin sol tarafındaki dize sağ taraftaki dizeden daha az olup olmadığını belirler.|
|[CStringT::işleç&gt;](#operator_gt)|İşleticinin sol tarafındaki dize sağ taraftaki dizeden daha büyük olup olmadığını belirler.|
|[CStringT::işleç&lt;=](#operator_lt_eq)|İşleticinin sol tarafındaki dize, sağ taraftaki dizeden daha az mı yoksa eşit mi olduğunu belirler.|
|[CStringT::işleç&gt;=](#operator_gt_eq)|İşleticinin sol tarafındaki dize, sağ taraftaki dizeden büyük mü yoksa eşit mi olduğunu belirler.|

## <a name="remarks"></a>Açıklamalar

`CStringT`[CSimpleStringT Sınıfından](../../atl-mfc-shared/reference/csimplestringt-class.md)devralır. Karakter işleme, sıralama ve arama gibi gelişmiş `CStringT`özellikler.

> [!NOTE]
> `CStringT`nesneler özel durumlar atma yeteneğine sahiptir. Bu, bir `CStringT` nesnenin herhangi bir nedenle belleği bittiğinde oluşur.

Bir `CStringT` nesne, değişken uzunluktabir karakter dizisinden oluşur. `CStringT`Basic'inkine benzer sözdizimi kullanarak işlevler ve işleçler sağlar. Birleştirme ve karşılaştırma işleçleri, basitleştirilmiş bellek `CStringT` yönetimiyle birlikte nesnelerin sıradan karakter dizilerinden daha kolay kullanılmasını kolaylaştırır.

> [!NOTE]
> Gömülü null karakterleri `CStringT` içeren örnekler oluşturmak mümkün olsa da, buna karşı öneririz. Katışmış null `CStringT` karakterleri içeren nesnelerüzerinde arama yöntemleri ve işleçleri istenmeyen sonuçlar üretebilir.

Farklı `BaseType` `StringTraits` parametre kombinasyonları kullanılarak, `CStringT` nesneler ATL kitaplıkları tarafından önceden tanımlanmış olan aşağıdaki türlerde gelebilir.

ATL uygulamasında kullanıyorsanız:

`CString`, `CStringA`, `CStringW` Ve MFC DLL (MFC90) ihraç edilir. DLL), kullanıcı DLs asla. Bu, tanımlanan `CStringT` çarpmanın önüne gelmek için yapılır.

> [!NOTE]
> [Kodunuz, CStringT kullanarak String Sınıfları Dışa Aktarma](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md)açıklanan bağlayıcı hataları için geçici çözüm içeriyorsa, bu kodu kaldırmanız gerekir. Artık buna ihtiyacınız yoktur.

Aşağıdaki dize türleri MFC tabanlı uygulamalar da kullanılabilir:

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CStringA`|CRT destekli bir ANSI karakter türü dizesi.|
|`CStringW`|CRT destekli Bir Unicode karakter türü dizesi.|
|`CString`|CRT destekli ANSI ve Unicode karakter türleri.|

ATL_CSTRING_NO_CRT tanımlandığı projelerde aşağıdaki dize türleri kullanılabilir:

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CAtlStringA`|CRT desteği olmayan bir ANSI karakter türü dizesi.|
|`CAtlStringW`|CRT desteği olmayan BirUnicode karakter türü dizesi.|
|`CAtlString`|CRT desteği olmayan HEM ANSI hem de Unicode karakter türleri.|

ATL_CSTRING_NO_CRT tanımlanmamış projelerde aşağıdaki dize türleri kullanılabilir:

|CStringT türü|Bildirim|
|-------------------|-----------------|
|`CAtlStringA`|CRT destekli bir ANSI karakter türü dizesi.|
|`CAtlStringW`|CRT destekli Bir Unicode karakter türü dizesi.|
|`CAtlString`|CRT destekli ANSI ve Unicode karakter türleri.|

`CString`nesneler de aşağıdaki özelliklere sahiptir:

- `CStringT`nesneleri concatenation işlemleri sonucunda büyüyebilir.

- `CStringT`nesneler "değer semantik" izleyin. Bir `CStringT` nesneyi bir dize işaretçisi olarak değil, gerçek bir dize olarak düşünün.

- Nesneleri işlev bağımsız `CStringT` değişkenleri `PCXSTR` için serbestçe değiştirebilirsiniz.

- Dize arabellekleri için özel bellek yönetimi. Daha fazla bilgi için [Bellek Yönetimi ve CStringT'e](../../atl-mfc-shared/memory-management-with-cstringt.md)bakın.

## <a name="cstringt-predefined-types"></a>CStringT Önceden Tanımlanmış Türleri

Desteklenen `CStringT` karakter türünü [(wchar_t](../../c-runtime-library/standard-types.md) veya [char)](../../c-runtime-library/standard-types.md)tanımlamak için bir şablon bağımsız değişkeni kullandığından, yöntem parametre türleri zaman zaman karmaşık olabilir. Bu sorunu basitleştirmek için, önceden tanımlanmış türler kümesi `CStringT` tanımlanır ve sınıf boyunca kullanılır. Aşağıdaki tabloçeşitli türleri listeler:

|Adı|Açıklama|
|----------|-----------------|
|`XCHAR`|`CStringT` Nesneyle aynı karakter türüne sahip tek bir karakter **(wchar_t** veya **char).**|
|`YCHAR`|`CStringT` Nesne olarak karşıt karakter türüne sahip tek bir karakter **(wchar_t** veya **char).**|
|`PXSTR`|Nesneyle aynı karakter türüne sahip bir karakter dizesine `CStringT` **(wchar_t** veya **char)** işaretçisi.|
|`PYSTR`|Nesne olarak karşıt karakter türüne sahip bir karakter dizesine **(wchar_t** veya **char)** işaretçisi. `CStringT`|
|`PCXSTR`|Nesneyle aynı karakter türüne sahip **const** karakter dizesini `CStringT` **(wchar_t** veya **char)** işaretçisi.|
|`PCYSTR`|Nesne olarak karşıt karakter türüne sahip **const** karakter dizesini **(wchar_t** veya **char)** işaretçisi. `CStringT`|

> [!NOTE]
> Daha önce belgelenmemiş yöntemler `CString` (örneğin) `AssignCopy`kullanılan kod, aşağıdaki belgelenmiş yöntemleri `CStringT` (örneğin `GetBuffer` veya) `ReleaseBuffer`kullanan kodla değiştirilmelidir. Bu yöntemler den `CSimpleStringT`kalıtsaldır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Csimplestringt](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>Gereksinimler

|Üst bilgi|Şunun için kullanın:|
|------------|-------------|
|cstringt.h|MFC yalnızca dize nesneleri|
|atlstr.h|MFC olmayan dize nesneleri|

## <a name="cstringtallocsysstring"></a><a name="allocsysstring"></a>CStringT::AllocSysString

BSTR türünün Otomasyon uyumlu bir dizesini ayırır ve `CStringT` sonlandırıcı null karakteri de dahil olmak üzere nesnenin içeriğini ona kopyalar.

```
BSTR AllocSysString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan dize.

### <a name="remarks"></a>Açıklamalar

MFC programlarında, yetersiz bellek varsa [cmemoryexception sınıfı](../../mfc/reference/cmemoryexception-class.md) atılır. ATL programlarında [catlException](../../atl/reference/catlexception-class.md) atılır. Bu işlev normalde Otomasyon dizeleri döndürmek için kullanılır.

Genellikle, bu dize bir [in] parametresi olarak bir COM işlevine aktarılırsa, bu, arayanın dizeyi serbest çeştirmesini gerektirir. Bu [SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)kullanılarak yapılabilir , Windows SDK açıklandığı gibi. Daha fazla bilgi için [bstr için Bellek Ayırma ve Serbest Bırakma'ya](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)bakın.

Windows'daki OLE ayırma işlevleri hakkında daha fazla bilgi için Windows SDK'daki [SysAllocString'e](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CStringT::AllocSysString`

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

## <a name="cstringtansitooem"></a><a name="ansitooem"></a>CStringT::AnsiToOem

Bu `CStringT` nesnedeki tüm karakterleri ANSI karakter kümesinden OEM karakter kümesine dönüştürür.

```cpp
void AnsiToOem();
```

### <a name="remarks"></a>Açıklamalar

_UNICODE tanımlanırsa işlev kullanılamaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

## <a name="cstringtappendformat"></a><a name="appendformat"></a>CStringT::AppendFormat

Varolan `CStringT` bir nesneye biçimlendirilmiş verileri ekler.

```cpp
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçim denetimi dizesi.

*nFormatID*<br/>
Biçim denetimi dizesini içeren dize kaynak tanımlayıcısı.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

Bu işlev biçimleri ve karakter ve değerler bir `CStringT`dizi ekler. Her isteğe bağlı bağımsız değişken (varsa) *pszFormat'taki* ilgili biçim belirtimine veya *nFormatID*tarafından tanımlanan dize kaynağından dönüştürülür ve eklenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

## <a name="cstringtcollate"></a><a name="collate"></a>CStringT::Harmanlama

Genel metin işlevini `_tcscoll`kullanarak iki dizeyi karşılaştırır.

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*Psz*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeleri aynı ysa sıfır, bu `CStringT` nesne psz'den küçükse 0 < veya bu `CStringT` nesne *psz'den*büyükse 0'>. *psz*

### <a name="remarks"></a>Açıklamalar

TCHAR'da `_tcscoll`tanımlanan genel metin işlevi. H, derleme `strcoll`zamanında `wcscoll`tanımlanan `_mbscoll`karakter kümesine bağlı olarak , , veya , ile eşler. Her işlev, şu anda kullanılmakta olan kod sayfasına göre dizeleri büyük/küçük harf duyarlı bir karşılaştırma gerçekleştirir. Daha fazla bilgi için [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l.](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)

## <a name="cstringtcollatenocase"></a><a name="collatenocase"></a>CStringT::CollateNoCase

Genel metin işlevini `_tcscoll`kullanarak iki dizeyi karşılaştırır.

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*Psz*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeleri aynıysa (büyük/küçük harf yoksayma), bu `CStringT` nesne psz'den küçükse (büyük/küçük harf eki)'den daha azsa 0'ı < veya bu `CStringT` nesne *psz'den* büyükse (büyük/küçük harf yoksayan) 0'ı >. *psz*

### <a name="remarks"></a>Açıklamalar

TCHAR'da `_tcscoll`tanımlanan genel metin işlevi. H, derleme `stricoll`zamanında `wcsicoll`tanımlanan `_mbsicoll`karakter kümesine bağlı olarak , , veya , ile eşler. Her işlev, şu anda kullanılmakta olan kod sayfasına göre dizeleri duyarsız bir karşılaştırma gerçekleştirir. Daha fazla bilgi için [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l.](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

## <a name="cstringtcompare"></a><a name="compare"></a>CStringT::Karşılaştır

İki dizeyi karşılaştırır (büyük/küçük harf duyarlı).

```
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>Parametreler

*Psz*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeleri aynı ysa sıfır, bu `CStringT` nesne psz'den küçükse 0 < veya bu `CStringT` nesne *psz'den*büyükse 0'>. *psz*

### <a name="remarks"></a>Açıklamalar

TCHAR'da `_tcscmp`tanımlanan genel metin işlevi. H, derleme `strcmp`zamanında `wcscmp`tanımlanan `_mbscmp`karakter kümesine bağlı olarak , , veya , ile eşler. Her işlev dizeleri büyük/küçük harf duyarlı bir karşılaştırma gerçekleştirir ve yerel etkietkilenmez. Daha fazla bilgi için [strcmp, wcscmp, _mbscmp.](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)

Dize katıştırılmış nulls içeriyorsa, karşılaştırma amacıyla dize ilk katıştırılmış null karakter de kesilmiş olarak kabul edilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CStringT::Compare`

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

## <a name="cstringtcomparenocase"></a><a name="comparenocase"></a>Cstringt::CompareNoCase

İki dize (büyük/küçük harf duyarsız) karşılaştırır.

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parametreler

*Psz*<br/>
Karşılaştırma için kullanılan diğer dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeleri aynıysa (büyük/küçük harf yoksayan), bu `CStringT` nesne psz'den (büyük/küçük harf eki)'den daha azsa 0'ı <veya bu `CStringT` nesne *psz'den* büyükse (büyük/küçük harf yoksayan) 0'ı >. *psz*

### <a name="remarks"></a>Açıklamalar

TCHAR'da `_tcsicmp`tanımlanan genel metin işlevi. H, derleme `_stricmp`zamanında `_wcsicmp` `_mbsicmp`tanımlanan karakter kümesine bağlı olarak , veya , eşler. Her işlev dizeleri bir büyük/küçük harf duyarsız karşılaştırma gerçekleştirir. Karşılaştırma, yerel in LC_CTYPE yönü bağlıdır, ancak LC_COLLATE. Daha fazla bilgi için [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l.](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

## <a name="cstringtcstringt"></a><a name="cstringt"></a>CStringT::CStringT

Bir `CStringT` nesne inşa eder.

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

*Pch*<br/>
Uzunluk *nLength*karakter dizisi için bir işaretçi , null-sonlandırılma.

*nUzunluk*<br/>
*pch'deki*karakter sayısının sayısı.

*Caner*<br/>
Tek bir karakter.

*pszSrc*<br/>
Bu `CStringT` nesneye kopyalanacak null-sonlandırılan dize.

*pStringMgr*<br/>
Nesne için bellek yöneticisine `CStringT` bir işaretçi. Için daha `IAtlStringMgr` fazla bilgi `CStringT`ve bellek yönetimi için , [CStringT ile Bellek Yönetimi](../../atl-mfc-shared/memory-management-with-cstringt.md)bakın.

*strSrc*<br/>
Varolan `CStringT` bir nesne bu `CStringT` nesneye kopyalanacak. Hakkında daha `CThisString` fazla `CThisSimpleString`bilgi için Açıklamalar bölümüne bakın.

*varSrc*<br/>
Bu `CStringT` nesneye kopyalanacak bir varyant nesne.

*BaseType*<br/>
String sınıfının karakter türü. Aşağıdakilerden biri olabilir:

**char** (ANSI karakter dizeleri için).

**wchar_t** (Unicode karakter dizeleri için).

TCHAR (hem ANSI hem de Unicode karakter dizeleri için).

*bMFCDLL*<br/>
Boolean bu proje bir MFC DLL (TRUE) ya da (FALSE) olup olmadığını belirtir.

*SystemString*<br/>
Olmalıdır `System::String`ve proje / clr ile derlenmiş olmalıdır.

*pString*<br/>
Bir `CStringT` nesne için tutamaç.

### <a name="remarks"></a>Açıklamalar

Kurucular giriş verilerini yeni ayrılmış depolama alanına kopyaladığı için, bellek özel durumlarının neden olabileceğini unutmayın. Bu kuruculardan bazılarının dönüşüm işlevleri olarak hareket ettiğini unutmayın. Bu, örneğin bir `CStringT` nesnenin beklendiği bir LPTSTR'yi yerine geçmenizi sağlar.

- `CStringT`( `LPCSTR` `lpsz` ): Bir ANSI dizesinden unicode `CStringT` kurar. Bu oluşturucuyu, aşağıdaki örnekte gösterildiği gibi bir dize kaynağı yüklemek için de kullanabilirsiniz.

- `CStringT(`): Unicode dizesinden bir a `CStringT` inşa eder. `LPCWSTR` `lpsz`

- `CStringT`( `const unsigned char*` `psz` ): İşaretçiden `CStringT` **imzasız char'a**bir işaretçi oluşturmanızı sağlar.

> [!NOTE]
> ANSI ve Unicode dizeleri arasında örtük dize dönüştürme kapatmak için _CSTRING_DISABLE_NARROW_WIDE_CONVERSION makro tanımlayın. Makro, dönüştürmeyi destekleyen derleme oluşturucuları hariç tutar.

*strSrc* parametresinin bir `CStringT` veya `CThisSimpleString` nesne olabileceğini unutmayın. Bunun `CStringT`için, varsayılan anlık kullanımlarından`CString` `CStringA`birini `CStringW`kullanın ( , , veya ); için, `CThisSimpleString` **bu** işaretçikullanın. `CThisSimpleString``CStringT` [csimplestringt sınıfının](../../atl-mfc-shared/reference/csimplestringt-class.md)bir örneğini bildirir, hangi sınıftan daha az yerleşik işlevselliği ile daha küçük bir dize sınıfıdır.

Aşırı yük `CSimpleStringT<>&()` işleci `CStringT` bir `CSimpleStringT` bildirimden bir nesne inşa eder.

> [!NOTE]
> Gömülü null karakterleri `CStringT` içeren örnekler oluşturmak mümkün olsa da, buna karşı öneririz. Katışmış null `CStringT` karakterleri içeren nesnelerüzerinde arama yöntemleri ve işleçleri istenmeyen sonuçlar üretebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

## <a name="cstringtcstringt"></a><a name="_dtorcstringt"></a>CStringT::~CStringT

Nesneyi `CStringT` yok eder.

```
~CStringT() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi `CStringT` yok eder.

## <a name="cstringtdelete"></a><a name="delete"></a>CStringT::Delete

Verilen dizindeki karakterle başlayan bir dizeden bir karakteri veya karakteri siler.

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
Silmek için `CStringT` nesnedeki ilk karakterin sıfır tabanlı dizin.

*nSayısı*<br/>
Kaldırılacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen dizenin uzunluğu.

### <a name="remarks"></a>Açıklamalar

*nCount* dizeden daha uzunsa, dizegeri kalanı kaldırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

## <a name="cstringtfind"></a><a name="find"></a>CStringT::Bul

Bu dizeyi bir karakterin veya alt dizenin ilk eşleşmesi için arar.

```
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>Parametreler

*pszSub*<br/>
Aranacak bir alt dize.

*iBaşlat*<br/>
Aramaya başlamak için dizdeki karakterin dizini veya başlangıçtan başlamak için 0.

*Caner*<br/>
Aranacak tek bir karakter.

### <a name="return-value"></a>Dönüş Değeri

İstenen alt dize veya `CStringT` karakterlerle eşleşen bu nesnedeki ilk karakterin sıfır tabanlı dizini; -1 alt dize veya karakter bulunamazsa.

### <a name="remarks"></a>Açıklamalar

İşlev, her iki tek karakteri (çalışma zamanı işlevine `strchr`benzer) ve dizeleri (benzer) kabul etmek için aşırı `strstr`yüklenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

## <a name="cstringtfindoneof"></a><a name="findoneof"></a>Cstringt::Findoneof

*PszCharSet'te*bulunan herhangi bir karakterle eşleşen ilk karakter için bu dizeyi arar.

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>Parametreler

*pszCharSet*<br/>
Eşleştirme için karakterler içeren dize.

### <a name="return-value"></a>Dönüş Değeri

*PszCharSet*de bu dize ilk karakterin sıfır tabanlı dizin ; -1 eşleşme yoksa.

### <a name="remarks"></a>Açıklamalar

*pszCharSet'teki*karakterlerden herhangi birinin ilk oluşumunu bulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

## <a name="cstringtformat"></a><a name="format"></a>CStringT::Biçim

Biçimlendirilmiş verileri, `CStringT` [sprintf_s'nin](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) verileri C stili karakter dizisine biçimlendirmesi gibi yazar.

```cpp
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>Parametreler

*nFormatID*<br/>
Biçim denetimi dizesini içeren dize kaynak tanımlayıcısı.

*pszFormat*<br/>
Biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir dizi karakter ve değeri `CStringT`biçimlendirin ve depolar. Her isteğe bağlı bağımsız değişken (varsa) dönüştürülür ve *pszFormat'taki* ilgili biçim belirtimine veya *nFormatID*tarafından tanımlanan string kaynağından çıktılanır.

Dize nesnesinin kendisi parametre olarak sunulursa `Format`çağrı başarısız olur. Örneğin, aşağıdaki kod öngörülemeyen sonuçlara neden olur:

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

Daha fazla bilgi için [bkz: Biçim Belirtimi: printf ve wprintf Fonksiyonları.](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

## <a name="cstringtformatmessage"></a><a name="formatmessage"></a>CStringT::BiçimMesajı

İleti dizelerini biçimlendirin.

```cpp
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>Parametreler

*nFormatID*<br/>
Biçimlendirilmemiş ileti metnini içeren dize kaynak tanımlayıcısı.

*pszFormat*<br/>
Biçim denetimi dizesini işaret edin. Ekler için taranır ve buna göre biçimlendirilir. Biçim dizesi, parametrelerin rasgele bir sırada eklenmesine izin vermesi dışında, çalışma zamanı *işlevprintf*-style format dizelerine benzer.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

İşlev giriş olarak bir ileti tanımı gerektirir. İleti tanımı *pszFormat* veya *nFormatID*tarafından tanımlanan dize kaynağından belirlenir. İşlev, biçimlendirilmiş ileti metnini `CStringT` nesneye kopyalar ve istenirse katıştirilmiş ekleme dizilerini işler.

> [!NOTE]
> `FormatMessage`yeni biçimlendirilmiş dize için sistem belleği ayırmaya çalışır. Bu girişim başarısız olursa, bir bellek özel durum otomatik olarak atılır.

Her kesici *uç, pszFormat* veya *nFormatID* parametresini izleyen karşılık gelen bir parametreye sahip olmalıdır. İleti metni içinde, iletinin dinamik biçimlendirmesi için birkaç kaçış sırası desteklenir. Daha fazla bilgi için Windows SDK'daki Windows [Biçimmesajı](/windows/win32/api/winbase/nf-winbase-formatmessage) işlevine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

## <a name="cstringtformatmessagev"></a><a name="formatmessagev"></a>CStringT::BiçimMessageV

Değişken bağımsız değişken listesi kullanarak ileti dizelerini biçimlendirin.

```cpp
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçim denetimi dizesini işaret edin. Ekler için taranır ve buna göre biçimlendirilir. Biçim dizesi, parametrelerin `printf`rasgele bir sırada eklenmesine izin vermesi dışında, çalışma zamanı işlev -stil biçimleri dizelerine benzer.

*pArgList*<br/>
Bağımsız değişkenler listesine işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlev, *pszFormat*tarafından belirlenen giriş olarak bir ileti tanımı gerektirir. İşlev, biçimlendirilmiş ileti metnini ve nesnenin `CStringT` bağımsız değişken listesini kopyalar ve istenirse katıştirilmiş ekleme dizilerini işler.

> [!NOTE]
> `FormatMessageV`[cStringT çağırır::FormatMessage](#formatmessage), yeni biçimlendirilmiş dize için sistem belleği ayırmaya çalışır. Bu girişim başarısız olursa, bir bellek özel durum otomatik olarak atılır.

Daha fazla bilgi için Windows SDK'daki Windows [Biçimmesajı](/windows/win32/api/winbase/nf-winbase-formatmessage) işlevine bakın.

## <a name="cstringtformatv"></a><a name="formatv"></a>CStringT::BiçimV

Değişken bağımsız değişken listesi kullanarak ileti dizelerini biçimlendirin.

```cpp
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçim denetimi dizesini işaret edin. Ekler için taranır ve buna göre biçimlendirilir. Biçim dizesi, parametrelerin `printf`rasgele bir sırada eklenmesine izin vermesi dışında, çalışma zamanı işlev -stil biçimleri dizelerine benzer.

*Args*<br/>
Bağımsız değişkenler listesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Verileri C stili karakter dizisine biçimlendirecek `CStringT` `vsprintf_s` şekilde biçimlendirilmiş bir dize ve bağımsız değişken bir bağımsız değişken listesini bir dize yazar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

## <a name="cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a>CStringT::GetEnvironmentVariable

Dizeyi belirtilen ortam değişkeninin değerine ayarlar.

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>Parametreler

*pszVar*<br/>
Ortam değişkenini belirten null-sonlandırılan dize işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çağrı işleminin ortam bloğundan belirtilen değişkenin değerini alır. Değer, null-terminatedli karakter dizisi şeklindedir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

## <a name="cstringtinsert"></a><a name="insert"></a>CStringT::Ekle

Dize içinde verilen dizine tek bir karakter veya bir alt dize ekler.

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
Eklemenin yapılacağı karakterin dizini.

*Psz*<br/>
Eklenecek alt dize için bir işaretçi.

*Caner*<br/>
Eklenecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen dizenin uzunluğu.

### <a name="remarks"></a>Açıklamalar

*iIndex* parametresi, karakter e veya alt dize için yer açmak için taşınacak ilk karakteri tanımlar. *nIndex* sıfır ise, ekleme tüm dize önce oluşur. *nIndex* dize uzunluğundan daha yüksekse, işlev mevcut dize ve *ch* veya *psz*tarafından sağlanan yeni malzeme yi birleştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

## <a name="cstringtleft"></a><a name="left"></a>CStringT::Sol

Bu `CStringT` nesneden en soldaki *nCount* karakterlerini ayıklar ve ayıklanan alt dizenin bir kopyasını döndürür.

```
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>Parametreler

*nSayısı*<br/>
Bu `CStringT` nesneden ayıklamak için karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen `CStringT` karakter aralığının bir kopyasını içeren bir nesne. Döndürülen `CStringT` nesne boş olabilir.

### <a name="remarks"></a>Açıklamalar

*nCount* dize uzunluğunu aşarsa, tüm dize ayıklanır. `Left`Temel `Left` işlevine benzer.

Çok baytkarakter kümeleri (MBCS) için *nCount* her 8 bitlik diziyi karakter olarak ele verir, böylece *nCount* iki ile çarpılarak çok bayt karakter sayısını döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

## <a name="cstringtloadstring"></a><a name="loadstring"></a>CStringT::LoadString

*NID*tarafından tanımlanan bir Windows dize `CStringT` kaynağını varolan bir nesneye okur.

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>Parametreler

*Hınstance*<br/>
Modülün örneğine bir tutamaç.

*Nıd*<br/>
Windows dize kaynak kimliği.

*wLanguageID*<br/>
Dize kaynağının dili.

### <a name="return-value"></a>Dönüş Değeri

Kaynak yükü başarılı ysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen modülden string kaynağını *(nID)* yükler (*hInstance*) belirtilen dili kullanarak (*wLanguage*).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

## <a name="cstringtmakelower"></a><a name="makelower"></a>CStringT::MakeLower

Nesneyi `CStringT` küçük bir dize dönüştürür.

```
CStringT& MakeLower();
```

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan küçük harf dizesi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

## <a name="cstringtmakereverse"></a><a name="makereverse"></a>CStringT::Ters Yapma

`CStringT` Nesnedeki karakterlerin sırasını tersine çevirir.

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan ters dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

## <a name="cstringtmakeupper"></a><a name="makeupper"></a>CStringT::Makyaj

Nesneyi `CStringT` büyük harf dizesine dönüştürür.

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan büyük harf dizesi.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

## <a name="cstringtmid"></a><a name="mid"></a>CStringT::Orta

Bu `CStringT` nesneden *iFirst* (sıfır tabanlı) konumundan başlayarak bir uzunluk *nCount* karakter alt dizesini ayıklar.

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>Parametreler

*iFirst*<br/>
Ayıklanan alt dize eklenecek olan `CStringT` bu nesnedeki ilk karakterin sıfır tabanlı dizin.

*nSayısı*<br/>
Bu `CStringT` nesneden ayıklamak için karakter sayısı. Bu parametre sağlanmazsa, dizegeri kalanı ayıklanır.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen `CStringT` karakter aralığının bir kopyasını içeren bir nesne. Döndürülen `CStringT` nesnenin boş olabileceğini unutmayın.

### <a name="remarks"></a>Açıklamalar

İşlev, ayıklanan alt dizeğin bir kopyasını döndürür. `Mid`Temel Orta işlevine benzer (Temel'deki dizinlerin tek tabanlı olması hariç).

Çok bayt karakter kümeleri (MBCS) için *nCount* her 8 bitkarakteranlamına gelir; diğer bir deyişle, bir çok bayt karakterde bir kurşun ve iz bayt iki karakter olarak sayılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

## <a name="cstringtoemtoansi"></a><a name="oemtoansi"></a>CStringT::OemToAnsi

Bu `CStringT` nesnedeki tüm karakterleri OEM karakter kümesinden ANSI karakter kümesine dönüştürür.

```cpp
void OemToAnsi();
```

### <a name="remarks"></a>Açıklamalar

_UNICODE tanımlanırsa bu işlev kullanılamaz.

### <a name="example"></a>Örnek

CStringT örneğine [bakın:AnsiToOem](#ansitooem).

## <a name="cstringtoperator-"></a><a name="operator_eq"></a>CStringT::işleç =

Dize yeni bir değer atar.

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
A `CStringT` bu dize atamak için.

*Str*<br/>
Bir `CThisSimpleString` nesneye başvuru.

*bMFCDLL*<br/>
Projenin Bir MFC DLL olup olmadığını belirten bir boolean.

*BaseType*<br/>
Dize taban türü.

*var*<br/>
Bu dize atamak için bir varyant nesne.

*Caner*<br/>
Dize atamak için bir ANSI veya Unicode karakteri.

*pszSrc*<br/>
Atanan özgün dize için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Atama işleci başka `CStringT` bir nesneyi, bir karakter işaretçisini veya tek bir karakteri kabul eder. Yeni depolama alanı ayrılabildiği için, bu işleci her kullandığınızda bellek özel durumlarının oluşabileceğini unutmayın.

Hakkında bilgi `CThisSimpleString`için, CStringT Açıklamalar bölümüne [bakın:CStringT](#cstringt).

> [!NOTE]
> Gömülü null karakterleri `CStringT` içeren örnekler oluşturmak mümkün olsa da, buna karşı öneririz. Katışmış null `CStringT` karakterleri içeren nesnelerüzerinde arama yöntemleri ve işleçleri istenmeyen sonuçlar üretebilir.

## <a name="cstringtoperator-"></a><a name="operator_add"></a>CStringT::operatör +

İki dize veya bir karakter ve bir dize birleştirir.

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

*ch2*<br/>
Bir dize ile birleştirmek için bir ANSI veya Unicode karakter.

*str1*<br/>
A `CStringT` bir dize veya karakter ile concatenate için.

*str2*<br/>
A `CStringT` bir dize veya karakter ile concatenate için.

*psz1*<br/>
Bir dize veya karakterle birleştirmek için null-sonlandırılan dize için bir işaretçi.

*psz2*<br/>
Bir dize veya karakter le birleştirmeye işaretçi.

### <a name="remarks"></a>Açıklamalar

Fonksiyonun `CStringT::operator+` yedi aşırı yük formu vardır. İlk sürüm, varolan `CStringT` iki nesneyi birleştirir. Sonraki iki bir `CStringT` nesne ve null-sonlandırılan dize birleştirir. Sonraki iki bir `CStringT` nesne ve bir ANSI karakteri birleştirir. Son iki bir `CStringT` nesne ve unicode karakter birleştirir.

> [!NOTE]
> Gömülü null karakterleri `CStringT` içeren örnekler oluşturmak mümkün olsa da, buna karşı öneririz. Katışmış null `CStringT` karakterleri içeren nesnelerüzerinde arama yöntemleri ve işleçleri istenmeyen sonuçlar üretebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_add_eq"></a>CStringT::işleç +=

Karakterleri dize sonuna kadar birleştirir.

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

*Str*<br/>
Bir `CThisSimpleString` nesneye başvuru.

*bMFCDLL*<br/>
Projenin Bir MFC DLL olup olmadığını belirten bir boolean.

*BaseType*<br/>
Dize taban türü.

*var*<br/>
Bu dize için concatenate bir varyant nesne.

*Caner*<br/>
Bir dize ile birleştirmek için bir ANSI veya Unicode karakter.

*pszSrc*<br/>
Özgün dize için bir işaretçi concatenated ediliyor.

*strSrc*<br/>
A `CStringT` bu dize için concatenate.

### <a name="remarks"></a>Açıklamalar

İşleç başka `CStringT` bir nesneyi, bir karakter işaretçisini veya tek bir karakteri kabul eder. Bu karmaşıklaştırma işleci kullandığınızda bellek özel durumları oluşabilir, çünkü bu `CStringT` nesneye eklenen karakterler için yeni depolama alanı ayrılabileceğini unutmayın.

Hakkında bilgi `CThisSimpleString`için, CStringT Açıklamalar bölümüne [bakın:CStringT](#cstringt).

> [!NOTE]
> Gömülü null karakterleri `CStringT` içeren örnekler oluşturmak mümkün olsa da, buna karşı öneririz. Katışmış null `CStringT` karakterleri içeren nesnelerüzerinde arama yöntemleri ve işleçleri istenmeyen sonuçlar üretebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_eq_eq"></a>CStringT::işleç ==

İki dize mantıksal olarak eşit olup olmadığını belirler.

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
Karşılaştırma için BIR ANSI veya Unicode karakteri.

*ch2*<br/>
Karşılaştırma için BIR ANSI veya Unicode karakteri.

*str1*<br/>
Karşılaştırma `CStringT` için.

*str2*<br/>
Karşılaştırma `CStringT` için.

*psz1*<br/>
Karşılaştırma için null-sonlandırılan dize için bir işaretçi.

*psz2*<br/>
Karşılaştırma için null-sonlandırılan dize için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir dize veya karakterin sağ taraftaki bir dize veya karaktere eşit olup olmadığını sınar ve buna göre TRUE veya FALSE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_neq"></a>CStringT::işleç !=

İki dize mantıksal olarak eşit olup olmadığını belirler.

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

*ch2*<br/>
Bir dize ile birleştirmek için bir ANSI veya Unicode karakter.

*str1*<br/>
Karşılaştırma `CStringT` için.

*str2*<br/>
Karşılaştırma `CStringT` için.

*psz1*<br/>
Karşılaştırma için null-sonlandırılan dize için bir işaretçi.

*psz2*<br/>
Karşılaştırma için null-sonlandırılan dize için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir dize veya karakter sağ taraftaki bir dize veya karaktere eşit değilse testler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt"></a>CStringT::işleç&lt;

Işlecinin sol tarafındaki dize sağ taraftaki dizeden daha az olup olmadığını belirler.

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırma `CStringT` için.

*str2*<br/>
Karşılaştırma `CStringT` için.

*psz1*<br/>
Karşılaştırma için null-sonlandırılan dize için bir işaretçi.

*psz2*<br/>
Karşılaştırma için null-sonlandırılan dize için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Dizeleri arasında bir lexicographical karşılaştırma, karakter e kadar karakter:

- Bu iki karşılık gelen karakter eşit siz bulur ve bunların karşılaştırma sonucu dizeleri arasında karşılaştırma sonucu olarak alınır.

- Hiçbir eşitsizlik bulur, ancak bir dize diğerinden daha fazla karaktere sahiptir ve kısa dize daha uzun dize daha az olarak kabul edilir.

- Hiçbir eşitsizlik bulmaz ve dizelerin aynı sayıda karaktere sahip olduğunu ve böylece dizelerin eşit olduğunu bulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

## <a name="cstringtoperator-gt"></a><a name="operator_gt"></a>CStringT::işleç&gt;

Işlecinin sol tarafındaki dize sağ taraftaki dizeden daha büyük olup olmadığını belirler.

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırma `CStringT` için.

*str2*<br/>
Karşılaştırma `CStringT` için.

*psz1*<br/>
Karşılaştırma için null-sonlandırılan dize için bir işaretçi.

*psz2*<br/>
Karşılaştırma için null-sonlandırılan dize için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Dizeleri arasında bir lexicographical karşılaştırma, karakter e kadar karakter:

- Bu iki karşılık gelen karakter eşit siz bulur ve bunların karşılaştırma sonucu dizeleri arasında karşılaştırma sonucu olarak alınır.

- Hiçbir eşitsizlik bulur, ancak bir dize diğerinden daha fazla karaktere sahiptir ve kısa dize daha uzun dize daha az olarak kabul edilir.

- Hiçbir eşitsizlik bulmaz ve dizelerin aynı sayıda karaktere sahip olduğunu bulur, böylece dizeleri eşittir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt_eq"></a>CStringT::işleç&lt;=

İşleticinin sol tarafındaki dize, sağ taraftaki dizeden daha az mı yoksa eşit mi olduğunu belirler.

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırma `CStringT` için.

*str2*<br/>
Karşılaştırma `CStringT` için.

*psz1*<br/>
Karşılaştırma için null-sonlandırılan dize için bir işaretçi.

*psz2*<br/>
Karşılaştırma için null-sonlandırılan dize için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Dizeleri arasında bir lexicographical karşılaştırma, karakter e kadar karakter:

- Bu iki karşılık gelen karakter eşit siz bulur ve bunların karşılaştırma sonucu dizeleri arasında karşılaştırma sonucu olarak alınır.

- Hiçbir eşitsizlik bulur, ancak bir dize diğerinden daha fazla karaktere sahiptir ve kısa dize daha uzun dize daha az olarak kabul edilir.

- Hiçbir eşitsizlik bulmaz ve dizelerin aynı sayıda karaktere sahip olduğunu bulur, böylece dizeleri eşittir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

## <a name="cstringtoperator-gt"></a><a name="operator_gt_eq"></a>CStringT::işleç&gt;=

İşleticinin sol tarafındaki dize, sağ taraftaki dizeden büyük mü yoksa eşit mi olduğunu belirler.

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırma `CStringT` için.

*str2*<br/>
Karşılaştırma `CStringT` için.

*psz1*<br/>
Karşılaştırma için bir dize için bir işaretçi.

*psz2*<br/>
Karşılaştırma için bir dize için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Dizeleri arasında bir lexicographical karşılaştırma, karakter e kadar karakter:

- Bu iki karşılık gelen karakter eşit siz bulur ve bunların karşılaştırma sonucu dizeleri arasında karşılaştırma sonucu olarak alınır.

- Hiçbir eşitsizlik bulur, ancak bir dize diğerinden daha fazla karaktere sahiptir ve kısa dize daha uzun dize daha az olarak kabul edilir.

- Hiçbir eşitsizlik bulmaz ve dizelerin aynı sayıda karaktere sahip olduğunu bulur, böylece dizeleri eşittir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

## <a name="cstringtremove"></a><a name="remove"></a>CStringT::Kaldır

Belirtilen karakterin tüm örneklerini dizeden kaldırır.

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>Parametreler

*chRemove*<br/>
Bir dizeden kaldırılacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Dizeden kaldırılan karakter sayısı. Dize değiştirilmezse sıfır.

### <a name="remarks"></a>Açıklamalar

Karakter için karşılaştırmalar büyük/küçük harf duyarlıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

## <a name="cstringtreplace"></a><a name="replace"></a>CStringT::Değiştir

İki sürümü `Replace`vardır. İlk sürüm, başka bir alt dize kullanarak bir alt dizenin bir veya daha fazla kopyasının yerini alır. Her iki alt dize de null-sonlandırıldı. İkinci sürüm, başka bir karakter kullanarak bir karakterin bir veya daha fazla kopyasının yerini alır. Her iki sürüm de ' `CStringT`de depolanan karakter verileri üzerinde çalışır.

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>Parametreler

*pszOld*<br/>
*PszNew*ile değiştirilecek null-sonlandırılan dize için bir işaretçi .

*pszYeni*<br/>
*pszOld*yerine null-sonlandırılan dize için bir işaretçi .

*chOld*<br/>
ChNew ile değiştirilecek *chNew*karakter.

*chYeni*<br/>
*ChOld*yerine karakter .

### <a name="return-value"></a>Dönüş Değeri

Dize değiştirilmezse, karakterin veya alt dizenin değiştirilen örneklerinin sayısını veya sıfırı döndürür.

### <a name="remarks"></a>Açıklamalar

`Replace`*pszNew* ve *pszOld* aynı uzunlukta olması gerekmez, çünkü dize uzunluğunu değiştirebilirsiniz ve eski alt dize birkaç kopya yeni bir değiştirilebilir. İşlev büyük/küçük harf duyarlı bir eşleşme gerçekleştirir.

Örneklere `CStringT` örnek `CString`olarak `CStringA`, `CStringW`, ve .

Bunun `CStringA` `Replace` için, ANSI veya multibayt (MBCS) karakterleri ile çalışır. Için `CStringW` `Replace` , geniş karakterler ile çalışır.

Bunun `CString`için, aşağıdaki tablodaki sabitlerin tanımlanıp tanımlanmadığına bağlı olarak, karakter veri türü derleme zamanında seçilir.

|Tanımlı Sabit|Karakter Veri Türü|
|----------------------|-------------------------|
|_unıcode|Geniş karakterler|
|_mbcs|Çok bayt karakterleri|
|Hiçbiri|Tek bayt karakterler|
|Her ikisi de|Tanımsız|

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

## <a name="cstringtreversefind"></a><a name="reversefind"></a>CStringT::ReverseFind

Bu `CStringT` nesneyi bir karakterin son eşleşmesi için arar.

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>Parametreler

*Caner*<br/>
Aranacak karakter.

### <a name="return-value"></a>Dönüş Değeri

İstenen karakterle eşleşen bu `CStringT` nesnedeki son karakterin sıfır tabanlı dizini veya karakter bulunamazsa -1.

### <a name="remarks"></a>Açıklamalar

İşlev çalışma zamanı işlevine `strrchr`benzer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

## <a name="cstringtright"></a><a name="right"></a>CStringT::Sağ

Bu `CStringT` nesneden son (yani en sağda) *nCount* karakterlerini ayıklar ve ayıklanan alt dizenin bir kopyasını döndürür.

```
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>Parametreler

*nSayısı*<br/>
Bu `CStringT` nesneden ayıklamak için karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen `CStringT` karakter aralığının bir kopyasını içeren bir nesne. Döndürülen `CStringT` nesnenin boş olabileceğini unutmayın.

### <a name="remarks"></a>Açıklamalar

*nCount* dize uzunluğunu aşarsa, tüm dize ayıklanır. `Right`Temel `Right` işlevine benzer (Temel'deki dizinlerin sıfır tabanlı olması hariç).

Çok bayt karakter kümeleri (MBCS) için *nCount* her 8 bitkarakteranlamına gelir; diğer bir deyişle, bir çok bayt karakterde bir kurşun ve iz bayt iki karakter olarak sayılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

## <a name="cstringtsetsysstring"></a><a name="setsysstring"></a>CStringT::SetSysString

*Pbstr* tarafından işaret edilen BSTR'yi yerle bir `CStringT` eder ve NULL karakteri de dahil olmak üzere nesnenin içeriğini ona kopyalar.

```
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>Parametreler

*pbstr*<br/>
Karakter dizesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni dize.

### <a name="remarks"></a>Açıklamalar

Nesnenin içeriğine `CStringT` bağlı olarak, *pbstr* tarafından başvurulan BSTR değeri değişebilir. İşlev, yetersiz `CMemoryException` bellek varsa atar.

Bu işlev normalde Otomasyon için başvuru tarafından geçirilen dizeleri değerini değiştirmek için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

## <a name="cstringtspanexcluding"></a><a name="spanexcluding"></a>CStringT::SpanExcluding

*PszCharSet*tarafından tanımlanan karakter kümesinde olmayan ilk karakterden başlayarak dizeden karakterleri ayıklar.

```
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Parametreler

*pszCharSet*<br/>
Bir karakter kümesi olarak yorumlanan bir dize.

### <a name="return-value"></a>Dönüş Değeri

*pszCharSet*olmayan dize karakterleri içeren bir alt dize , dize ilk karakter ile başlayan ve *pszCharSet* de dize bulunan ilk karakter ile biten (yani, dize ilk karakter ile başlayan ve kadar ama *pszCharSet*bulunan dize ilk karakter hariç ). *pszCharSet'te* karakter yoksa dizede bulunursa tüm dizeyi döndürür.

### <a name="remarks"></a>Açıklamalar

`SpanExcluding`*pszCharSet'ten* bir karakterin ilk oluşumundan önceki tüm karakterleri ayıklar ve döndürür (diğer bir deyişle, *pszCharSet'teki* karakter ve dizedeki onu izleyen tüm karakterler döndürülmez). dizede *pszCharSet'ten* hiçbir karakter `SpanExcluding` bulunmazsa, tüm dize yi döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

## <a name="cstringtspanincluding"></a><a name="spanincluding"></a>CStringT::SpanIncluding

*PszCharSet*tarafından tanımlanan karakter kümesinde ilk karakterile başlayan dizeden karakterleri ayıklar.

```
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Parametreler

*pszCharSet*<br/>
Bir karakter kümesi olarak yorumlanan bir dize.

### <a name="return-value"></a>Dönüş Değeri

*pszCharSet*içinde olan dize karakterleri içeren bir alt dize , dize ilk karakter ile başlayan ve *pszCharSet*olmayan dize bir karakter bulunduğunda biten . `SpanIncluding`Dizedeki ilk karakter belirtilen kümede değilse boş bir alt dize döndürür.

### <a name="remarks"></a>Açıklamalar

Dize ilk karakteri karakter kümesinde değilse, `SpanIncluding` boş bir dize döndürür. Aksi takdirde, kümede bulunan ardışık karakter sırasını döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

## <a name="cstringttokenize"></a><a name="tokenize"></a>CStringT::Tokenize

Hedef dizedeki sonraki belirteci bulur

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>Parametreler

*pszTokens*<br/>
Belirteç sınırlayıcılar içeren bir dize. Bu sınırlayıcıların sırası önemli değildir.

*iBaşlat*<br/>
Aramaya başlamak için sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Geçerli `CStringT` belirteç değerini içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

İşlev, `Tokenize` hedef dizedeki bir sonraki belirteci bulur. *pszTokens* karakter kümesi bulunacak belirteç olası sınırlayıcıları belirtir. İşlev için `Tokenize` her çağrı *da iStart*başlar, önde gelen `CStringT` sınırlayıcıları atlar ve bir sonraki sınırlayıcı karaktere kadar karakter dizesi olan geçerli belirteci içeren bir nesne döndürür. *iStart* değeri bitiş delimiter karakterini izleyen konum olarak güncelleştirilir veya dize sonuna ulaşıldıysa -1. Daha fazla belirteçleri sonraki belirteç dize nerede okunacak izlemek için `Tokenize` *iStart* kullanarak, bir dizi çağrı ile hedef dize geri kalanı dışarı kırılabilir. Daha fazla belirteç olmadığında işlev boş bir dize döndürür ve *iStart* -1 olarak ayarlanır.

CRT belirteçleri [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)gibi işlevleri, hedef dize `Tokenize` değiştirmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>Açıklamalar

Bu örnekteki çıktı aşağıdaki gibidir:

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

## <a name="cstringttrim"></a><a name="trim"></a>CStringT::Kırpma

Dizedeki önde gelen ve karakterleri izler.

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>Parametreler

*chTarget*<br/>
Kesilecek hedef karakter.

*pszTargets*<br/>
Kesilecek hedef karakterleri içeren bir dize işaretçisi. *pszTarget'deki* karakterlerin tüm önde gelen ve sondaki oluşumları `CStringT` nesneden kesilir.

### <a name="return-value"></a>Dönüş Değeri

Kesilmiş dizeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin tüm satır baş ve sondaki oluşumlarını kaldırır:

- *chTarget*tarafından belirtilen karakter.

- *pszTargets*tarafından belirtilen dize bulunan tüm karakterler .

- Boşluk.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>Açıklamalar

Bu örnekteki çıktı aşağıdaki gibidir:

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

## <a name="cstringttrimleft"></a><a name="trimleft"></a>CStringT::TrimLeft

Dizedeki önde gelen karakterleri kırpar.

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>Parametreler

*chTarget*<br/>
Kesilecek hedef karakter.

*pszTargets*<br/>
Kesilecek hedef karakterleri içeren bir dize işaretçisi. *pszTarget'deki* karakterlerin tüm önde gelen oluşumları `CStringT` nesneden kesilir.

### <a name="return-value"></a>Dönüş Değeri

Elde edilen kesilmiş dize.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin tüm satır baş ve sondaki oluşumlarını kaldırır:

- *chTarget*tarafından belirtilen karakter.

- *pszTargets*tarafından belirtilen dize bulunan tüm karakterler .

- Boşluk.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

## <a name="cstringttrimright"></a><a name="trimright"></a>CStringT::Trimright

Dizedeki karakterleri kırpar.

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>Parametreler

*chTarget*<br/>
Kesilecek hedef karakter.

*pszTargets*<br/>
Kesilecek hedef karakterleri içeren bir dize işaretçisi. *pszTarget'deki* karakterlerin tüm sondaki oluşumları `CStringT` nesneden kesilir.

### <a name="return-value"></a>Dönüş Değeri

Kesilmiş `CStringT` dize içeren nesneyi döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdakilerden birinin sondaki oluşumlarını kaldırır:

- *chTarget*tarafından belirtilen karakter.

- *pszTargets*tarafından belirtilen dize bulunan tüm karakterler .

- Boşluk.

Sürüm `CStringT& TrimRight(XCHAR chTarget)` bir karakter parametresini kabul eder ve bu karakterin tüm `CStringT` kopyalarını dize verilerinin sonundan kaldırır. Bu dize sonundan başlar ve ön doğru çalışır. Farklı bir karakter bulduğunda veya `CSTringT` karakter verileri tükendiğinde durur.

Sürüm, `CStringT& TrimRight(PCXSTR pszTargets)` aranacak tüm farklı karakterleri içeren geçersiz sonlandırılmış bir dize kabul eder. Nesnedeki `CStringT` karakterlerin tüm kopyalarını kaldırır. Bu dize sonunda başlar ve ön doğru çalışır. Hedef dizede olmayan bir karakter bulduğunda veya karakter `CStringT` verileri tükendiğinde durur. Tüm hedef dizesini sonundaki bir alt dizeyle `CStringT`eşleştirmeye çalışmaz.

Sürüm `CStringT& TrimRight()` hiçbir parametre gerektirmez. Dize sonundaki `CStringT` herhangi bir beyaz boşluk karakterini kırpar. Beyaz alan karakterleri satır sonları, boşluklar veya sekmeler olabilir.

-

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[CSimpleStringT Sınıfı](../../atl-mfc-shared/reference/csimplestringt-class.md)
