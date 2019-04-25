---
title: CComBSTR sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComBSTR
- ATLBASE/ATL::CComBSTR
- ATLBASE/ATL::CComBSTR::CComBSTR
- ATLBASE/ATL::CComBSTR::Append
- ATLBASE/ATL::CComBSTR::AppendBSTR
- ATLBASE/ATL::CComBSTR::AppendBytes
- ATLBASE/ATL::CComBSTR::ArrayToBSTR
- ATLBASE/ATL::CComBSTR::AssignBSTR
- ATLBASE/ATL::CComBSTR::Attach
- ATLBASE/ATL::CComBSTR::BSTRToArray
- ATLBASE/ATL::CComBSTR::ByteLength
- ATLBASE/ATL::CComBSTR::Copy
- ATLBASE/ATL::CComBSTR::CopyTo
- ATLBASE/ATL::CComBSTR::Detach
- ATLBASE/ATL::CComBSTR::Empty
- ATLBASE/ATL::CComBSTR::Length
- ATLBASE/ATL::CComBSTR::LoadString
- ATLBASE/ATL::CComBSTR::ReadFromStream
- ATLBASE/ATL::CComBSTR::ToLower
- ATLBASE/ATL::CComBSTR::ToUpper
- ATLBASE/ATL::CComBSTR::WriteToStream
- ATLBASE/ATL::CComBSTR::m_str
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
ms.openlocfilehash: 48447b9e6a211927d8e729dd761d2e14ecd89615
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246569"
---
# <a name="ccombstr-class"></a>CComBSTR sınıfı

Bu sınıf için bir sarmalayıcı olan [BSTR](/previous-versions/windows/desktop/automat/bstr)s.

## <a name="syntax"></a>Sözdizimi

```
class CComBSTR
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComBSTR::CComBSTR](#ccombstr)|Oluşturucu.|
|[CComBSTR::~CComBSTR](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComBSTR::Append](#append)|İçin bir dize ekler `m_str`.|
|[CComBSTR::AppendBSTR](#appendbstr)|BSTR için ekler `m_str`.|
|[CComBSTR::AppendBytes](#appendbytes)|Belirtilen sayıda bayt ekler `m_str`.|
|[CComBSTR::ArrayToBSTR](#arraytobstr)|Her öğesine SAFEARRAY'i ilk karakteri bir BSTR oluşturur ve ona ekler `CComBSTR` nesne.|
|[CComBSTR::AssignBSTR](#assignbstr)|BSTR için atar `m_str`.|
|[CComBSTR::Attach](#attach)|BSTR için ekler `CComBSTR` nesne.|
|[CComBSTR::BSTRToArray](#bstrtoarray)|Dizinin her öğesi, bir karakter olduğu bir sıfır tabanlı bir tek boyutlu SAFEARRAY'i oluşturur `CComBSTR` nesne.|
|[CComBSTR::ByteLength](#bytelength)|Uzunluğunu döndürür `m_str` bayt.|
|[CComBSTR::Copy](#copy)|Bir kopyasını döndürür `m_str`.|
|[CComBSTR::CopyTo](#copyto)|Bir kopyasını döndürür `m_str` aracılığıyla bir **[out]** parametresi|
|[CComBSTR::Detach](#detach)|Ayırır `m_str` gelen `CComBSTR` nesne.|
|[CComBSTR::Empty](#empty)|Serbest bırakma `m_str`.|
|[CComBSTR::Length](#length)|Uzunluğunu döndürür `m_str`.|
|[CComBSTR::LoadString](#loadstring)|Bir dize kaynağı yükler.|
|[CComBSTR::ReadFromStream](#readfromstream)|BSTR nesnesi bir akışından yükler.|
|[CComBSTR::ToLower](#tolower)|Dizeyi küçük harfe dönüştürür.|
|[CComBSTR::ToUpper](#toupper)|Dizeyi büyük harfe dönüştürür.|
|[CComBSTR::WriteToStream](#writetostream)|Kaydeder `m_str` bir akışa.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[BSTR CComBSTR::operator](#operator_bstr)|Yayınları bir `CComBSTR` BSTR için nesne.|
|[CComBSTR::operator!](#operator_not)|TRUE veya FALSE bağlı olarak döndürür `m_str`null.|
|[CComBSTR::operator !=](#operator_neq)|Karşılaştıran bir `CComBSTR` içeren bir dize.|
|[CComBSTR::operator &](#operator_amp)|Adresini döndürür `m_str`.|
|[CComBSTR::operator +=](#operator_add_eq)|Ekler bir `CComBSTR` nesneye.|
|[CComBSTR::operator <](#operator_lt)|Karşılaştıran bir `CComBSTR` içeren bir dize.|
|[CComBSTR::operator =](#operator_eq)|Bir değer atar `m_str`.|
|[CComBSTR::operator ==](#operator_eq_eq)|Karşılaştıran bir `CComBSTR` içeren bir dize.|
|[CComBSTR::operator >](#operator_gt)|Karşılaştıran bir `CComBSTR` içeren bir dize.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComBSTR::m_str](#m_str)|İle ilişkili BSTR içeren `CComBSTR` nesne.|

## <a name="remarks"></a>Açıklamalar

`CComBSTR` Dizeleri ön eki uzunluğu olan BSTR'lerin için bir sarmalayıcı sınıftır. Uzunluğu bir tamsayı veri dizesinde önceki bellek konumunda saklanır.

A [BSTR](/previous-versions/windows/desktop/automat/bstr) boş sonra son karakter sayılan ancak aynı zamanda dizede katıştırılmış null karakterleri içerebilir sonlandırılmıştır. Dize uzunluğu ilk null karakteri değil karakter sayısı tarafından belirlenir.

> [!NOTE]
>  `CComBSTR` Sınıfı bir dizi ANSI veya Unicode dize bağımsız değişken olarak ele üyeleri (Oluşturucular, atama işleçleri ve Karşılaştırma işleçleri) sağlar. Geçici Unicode dizelerini genellikle dahili olarak oluşturulduğundan bu işlevler ANSI sürümleri, Unicode emsallerinden çok daha az verimlidir. Verimliliği için mümkün olduğunda Unicode sürümlerini kullanın.

> [!NOTE]
>  Visual Studio. NET'te uygulanan Gelişmiş arama davranış nedeniyle, aşağıdaki gibi kod `bstr = L"String2" + bstr;`, hangi önceki sürümlerde, derlenmiş yerine uygulanmasını olarak `bstr = CStringW(L"String2") + bstr`.

Kullanırken uyarıların bir listesi için `CComBSTR`, bkz: [CComBSTR ile programlama](../../atl/programming-with-ccombstr-atl.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="append"></a>  CComBSTR::Append

Ya da ekler *lpsz* veya BSTR üyesi *bstrSrc* için [m_str](#m_str).

```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
[in] A `CComBSTR` eklenecek nesne.

*ch*<br/>
[in] Eklenecek bir karakter.

*lpsz*<br/>
[in] Eklenecek sıfır ile sonlandırılmış dize. Bir Unicode dize LPCOLESTR aşırı yükleme ya da bir ANSI dizesine LPCSTR sürümü aracılığıyla aracılığıyla geçirebilirsiniz.

*nLen*<br/>
[in] Karakter sayısı *lpsz* eklenecek.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı ya da standart HRESULT hatası herhangi bir değer.

### <a name="remarks"></a>Açıklamalar

Bir ANSI dizesine eklenen önce Unicode'a dönüştürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

##  <a name="appendbstr"></a>  CComBSTR::AppendBSTR

Ekler için belirtilen BSTR [m_str](#m_str).

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
[in] Eklenecek BSTR.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı ya da standart HRESULT hatası herhangi bir değer.

### <a name="remarks"></a>Açıklamalar

Sıradan bir geniş karakter dizesi için bu yöntem geçirmeyin. Derleyici, hata catch ve çalışma zamanı hataları meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

##  <a name="appendbytes"></a>  CComBSTR::AppendBytes

Belirtilen sayıda baytı için ekler [m_str](#m_str) dönüştürme olmadan.

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
[in] Eklenecek Bayt dizisine bir işaretçi.

*p*<br/>
[in] Eklenecek bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı ya da standart HRESULT hatası herhangi bir değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

##  <a name="arraytobstr"></a>  CComBSTR::ArrayToBSTR

Tutulan varolan bir dizeyi boşaltır `CComBSTR` nesne, ardından her öğesine SAFEARRAY'i ilk karakteri bir BSTR oluşturur ve ona ekler `CComBSTR` nesne.

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
[in] Dizeyi oluşturmak için kullanılan öğeleri içeren SAFEARRAY'i.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı ya da standart HRESULT hatası herhangi bir değer.

##  <a name="assignbstr"></a>  CComBSTR::AssignBSTR

BSTR için atar [m_str](#m_str).

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
[in] Geçerli atamak için bir BSTR `CComBSTR` nesne.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı ya da standart HRESULT hatası herhangi bir değer.

##  <a name="attach"></a>  CComBSTR::Attach

BSTR için ekler `CComBSTR` ayarlayarak nesne [m_str](#m_str) üyesine *src*.

```
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[in] Nesnesine eklenecek BSTR.

### <a name="remarks"></a>Açıklamalar

Sıradan bir geniş karakter dizesi için bu yöntem geçirmeyin. Derleyici, hata catch ve çalışma zamanı hataları meydana gelir.

> [!NOTE]
>  Bu yöntem, onay `m_str` NULL değil.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="bstrtoarray"></a>  CComBSTR::BSTRToArray

Dizinin her öğesi, bir karakter olduğu bir sıfır tabanlı bir tek boyutlu SAFEARRAY'i oluşturur `CComBSTR` nesne.

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>Parametreler

*ppArray*<br/>
[out] İşlevinin sonuçlarını tutmak için kullanılan SAFEARRAY'i işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı ya da standart HRESULT hatası herhangi bir değer.

##  <a name="bytelength"></a>  CComBSTR::ByteLength

Bayt sayısını döndürür `m_str`, sondaki null karakter hariç.

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Uzunluğunu [m_str](#m_str) üye bayt.

### <a name="remarks"></a>Açıklamalar

0 döndürür `m_str` null.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

##  <a name="ccombstr"></a>  CComBSTR::CComBSTR

Oluşturucu. Varsayılan Oluşturucu kümeleri [m_str](#m_str) üyesi null.

```
CComBSTR() throw();
CComBSTR(const CComBSTR& src);
CComBSTR(REFGUID  guid);
CComBSTR(int nSize);
CComBSTR(int nSize, LPCOLESTR sz);
CComBSTR(int nSize, LPCSTR sz);
CComBSTR(LPCOLESTR pSrc);
CComBSTR(LPCSTR pSrc);
CComBSTR(CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
[in] Kopyalanacak karakter sayısını *sz* veya ilk boyutu için karakter cinsinden `CComBSTR`.

*sz*<br/>
[in] Kopyalamak için bir dize. Unicode sürümü bir LPCOLESTR belirtir. ANSI sürümü bir LPCSTR belirtir.

*pSrc*<br/>
[in] Kopyalamak için bir dize. Unicode sürümü bir LPCOLESTR belirtir. ANSI sürümü bir LPCSTR belirtir.

*src*<br/>
[in] A `CComBSTR` nesne.

*GUID*<br/>
[in] Bir başvuru bir `GUID` yapısı.

### <a name="remarks"></a>Açıklamalar

Kopya Oluşturucu kümeleri `m_str` BSTR üyesi bir kopyasına *src*. `REFGUID` Oluşturucusu kullanarak bir dize GUID dönüştürür `StringFromGUID2` ve sonucu depolar.

Bir oluşturucu kümesi `m_str` belirtilen dizenin bir kopyası için. Bir değer geçirmek, *nSize*, yalnızca *nSize* karakter kopyalanır, bir sonlandırıcı null karakter tarafından izlenen.

`CComBSTR` taşıma semantiği destekler. Taşıma Oluşturucusu kullanabilirsiniz (bir rvalue başvurusu alan oluşturucu (`&&`) geçirdiğiniz nesne kopyalama iş yükü olmadan bir bağımsız değişken olarak eski nesnesi olarak aynı temel verilerini kullanan yeni bir nesne oluşturmak için.

Yok edici işaret ettiği bir dizeyi boşaltır `m_str`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

##  <a name="dtor"></a>  CComBSTR::~CComBSTR

Yıkıcı.

```
~CComBSTR();
```

### <a name="remarks"></a>Açıklamalar

Yok edici işaret ettiği bir dizeyi boşaltır `m_str`.

##  <a name="copy"></a>  CComBSTR::Copy

Ayırır ve bir kopyasını döndürür `m_str`.

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kopyasını [m_str](#m_str) üyesi. Varsa `m_str` null, NULL döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

##  <a name="copyto"></a>  CComBSTR::CopyTo

Ayırır ve bir kopyasını döndürür [m_str](#m_str) parametresi aracılığıyla.

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>Parametreler

*pbstr*<br/>
[out] Burada bu yöntem tarafından ayrılan dize döndürecek şekilde BSTR adresi.

*pvarDest*<br/>
[out] Bir değişken, bu yöntem tarafından ayrılan dize döndürecek şekilde adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT başarısı veya başarısızlığı kopyanın belirten değer.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağrıldıktan sonra DEĞİŞKENİ tarafından işaret edilen *pvarDest* VT_BSTR türünde olacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

##  <a name="detach"></a>  CComBSTR::Detach

Ayırır [m_str](#m_str) gelen `CComBSTR` nesne ve ayarlar `m_str` null.

```
BSTR Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

BSTR ilişkili `CComBSTR` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

##  <a name="empty"></a>  CComBSTR::Empty

Serbest bırakma [m_str](#m_str) üyesi.

```
void Empty() throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

##  <a name="length"></a>  CComBSTR::Length

Karakter sayısını döndürür `m_str`, sondaki null karakter hariç.

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Uzunluğunu [m_str](#m_str) üyesi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

##  <a name="loadstring"></a>  CComBSTR::LoadString

Tarafından belirtilen bir dize kaynağı yükler *nID* ve bu nesnesi içine kaydeder.

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>Parametreler

Bkz: [LoadString](/windows/desktop/api/winuser/nf-winuser-loadstringa) Windows SDK içinde.

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla yüklenip yüklenmediğini TRUE döndürür; Aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

İlk işlev sizin tarafınızdan belirlenen modülündeki kaynak yükler *hInst* parametresi. Kaynak ikinci işlevi ile ilişkili kaynak modülü yükler [CComModule](../../atl/reference/ccommodule-class.md)-türetilmiş bu projede kullanılan nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

##  <a name="m_str"></a>  CComBSTR::m_str

İle ilişkili BSTR içeren `CComBSTR` nesne.

```
BSTR m_str;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

##  <a name="operator_bstr"></a>  BSTR CComBSTR::operator

Yayınları bir `CComBSTR` BSTR için nesne.

```
operator BSTR() const throw();
```

### <a name="remarks"></a>Açıklamalar

Geçirmenize olanak `CComBSTR` nesnelere sahip işlevlerin **[in] BSTR** parametreleri.

### <a name="example"></a>Örnek

Örneğin bakın [CComBSTR::m_str](#m_str).

##  <a name="operator_not"></a>  CComBSTR::operator!

BSTR dizesi NULL olup olmadığını denetler.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür [m_str](#m_str) üyesi NULL; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işleç sadece boş bir dize için bir NULL değer denetler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="operator_neq"></a>  CComBSTR::operator! =

Mantıksal tersini döndürür [işleç ==](#operator_eq_eq).

```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
[in] A `CComBSTR` nesne.

*pszSrc*<br/>
[in] Sıfır ile sonlandırılmış dize.

*nNull*<br/>
[in] NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğesi eşit değilse TRUE döndürür `CComBSTR` nesne; Aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CComBSTR`s kullanıcının varsayılan yerel ayar bağlamında metin içeriğini eklemek karşılaştırılır. Son karşılaştırma işleci yalnızca NULL kapsanan dizeyi karşılaştırır.

##  <a name="operator_amp"></a>  CComBSTR::operator &amp;

Depolanan BSTR adresini döndürür [m_str](#m_str) üyesi.

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>Açıklamalar

`CComBstr operator &` özel bir onaylama işlemi bellek sızıntılarını belirlemenize yardımcı olması için onunla ilişkilendirilir. Programın ne zaman iddia `m_str` üye başlatılır. Burada Programcı kullanan durumları belirlemek için bu onay oluşturulduğu `& operator` için yeni bir değer atamak için `m_str` ilk ayırma boşaltma olmadan üye `m_str`. Varsa `m_str` NULL eşittir, programın bu m_str değildi ayrılan henüz varsayar. Bu durumda, program iddia etmeyecektir.

Bu onay, varsayılan olarak etkin değildir. Bu onay etkinleştirmek için ATL_CCOMBSTR_ADDRESS_OF_ASSERT tanımlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

##  <a name="operator_add_eq"></a>  CComBSTR::operator +=

İçin bir dize ekler `CComBSTR` nesne.

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
[in] A `CComBSTR` eklenecek nesne.

*pszSrc*<br/>
[in] Eklenecek sıfır ile sonlandırılmış dize.

### <a name="remarks"></a>Açıklamalar

`CComBSTR`s kullanıcının varsayılan yerel ayar bağlamında metin içeriğini eklemek karşılaştırılır. LPCOLESTR karşılaştırma yapılır kullanarak `memcmp` her bir dizenin ham verileri. Geçici bir Unicode kopyalayın sonra LPCSTR karşılaştırma aynı şekilde gerçekleştirilir *pszSrc* oluşturuldu. Son karşılaştırma işleci yalnızca NULL kapsanan dizeyi karşılaştırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

##  <a name="operator_lt"></a>  CComBSTR::operator &lt;

Karşılaştıran bir `CComBSTR` içeren bir dize.

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe ise TRUE döndürür küçüktür `CComBSTR` nesne; Aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırma, kullanıcının varsayılan yerel ayar kullanılarak gerçekleştirilir.

##  <a name="operator_eq"></a>  CComBSTR::operator =

Kümeleri [m_str](#m_str) üyeye bir kopyası *pSrc* veya BSTR üyesi bir kopyasını *src*. Taşıma atama işlecini taşır `src` kopyalayarak olmadan.

```
CComBSTR& operator= (const CComBSTR& src);
CComBSTR& operator= (LPCOLESTR pSrc);
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>Açıklamalar

*PSrc* parametresi bir LPCOLESTR Unicode sürümleri ya da ANSI sürümleri LPCSTR belirtir.

### <a name="example"></a>Örnek

Örneğin bakın [CComBSTR::Copy](#copy).

##  <a name="operator_eq_eq"></a>  CComBSTR::operator ==

Karşılaştıran bir `CComBSTR` içeren bir dize. `CComBSTR`s kullanıcının varsayılan yerel ayar bağlamında metin içeriğini eklemek karşılaştırılır.

```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
[in] A `CComBSTR` nesne.

*pszSrc*<br/>
[in] Sıfır ile sonlandırılmış dize.

*nNull*<br/>
[in] NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe eşitse TRUE döndürür `CComBSTR` nesne; Aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Son karşılaştırma işleci yalnızca NULL kapsanan dizeyi karşılaştırır.

##  <a name="operator_gt"></a>  CComBSTR::operator &gt;

Karşılaştıran bir `CComBSTR` içeren bir dize.

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğesi sayısından büyükse TRUE döndürür `CComBSTR` nesne; Aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırma, kullanıcının varsayılan yerel ayar kullanılarak gerçekleştirilir.

##  <a name="readfromstream"></a>  CComBSTR::ReadFromStream

Kümeleri [m_str](#m_str) üye belirtilen akışında bulunan BSTR.

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[in] Bir işaretçi [IStream](/windows/desktop/api/objidl/nn-objidl-istream) akış verilerini içeren bir arabirimdeki.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

`ReadToStream` geçerli konumda bir çağrı tarafından yazılan veri biçimi ile uyumlu olacak şekilde akış içeriğini gerektirir [WriteToStream](#writetostream).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

##  <a name="tolower"></a>  CComBSTR::ToLower

Kapsanan dizeyi küçük harfe dönüştürür.

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bkz: `CharLowerBuff` dönüştürme nasıl gerçekleştirildiğini hakkında daha fazla bilgi.

##  <a name="toupper"></a>  CComBSTR::ToUpper

Kapsanan dizeyi büyük harfe dönüştürür.

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bkz: `CharUpperBuff` dönüştürme nasıl gerçekleştirildiğini hakkında daha fazla bilgi.

##  <a name="writetostream"></a>  CComBSTR::WriteToStream

Kaydeder [m_str](#m_str) bir akışa üyesi.

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[in] Bir işaretçi [IStream](/windows/desktop/api/objidl/nn-objidl-istream) arabirimdeki bir akış.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

BSTR içeriğinden stream kullanarak yeniden oluşturabilirsiniz [ReadFromStream](#readfromstream) işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md)
