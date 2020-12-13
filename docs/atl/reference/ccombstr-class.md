---
description: 'Daha fazla bilgi edinin: CComBSTR sınıfı'
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
ms.openlocfilehash: 1ddb830846747f0e3efe36f02be07ce1a45b353e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152314"
---
# <a name="ccombstr-class"></a>CComBSTR sınıfı

Bu sınıf, [BSTR](/previous-versions/windows/desktop/automat/bstr)'leri için bir sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CComBSTR
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComBSTR:: CComBSTR](#ccombstr)|Oluşturucu.|
|[CComBSTR:: ~ CComBSTR](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComBSTR:: Append](#append)|Bir dize ekler `m_str` .|
|[CComBSTR:: AppendBSTR](#appendbstr)|İçin bir BSTR ekler `m_str` .|
|[CComBSTR:: AppendBytes](#appendbytes)|Belirtilen sayıda baytı sonuna ekler `m_str` .|
|[CComBSTR:: ArrayToBSTR](#arraytobstr)|SafeArray içindeki her bir öğenin ilk karakterinden bir BSTR oluşturur ve `CComBSTR` nesneye iliştirir.|
|[CComBSTR:: Atamabstr](#assignbstr)|İçin bir BSTR atar `m_str` .|
|[CComBSTR:: Attach](#attach)|Nesnesine bir BSTR ekler `CComBSTR` .|
|[CComBSTR:: BSTRToArray](#bstrtoarray)|Dizinin her öğesi nesnesinden bir karakter olduğunda, sıfır tabanlı tek boyutlu bir SAFEARRAY oluşturur `CComBSTR` .|
|[CComBSTR:: ByteLength](#bytelength)|Bayt cinsinden uzunluğunu döndürür `m_str` .|
|[CComBSTR:: Copy](#copy)|Bir kopyasını döndürür `m_str` .|
|[CComBSTR:: CopyTo](#copyto)|`m_str` **[Out]** parametresi aracılığıyla bir kopyasını döndürür|
|[CComBSTR::D etach](#detach)|`m_str` `CComBSTR` Nesneden ayırır.|
|[CComBSTR:: Empty](#empty)|Serbest bırakır `m_str` .|
|[CComBSTR:: length](#length)|Uzunluğunu döndürür `m_str` .|
|[CComBSTR:: LoadString](#loadstring)|Bir dize kaynağı yükler.|
|[CComBSTR:: ReadFromStream](#readfromstream)|Akıştan bir BSTR nesnesi yükler.|
|[CComBSTR:: ToLower](#tolower)|Dizeyi küçük harfe dönüştürür.|
|[CComBSTR:: ToUpper](#toupper)|Dizeyi büyük harfe dönüştürür.|
|[CComBSTR:: WriteToStream](#writetostream)|`m_str`Bir akışa kaydeder.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComBSTR:: operator BSTR](#operator_bstr)|Bir `CComBSTR` NESNEYI BSTR 'ye yayınlar.|
|[CComBSTR:: operator!](#operator_not)|NULL olup olmadığına bağlı olarak TRUE veya FALSE değerini döndürür `m_str` .|
|[CComBSTR:: operator! =](#operator_neq)|Bir `CComBSTR` dizeyle bir ile karşılaştırır.|
|[CComBSTR:: operator &](#operator_amp)|Adresini döndürür `m_str` .|
|[CComBSTR:: operator + =](#operator_add_eq)|Nesnesine bir ekler `CComBSTR` .|
|[CComBSTR:: operator <](#operator_lt)|Bir `CComBSTR` dizeyle bir ile karşılaştırır.|
|[CComBSTR:: operator =](#operator_eq)|Öğesine bir değer atar `m_str` .|
|[CComBSTR:: operator = =](#operator_eq_eq)|Bir `CComBSTR` dizeyle bir ile karşılaştırır.|
|[CComBSTR:: operator >](#operator_gt)|Bir `CComBSTR` dizeyle bir ile karşılaştırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComBSTR:: m_str](#m_str)|Nesneyle ilişkili BSTR 'yi içerir `CComBSTR` .|

## <a name="remarks"></a>Açıklamalar

`CComBSTR`Sınıfı, uzunluk ön eki olan dizeler olan BSTRs için bir sarmalayıcıdır. Uzunluk, dizedeki verilerden önceki bellek konumunda bir tamsayı olarak depolanır.

[BSTR](/previous-versions/windows/desktop/automat/bstr) , son sayılan karakterden sonra null ile sonlandırılır, ancak dize içine gömülü null karakterler de içerebilir. Dize uzunluğu, ilk null karakter değil karakter sayısına göre belirlenir.

> [!NOTE]
> `CComBSTR`Sınıfı, bağımsız değişken olarak ANSI veya Unicode dizeleri alan bir dizi üye (oluşturucular, atama işleçleri ve karşılaştırma işleçleri) sağlar. Geçici Unicode dizeleri genellikle dahili olarak oluşturulduğundan, bu işlevlerin ANSI sürümleri Unicode karşılıklarından daha az verimlidir. Verimlilik için mümkün olan yerlerde Unicode sürümlerini kullanın.

> [!NOTE]
> Visual Studio .NET içinde uygulanan geliştirilmiş arama davranışı nedeniyle, gibi bir kod, `bstr = L"String2" + bstr;` önceki sürümlerde derlenmiş olabilecek gibi, yerine uygulanmalıdır `bstr = CStringW(L"String2") + bstr` .

Kullanırken uyarı listesi için `CComBSTR` bkz. [CComBSTR ile programlama](../../atl/programming-with-ccombstr-atl.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccombstrappend"></a><a name="append"></a> CComBSTR:: Append

[M_str](#m_str)bir *bstrsrc* 'nın *lpsz* veya BSTR üyesini ekler.

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
'ndaki `CComBSTR` Eklenecek nesne.

*denetleyebilirsiniz*<br/>
'ndaki Eklenecek karakter.

*lpsz*<br/>
'ndaki Sona eklenecek sıfır ile sonlandırılmış bir karakter dizesi. Bir Unicode dizesini LPCOLISTR aşırı yüklemesi veya bir ANSI dizesi aracılığıyla LPCSTR sürümü aracılığıyla geçirebilirsiniz.

*nLen*<br/>
'ndaki *Lpsz* 'den eklenecek karakterlerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değeri S_OK.

### <a name="remarks"></a>Açıklamalar

Bir ANSI dizesi eklenmeden önce Unicode olarak dönüştürülecek.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

## <a name="ccombstrappendbstr"></a><a name="appendbstr"></a> CComBSTR:: AppendBSTR

[M_str](#m_str)IÇIN belirtilen BSTR 'yi ekler.

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Eklenecek BSTR.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değeri S_OK.

### <a name="remarks"></a>Açıklamalar

Bu yönteme sıradan bir geniş karakterli dize geçirmeyin. Derleyici hatayı yakalayamaz ve çalıştırma zamanı hataları oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

## <a name="ccombstrappendbytes"></a><a name="appendbytes"></a> CComBSTR:: AppendBytes

Dönüştürme yapmadan [m_str](#m_str) belirtilen bayt sayısını ekler.

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
'ndaki Eklenecek bayt dizisinin bir işaretçisi.

*Lama*<br/>
'ndaki Eklenecek bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değeri S_OK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

## <a name="ccombstrarraytobstr"></a><a name="arraytobstr"></a> CComBSTR:: ArrayToBSTR

Nesnede tutulan mevcut dizeleri serbest bırakır `CComBSTR` , ardından SAFEARRAY içindeki her bir öğenin ilk karakterinden BIR BSTR oluşturur ve `CComBSTR` nesneye iliştirir.

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
'ndaki Dizeyi oluşturmak için kullanılan öğeleri içeren SAFEARRAY.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değeri S_OK.

## <a name="ccombstrassignbstr"></a><a name="assignbstr"></a> CComBSTR:: Atamabstr

[M_str](#m_str)için BSTR atar.

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
'ndaki Geçerli nesneye atanacak bir BSTR `CComBSTR` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değeri S_OK.

## <a name="ccombstrattach"></a><a name="attach"></a> CComBSTR:: Attach

`CComBSTR` [M_str](#m_str) üyesini *src* olarak ayarlayarak nesnesine bir BSTR ekler.

```cpp
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>Parametreler

*src*<br/>
'ndaki Nesneye iliştirilecek BSTR.

### <a name="remarks"></a>Açıklamalar

Bu yönteme sıradan bir geniş karakterli dize geçirmeyin. Derleyici hatayı yakalayamaz ve çalıştırma zamanı hataları oluşur.

> [!NOTE]
> Bu yöntem, `m_str` null değilse onay olacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

## <a name="ccombstrbstrtoarray"></a><a name="bstrtoarray"></a> CComBSTR:: BSTRToArray

Dizinin her öğesi nesnesinden bir karakter olduğunda, sıfır tabanlı tek boyutlu bir SAFEARRAY oluşturur `CComBSTR` .

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>Parametreler

*ppArray*<br/>
dışı İşlevin sonuçlarını tutmak için kullanılan SAFEARRAY işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değeri S_OK.

## <a name="ccombstrbytelength"></a><a name="bytelength"></a> CComBSTR:: ByteLength

' Deki, `m_str` Sonlandırıcı null karakteri hariç bayt sayısını döndürür.

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[M_str](#m_str) üyesinin bayt cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

NULL ise 0 döndürür `m_str` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

## <a name="ccombstrccombstr"></a><a name="ccombstr"></a> CComBSTR:: CComBSTR

Oluşturucu. Varsayılan Oluşturucu, [m_str](#m_str) üyesini null olarak ayarlar.

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
'ndaki *SZ* 'den kopyalanacak karakter sayısı veya için karakter cinsinden başlangıç boyutu `CComBSTR` .

*SZ*<br/>
'ndaki Kopyalanacak dize. Unicode sürümü bir LPCOELSTR belirtir; ANSI sürümü bir LPCSTR belirtir.

*pSrc*<br/>
'ndaki Kopyalanacak dize. Unicode sürümü bir LPCOELSTR belirtir; ANSI sürümü bir LPCSTR belirtir.

*src*<br/>
'ndaki Bir `CComBSTR` nesne.

*guid*<br/>
'ndaki Bir `GUID` yapıya başvuru.

### <a name="remarks"></a>Açıklamalar

Kopya Oluşturucu, `m_str` *src* öğesinin BSTR üyesinin bir kopyasına ayarlanır. `REFGUID`Oluşturucu, kullanarak GUID 'yi bir dizeye dönüştürür `StringFromGUID2` ve sonucu depolar.

Diğer oluşturucular `m_str` belirtilen dizenin bir kopyasına ayarlanır. *NSize* için bir değer geçirirseniz, yalnızca *nSize* karakterleri kopyalanacak ve ardından bir Sonlandırıcı null karakteri gelir.

`CComBSTR` taşıma semantiğini destekler. `&&`Nesne kopyalama ek yükü olmadan, bir bağımsız değişken olarak geçirdiğiniz eski nesneyle aynı temel verileri kullanan yeni bir nesne oluşturmak için, taşıma oluşturucusunu (bir rvalue başvurusu () alan Oluşturucu () kullanabilirsiniz.

Yıkıcı, tarafından işaret edilen dizeyi serbest bırakır `m_str` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

## <a name="ccombstrccombstr"></a><a name="dtor"></a> CComBSTR:: ~ CComBSTR

Yok edicisi.

```
~CComBSTR();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, tarafından işaret edilen dizeyi serbest bırakır `m_str` .

## <a name="ccombstrcopy"></a><a name="copy"></a> CComBSTR:: Copy

Bir kopyasını ayırır ve döndürür `m_str` .

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[M_str](#m_str) üyesinin bir kopyası. `m_str`Null ise, null döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

## <a name="ccombstrcopyto"></a><a name="copyto"></a> CComBSTR:: CopyTo

Parametresi aracılığıyla [m_str](#m_str) kopyasını ayırır ve döndürür.

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>Parametreler

*pbstr*<br/>
dışı Bu yöntem tarafından ayrılan dizenin döndürüleceği bir BSTR 'nin adresi.

*pvarDest*<br/>
dışı Bu yöntem tarafından ayrılan dizenin döndürüleceği bir DEĞIŞKENIN adresi.

### <a name="return-value"></a>Dönüş Değeri

Kopyanın başarısını veya başarısızlığını belirten standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırdıktan sonra, *pvarDest* tarafından Işaret edilen değişken VT_BSTR türünde olacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

## <a name="ccombstrdetach"></a><a name="detach"></a> CComBSTR::D etach

Nesnesinden [m_str](#m_str) AYıRıR `CComBSTR` ve `m_str` null olarak ayarlar.

```
BSTR Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyle ilişkili BSTR `CComBSTR` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

## <a name="ccombstrempty"></a><a name="empty"></a> CComBSTR:: Empty

[M_str](#m_str) üyesini serbest bırakır.

```cpp
void Empty() throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

## <a name="ccombstrlength"></a><a name="length"></a> CComBSTR:: length

' Deki karakter sayısını `m_str` , Sonlandırıcı null karakteri hariç döndürür.

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[M_str](#m_str) üyesinin uzunluğu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

## <a name="ccombstrloadstring"></a><a name="loadstring"></a> CComBSTR:: LoadString

*NID* tarafından belirtilen bir dize kaynağını yükler ve bu nesnede depolar.

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>Parametreler

Windows SDK [LoadString](/windows/win32/api/winuser/nf-winuser-loadstringw) öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla yüklenirse TRUE değerini döndürür; Aksi takdirde, FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

İlk işlev, *hinst* parametresi aracılığıyla sizin tarafınızdan tanımlanan modülden kaynağı yükler. İkinci işlev, bu projede kullanılan [CComModule](../../atl/reference/ccommodule-class.md)ile türetilmiş nesneyle ilişkili kaynak modülünden kaynağı yükler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

## <a name="ccombstrm_str"></a><a name="m_str"></a> CComBSTR:: m_str

Nesneyle ilişkili BSTR 'yi içerir `CComBSTR` .

```
BSTR m_str;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

## <a name="ccombstroperator-bstr"></a><a name="operator_bstr"></a> CComBSTR:: operator BSTR

Bir `CComBSTR` NESNEYI BSTR 'ye yayınlar.

```
operator BSTR() const throw();
```

### <a name="remarks"></a>Açıklamalar

`CComBSTR`Nesneleri **[ın] BSTR** parametrelerine sahip işlevlere geçirmenize olanak sağlar.

### <a name="example"></a>Örnek

[CComBSTR:: m_str](#m_str)örneğine bakın.

## <a name="ccombstroperator-"></a><a name="operator_not"></a> CComBSTR:: operator!

BSTR dizesinin NULL olup olmadığını denetler.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[M_str](#m_str) üyesi null ise true döndürür; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işleç, boş bir dize için değil, yalnızca NULL değer olup olmadığını denetler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

## <a name="ccombstroperator-"></a><a name="operator_neq"></a> CComBSTR:: operator! =

[= = İşlecinin](#operator_eq_eq)mantıksal tersini döndürür.

```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
'ndaki Bir `CComBSTR` nesne.

*pszSrc*<br/>
'ndaki Sıfır ile sonlandırılmış bir dize.

*nNull*<br/>
'ndaki NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe nesnesine eşitse TRUE, `CComBSTR` DEĞILSE false döndürür.

### <a name="remarks"></a>Açıklamalar

`CComBSTR`metin içeriğini eklemek, kullanıcının varsayılan yerel ayarı bağlamında karşılaştırılır. Son karşılaştırma işleci yalnızca kapsanan dizeyi NULL ile karşılaştırır.

## <a name="ccombstroperator-amp"></a><a name="operator_amp"></a> CComBSTR:: işleci &amp;

[M_str](#m_str) ÜYESINDE depolanan BSTR 'nin adresini döndürür.

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>Açıklamalar

`CComBstr operator &` , bellek sızıntılarını belirlemenize yardımcı olmak için kendisiyle ilişkili özel bir onaylama işlemi içerir. Program, üye başlatıldığında onay alacak `m_str` . Bu onaylama, bir programcının `& operator` `m_str` ilk ayırmayı boşaltmadan üyeye yeni bir değer atamak için kullandığı durumları belirlemek için oluşturulmuştur `m_str` . `m_str`EŞITTIR null ise, program m_str henüz ayrılmadığı varsayılır. Bu durumda, program onay olmaz.

Bu onaylama varsayılan olarak etkin değildir. Bu onayı etkinleştirmek için ATL_CCOMBSTR_ADDRESS_OF_ASSERT tanımlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

## <a name="ccombstroperator-"></a><a name="operator_add_eq"></a> CComBSTR:: operator + =

Nesnesine bir dize ekler `CComBSTR` .

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
'ndaki `CComBSTR` Eklenecek nesne.

*pszSrc*<br/>
'ndaki Sona eklenecek sıfır ile sonlandırılmış dize.

### <a name="remarks"></a>Açıklamalar

`CComBSTR`metin içeriğini eklemek, kullanıcının varsayılan yerel ayarı bağlamında karşılaştırılır. LPCOTASTR karşılaştırması, `memcmp` her dizedeki ham verilerde kullanılarak yapılır. LPCSTR karşılaştırması, *pszSrc* 'nin geçici bir Unicode kopyası oluşturulduktan sonra aynı şekilde yürütülür. Son karşılaştırma işleci yalnızca kapsanan dizeyi NULL ile karşılaştırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

## <a name="ccombstroperator-lt"></a><a name="operator_lt"></a> CComBSTR:: işleci &lt;

Bir `CComBSTR` dizeyle bir ile karşılaştırır.

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe nesnesinden küçükse TRUE `CComBSTR` , DEĞILSE false döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırma, kullanıcının varsayılan yerel ayarı kullanılarak gerçekleştirilir.

## <a name="ccombstroperator-"></a><a name="operator_eq"></a> CComBSTR:: operator =

[M_str](#m_str) üyesini bir *pSrc* KOPYASı veya *src*'nin BSTR üyesinin bir kopyasına ayarlar. Taşıma atama işleci `src` kopyalanmadan taşınır.

```
CComBSTR& operator= (const CComBSTR& src);
CComBSTR& operator= (LPCOLESTR pSrc);
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>Açıklamalar

*PSrc* parametresi, Unicode sürümleri IÇIN BIR LPCOYESTR veya ANSI sürümleri için LPCSTR belirtir.

### <a name="example"></a>Örnek

[CComBSTR:: Copy](#copy)örneğine bakın.

## <a name="ccombstroperator-"></a><a name="operator_eq_eq"></a> CComBSTR:: operator = =

Bir `CComBSTR` dizeyle bir ile karşılaştırır. `CComBSTR`metin içeriğini eklemek, kullanıcının varsayılan yerel ayarı bağlamında karşılaştırılır.

```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
'ndaki Bir `CComBSTR` nesne.

*pszSrc*<br/>
'ndaki Sıfır ile sonlandırılmış bir dize.

*nNull*<br/>
'ndaki NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe nesnesine eşitse TRUE, `CComBSTR` DEĞILSE false döndürür.

### <a name="remarks"></a>Açıklamalar

Son karşılaştırma işleci yalnızca kapsanan dizeyi NULL ile karşılaştırır.

## <a name="ccombstroperator-gt"></a><a name="operator_gt"></a> CComBSTR:: işleci &gt;

Bir `CComBSTR` dizeyle bir ile karşılaştırır.

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe nesneden büyükse TRUE `CComBSTR` , DEĞILSE false döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırma, kullanıcının varsayılan yerel ayarı kullanılarak gerçekleştirilir.

## <a name="ccombstrreadfromstream"></a><a name="readfromstream"></a> CComBSTR:: ReadFromStream

[M_str](#m_str) üyesini belirtilen AKıŞTA bulunan BSTR 'ye ayarlar.

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
'ndaki Verileri içeren akıştaki [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`ReadToStream` bir [WriteToStream](#writetostream)çağrısıyla yazılmış veri biçimiyle uyumlu olması için geçerli konumdaki akışın içeriğini gerektirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

## <a name="ccombstrtolower"></a><a name="tolower"></a> CComBSTR:: ToLower

İçerilen dizeyi küçük harfe dönüştürür.

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`CharLowerBuff`Dönüştürmenin nasıl gerçekleştirildiği hakkında daha fazla bilgi için bkz..

## <a name="ccombstrtoupper"></a><a name="toupper"></a> CComBSTR:: ToUpper

İçerilen dizeyi büyük harfe dönüştürür.

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`CharUpperBuff`Dönüştürmenin nasıl gerçekleştirildiği hakkında daha fazla bilgi için bkz..

## <a name="ccombstrwritetostream"></a><a name="writetostream"></a> CComBSTR:: WriteToStream

[M_str](#m_str) üyesini bir akışa kaydeder.

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
'ndaki Akıştaki [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

[ReadFromStream](#readfromstream) işlevini kullanarak akışın IÇERIĞINDEN bir BSTR 'yi yeniden oluşturabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md)
