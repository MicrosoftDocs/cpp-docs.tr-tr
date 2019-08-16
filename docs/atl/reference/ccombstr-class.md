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
ms.openlocfilehash: dd45c2ff9b43148e0fe27ebd410a2390a4d12ce2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497550"
---
# <a name="ccombstr-class"></a>CComBSTR sınıfı

Bu sınıf, [BSTR](/previous-versions/windows/desktop/automat/bstr)'leri için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

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
|[CComBSTR:: Append](#append)|Bir dize `m_str`ekler.|
|[CComBSTR:: AppendBSTR](#appendbstr)|İçin `m_str`bir BSTR ekler.|
|[CComBSTR:: AppendBytes](#appendbytes)|Belirtilen sayıda baytı `m_str`sonuna ekler.|
|[CComBSTR:: ArrayToBSTR](#arraytobstr)|SafeArray içindeki her bir öğenin ilk karakterinden bir BSTR oluşturur ve `CComBSTR` nesneye iliştirir.|
|[CComBSTR:: Atamabstr](#assignbstr)|İçin `m_str`bir BSTR atar.|
|[CComBSTR:: Attach](#attach)|`CComBSTR` Nesnesine bir BSTR ekler.|
|[CComBSTR:: BSTRToArray](#bstrtoarray)|Dizinin her öğesi `CComBSTR` nesnesinden bir karakter olduğunda, sıfır tabanlı tek boyutlu bir SAFEARRAY oluşturur.|
|[CComBSTR:: ByteLength](#bytelength)|Bayt `m_str` cinsinden uzunluğunu döndürür.|
|[CComBSTR:: Copy](#copy)|Bir kopyasını `m_str`döndürür.|
|[CComBSTR:: CopyTo](#copyto)|**[Out]** parametresi `m_str` aracılığıyla bir kopyasını döndürür|
|[CComBSTR::D etach](#detach)|Nesneden ayırır `m_str`. `CComBSTR`|
|[CComBSTR:: Empty](#empty)|Serbest `m_str`bırakır.|
|[CComBSTR:: length](#length)|Uzunluğunu `m_str`döndürür.|
|[CComBSTR:: LoadString](#loadstring)|Bir dize kaynağı yükler.|
|[CComBSTR:: ReadFromStream](#readfromstream)|Akıştan bir BSTR nesnesi yükler.|
|[CComBSTR:: ToLower](#tolower)|Dizeyi küçük harfe dönüştürür.|
|[CComBSTR:: ToUpper](#toupper)|Dizeyi büyük harfe dönüştürür.|
|[CComBSTR:: WriteToStream](#writetostream)|Bir `m_str` akışa kaydeder.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComBSTR:: operator BSTR](#operator_bstr)|Bir `CComBSTR` nesneyi BSTR 'ye yayınlar.|
|[CComBSTR:: operator!](#operator_not)|NULL olup olmadığına `m_str`bağlı olarak true veya false değerini döndürür.|
|[CComBSTR:: operator! =](#operator_neq)|Bir dizeyle `CComBSTR` bir ile karşılaştırır.|
|[CComBSTR:: operator &](#operator_amp)|Adresini `m_str`döndürür.|
|[CComBSTR:: operator + =](#operator_add_eq)|Nesnesine bir `CComBSTR` ekler.|
|[CComBSTR:: operator <](#operator_lt)|Bir dizeyle `CComBSTR` bir ile karşılaştırır.|
|[CComBSTR:: operator =](#operator_eq)|Öğesine `m_str`bir değer atar.|
|[CComBSTR:: operator = =](#operator_eq_eq)|Bir dizeyle `CComBSTR` bir ile karşılaştırır.|
|[CComBSTR:: operator >](#operator_gt)|Bir dizeyle `CComBSTR` bir ile karşılaştırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComBSTR:: m_str](#m_str)|`CComBSTR` Nesneyle ilişkili BSTR 'yi içerir.|

## <a name="remarks"></a>Açıklamalar

`CComBSTR` Sınıfı, uzunluk ön eki olan dizeler olan BSTRs için bir sarmalayıcıdır. Uzunluk, dizedeki verilerden önceki bellek konumunda bir tamsayı olarak depolanır.

[BSTR](/previous-versions/windows/desktop/automat/bstr) , son sayılan karakterden sonra null ile sonlandırılır, ancak dize içine gömülü null karakterler de içerebilir. Dize uzunluğu, ilk null karakter değil karakter sayısına göre belirlenir.

> [!NOTE]
>  `CComBSTR` Sınıfı, bağımsız değişken olarak ANSI veya Unicode dizeleri alan bir dizi üye (oluşturucular, atama işleçleri ve karşılaştırma işleçleri) sağlar. Geçici Unicode dizeleri genellikle dahili olarak oluşturulduğundan, bu işlevlerin ANSI sürümleri Unicode karşılıklarından daha az verimlidir. Verimlilik için mümkün olan yerlerde Unicode sürümlerini kullanın.

> [!NOTE]
>  Visual Studio .NET içinde uygulanan geliştirilmiş arama davranışı nedeniyle, gibi bir kod `bstr = L"String2" + bstr;`, önceki sürümlerde derlenmiş olabilecek gibi, yerine `bstr = CStringW(L"String2") + bstr`uygulanmalıdır.

Kullanırken `CComBSTR`uyarı listesi için bkz. [CComBSTR ile programlama](../../atl/programming-with-ccombstr-atl.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="append"></a>CComBSTR:: Append

*Bstrsrc* 'nin [m_str](#m_str)'e *lpsz* veya BSTR üyesini ekler.

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
'ndaki Eklenecek `CComBSTR` nesne.

*ch*<br/>
'ndaki Eklenecek karakter.

*lpsz*<br/>
'ndaki Sona eklenecek sıfır ile sonlandırılmış bir karakter dizesi. Bir Unicode dizesini LPCOLISTR aşırı yüklemesi veya bir ANSI dizesi aracılığıyla LPCSTR sürümü aracılığıyla geçirebilirsiniz.

*nLen*<br/>
'ndaki *Lpsz* 'den eklenecek karakterlerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değerine S_OK.

### <a name="remarks"></a>Açıklamalar

Bir ANSI dizesi eklenmeden önce Unicode olarak dönüştürülecek.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

##  <a name="appendbstr"></a>CComBSTR:: AppendBSTR

Belirtilen BSTR 'yi [m_str](#m_str)'e ekler.

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
'ndaki Eklenecek BSTR.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değerine S_OK.

### <a name="remarks"></a>Açıklamalar

Bu yönteme sıradan bir geniş karakterli dize geçirmeyin. Derleyici hatayı yakalayamaz ve çalıştırma zamanı hataları oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

##  <a name="appendbytes"></a>CComBSTR:: AppendBytes

Dönüştürme olmadan, belirtilen bayt sayısını [m_str](#m_str) 'e ekler.

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
'ndaki Eklenecek bayt dizisinin bir işaretçisi.

*p*<br/>
'ndaki Eklenecek bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değerine S_OK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

##  <a name="arraytobstr"></a>CComBSTR:: ArrayToBSTR

`CComBSTR` Nesnede tutulan mevcut dizeleri serbest bırakır, ardından SAFEARRAY içindeki her bir öğenin ilk karakterinden bir BSTR oluşturur ve `CComBSTR` nesneye iliştirir.

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
'ndaki Dizeyi oluşturmak için kullanılan öğeleri içeren SAFEARRAY.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değerine S_OK.

##  <a name="assignbstr"></a>CComBSTR:: Atamabstr

[M_str](#m_str)'e bir BSTR atar.

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
'ndaki Geçerli `CComBSTR` nesneye atanacak bir BSTR.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değerine S_OK.

##  <a name="attach"></a>CComBSTR:: Attach

[M_str](#m_str) üyesini *src*olarak ayarlayarak `CComBSTR` nesnesine bir BSTR ekler.

```
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>Parametreler

*YN*<br/>
'ndaki Nesneye iliştirilecek BSTR.

### <a name="remarks"></a>Açıklamalar

Bu yönteme sıradan bir geniş karakterli dize geçirmeyin. Derleyici hatayı yakalayamaz ve çalıştırma zamanı hataları oluşur.

> [!NOTE]
>  Bu yöntem, null `m_str` değilse onay olacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="bstrtoarray"></a>CComBSTR:: BSTRToArray

Dizinin her öğesi `CComBSTR` nesnesinden bir karakter olduğunda, sıfır tabanlı tek boyutlu bir SAFEARRAY oluşturur.

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>Parametreler

*ppArray*<br/>
dışı İşlevin sonuçlarını tutmak için kullanılan SAFEARRAY işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya herhangi bir standart HRESULT hata değerine S_OK.

##  <a name="bytelength"></a>CComBSTR:: ByteLength

' Deki `m_str`, Sonlandırıcı null karakteri hariç bayt sayısını döndürür.

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[M_str](#m_str) üyesinin bayt cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

NULL ise 0 `m_str` döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

##  <a name="ccombstr"></a>CComBSTR:: CComBSTR

Oluşturucu. Varsayılan Oluşturucu [m_str](#m_str) üyesini null olarak ayarlar.

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
'ndaki *SZ* 'den kopyalanacak karakter sayısı veya için `CComBSTR`karakter cinsinden başlangıç boyutu.

*SZ*<br/>
'ndaki Kopyalanacak dize. Unicode sürümü bir LPCOELSTR belirtir; ANSI sürümü bir LPCSTR belirtir.

*pSrc*<br/>
'ndaki Kopyalanacak dize. Unicode sürümü bir LPCOELSTR belirtir; ANSI sürümü bir LPCSTR belirtir.

*YN*<br/>
'ndaki Bir `CComBSTR` nesne.

*guid*<br/>
'ndaki Bir `GUID` yapıya başvuru.

### <a name="remarks"></a>Açıklamalar

Kopya Oluşturucu, `m_str` *src*öğesinin BSTR üyesinin bir kopyasına ayarlanır. Oluşturucu, kullanarak `StringFromGUID2` GUID 'yi bir dizeye dönüştürür ve sonucu depolar. `REFGUID`

Diğer oluşturucular belirtilen dizenin `m_str` bir kopyasına ayarlanır. *NSize*için bir değer geçirirseniz, yalnızca *nSize* karakterleri kopyalanacak ve ardından bir Sonlandırıcı null karakteri gelir.

`CComBSTR`taşıma semantiğini destekler. Nesne kopyalama ek yükü olmadan, bir bağımsız değişken olarak geçirdiğiniz eski nesneyle aynı temel`&&`verileri kullanan yeni bir nesne oluşturmak için, taşıma oluşturucusunu (bir rvalue başvurusu () alan Oluşturucu () kullanabilirsiniz.

Yıkıcı, tarafından `m_str`işaret edilen dizeyi serbest bırakır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

##  <a name="dtor"></a>CComBSTR:: ~ CComBSTR

Yok edicisi.

```
~CComBSTR();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, tarafından `m_str`işaret edilen dizeyi serbest bırakır.

##  <a name="copy"></a>CComBSTR:: Copy

Bir kopyasını `m_str`ayırır ve döndürür.

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[M_str](#m_str) üyesinin bir kopyası. `m_str` Null ise, null döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

##  <a name="copyto"></a>CComBSTR:: CopyTo

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

Bu yöntemi çağırdıktan sonra, *pvarDest* tarafından Işaret EDILEN değişken VT_BSTR türünde olacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

##  <a name="detach"></a>CComBSTR::D etach

`m_str` [M_str](#m_str) `CComBSTR` nesnesinden ayırır ve null olarak ayarlar.

```
BSTR Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CComBSTR` Nesneyle ilişkili BSTR.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

##  <a name="empty"></a>CComBSTR:: Empty

[M_str](#m_str) üyesini serbest bırakır.

```
void Empty() throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

##  <a name="length"></a>CComBSTR:: length

' Deki `m_str`karakter sayısını, Sonlandırıcı null karakteri hariç döndürür.

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[M_str](#m_str) üyesinin uzunluğu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

##  <a name="loadstring"></a>CComBSTR:: LoadString

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

##  <a name="m_str"></a>CComBSTR:: m_str

`CComBSTR` Nesneyle ilişkili BSTR 'yi içerir.

```
BSTR m_str;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

##  <a name="operator_bstr"></a>CComBSTR:: operator BSTR

Bir `CComBSTR` nesneyi BSTR 'ye yayınlar.

```
operator BSTR() const throw();
```

### <a name="remarks"></a>Açıklamalar

Nesneleri `CComBSTR` **[in] BSTR** parametrelerine sahip işlevlere geçirmenize olanak sağlar.

### <a name="example"></a>Örnek

[CComBSTR:: m_str](#m_str)örneğine bakın.

##  <a name="operator_not"></a>CComBSTR:: operator!

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

##  <a name="operator_neq"></a>CComBSTR:: operator! =

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

Karşılaştırılan öğe `CComBSTR` nesnesine eşitse true, değilse false döndürür.

### <a name="remarks"></a>Açıklamalar

`CComBSTR`metin içeriğini eklemek, kullanıcının varsayılan yerel ayarı bağlamında karşılaştırılır. Son karşılaştırma işleci yalnızca kapsanan dizeyi NULL ile karşılaştırır.

##  <a name="operator_amp"></a>CComBSTR:: işleci&amp;

[M_str](#m_str) ÜYESINDE depolanan BSTR 'nin adresini döndürür.

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>Açıklamalar

`CComBstr operator &`, bellek sızıntılarını belirlemenize yardımcı olmak için kendisiyle ilişkili özel bir onaylama işlemi içerir. Program, `m_str` üye başlatıldığında onay alacak. Bu onaylama, `& operator` bir programcının ilk ayırmayı `m_str`boşaltmadan `m_str` üyeye yeni bir değer atamak için kullandığı durumları belirlemek için oluşturulmuştur. Eşittir `m_str` null ise program m_str henüz ayrılmadığı varsayılır. Bu durumda, program onay olmaz.

Bu onaylama varsayılan olarak etkin değildir. Bu onayı etkinleştirmek için ATL_CCOMBSTR_ADDRESS_OF_ASSERT tanımlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

##  <a name="operator_add_eq"></a>CComBSTR:: operator + =

`CComBSTR` Nesnesine bir dize ekler.

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
'ndaki Eklenecek `CComBSTR` nesne.

*pszSrc*<br/>
'ndaki Sona eklenecek sıfır ile sonlandırılmış dize.

### <a name="remarks"></a>Açıklamalar

`CComBSTR`metin içeriğini eklemek, kullanıcının varsayılan yerel ayarı bağlamında karşılaştırılır. Lpcotastr karşılaştırması, her dizedeki ham `memcmp` verilerde kullanılarak yapılır. LPCSTR karşılaştırması, *pszSrc* 'nin geçici bir Unicode kopyası oluşturulduktan sonra aynı şekilde yürütülür. Son karşılaştırma işleci yalnızca kapsanan dizeyi NULL ile karşılaştırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

##  <a name="operator_lt"></a>CComBSTR:: işleci&lt;

Bir dizeyle `CComBSTR` bir ile karşılaştırır.

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe `CComBSTR` nesnesinden küçükse true, değilse false döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırma, kullanıcının varsayılan yerel ayarı kullanılarak gerçekleştirilir.

##  <a name="operator_eq"></a>CComBSTR:: operator =

[M_str](#m_str) üyesini bir *pSrc* KOPYASı veya *src*'nin BSTR üyesinin bir kopyasına ayarlar. Taşıma atama işleci kopyalanmadan `src` taşınır.

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

##  <a name="operator_eq_eq"></a>CComBSTR:: operator = =

Bir dizeyle `CComBSTR` bir ile karşılaştırır. `CComBSTR`metin içeriğini eklemek, kullanıcının varsayılan yerel ayarı bağlamında karşılaştırılır.

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

Karşılaştırılan öğe `CComBSTR` nesnesine eşitse true, değilse false döndürür.

### <a name="remarks"></a>Açıklamalar

Son karşılaştırma işleci yalnızca kapsanan dizeyi NULL ile karşılaştırır.

##  <a name="operator_gt"></a>CComBSTR:: işleci&gt;

Bir dizeyle `CComBSTR` bir ile karşılaştırır.

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe `CComBSTR` nesneden büyükse true, değilse false döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırma, kullanıcının varsayılan yerel ayarı kullanılarak gerçekleştirilir.

##  <a name="readfromstream"></a>CComBSTR:: ReadFromStream

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

`ReadToStream`bir [WriteToStream](#writetostream)çağrısıyla yazılmış veri biçimiyle uyumlu olması için geçerli konumdaki akışın içeriğini gerektirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

##  <a name="tolower"></a>CComBSTR:: ToLower

İçerilen dizeyi küçük harfe dönüştürür.

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Dönüştürmenin `CharLowerBuff` nasıl gerçekleştirildiği hakkında daha fazla bilgi için bkz.

##  <a name="toupper"></a>CComBSTR:: ToUpper

İçerilen dizeyi büyük harfe dönüştürür.

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Dönüştürmenin `CharUpperBuff` nasıl gerçekleştirildiği hakkında daha fazla bilgi için bkz.

##  <a name="writetostream"></a>CComBSTR:: WriteToStream

[M_str](#m_str) üyesini bir akışa kaydeder.

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
'ndaki Akıştaki IStream arabirimine [](/windows/win32/api/objidl/nn-objidl-istream) yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

[ReadFromStream](#readfromstream) işlevini kullanarak akışın IÇERIĞINDEN bir BSTR 'yi yeniden oluşturabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md)
