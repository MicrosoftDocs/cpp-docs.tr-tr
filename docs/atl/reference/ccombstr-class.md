---
title: CComBSTR Sınıfı
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
ms.openlocfilehash: adaad47c49a64c6654b70fa60ef5514e104c50a5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321047"
---
# <a name="ccombstr-class"></a>CComBSTR Sınıfı

Bu sınıf [BSTR'ler](/previous-versions/windows/desktop/automat/bstr)için bir sarmalayıcıdır.

## <a name="syntax"></a>Sözdizimi

```
class CComBSTR
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComBSTR::CComBSTR](#ccombstr)|Oluşturucu.|
|[CComBSTR::~CComBSTR](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComBSTR::Ek](#append)|Bir dize `m_str`ekler.|
|[CComBSTR::EkBSTR](#appendbstr)|Bir BSTR ekler. `m_str`|
|[CComBSTR::EklerBytes](#appendbytes)|Belirli sayıda bayt `m_str`ekler.|
|[CComBSTR::ArrayToBSTR](#arraytobstr)|Safearray her öğenin ilk karakteri bir BSTR oluşturur ve `CComBSTR` nesneye bağlar.|
|[CComBSTR::AtamaBSTR](#assignbstr)|Bir BSTR `m_str`atar.|
|[CComBSTR::Ekle](#attach)|`CComBSTR` Nesneye bir BSTR bağlar.|
|[CComBSTR::BSTRToArray](#bstrtoarray)|Dizinin her öğesinin `CComBSTR` nesneden bir karakter olduğu sıfır tabanlı tek boyutlu bir safearray oluşturur.|
|[CComBSTR::ByteLength](#bytelength)|Baytların `m_str` uzunluğunu verir.|
|[CComBSTR::Kopyala](#copy)|Bir kopyasını `m_str`döndürür.|
|[CComBSTR::CopyTo](#copyto)|**[out]** `m_str` parametresi üzerinden bir kopyasını verir|
|[CComBSTR::Detach](#detach)|Nesneden `CComBSTR` `m_str` ayrılır.|
|[CComBSTR::Boş](#empty)|Serbest `m_str`kalır.|
|[CComBSTR::Uzunluk](#length)|Uzunluk'u `m_str`verir.|
|[CComBSTR::LoadString](#loadstring)|Bir dize kaynağı yükler.|
|[CComBSTR::ReadFromStream](#readfromstream)|Bir akıştan bir BSTR nesnesi yükler.|
|[CComBSTR::ToLower](#tolower)|Dizeyi küçük harfe dönüştürür.|
|[CComBSTR::ToUpper](#toupper)|Dizeyi büyük harfe dönüştürür.|
|[CComBSTR::Writetostream](#writetostream)|Bir `m_str` akışa kaydeder.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CComBSTR::operatör BSTR](#operator_bstr)|Bir `CComBSTR` nesneyi BSTR'ye atar.|
|[CComBSTR::operatör !](#operator_not)|NULL olup olmadığına bağlı olarak `m_str`DOĞRU veya YANLIŞ döndürür.|
|[CComBSTR::operatör !=](#operator_neq)|Bir `CComBSTR` dize ile karşılaştırır.|
|[CComBSTR::operatör &](#operator_amp)|Adresini döndürür. `m_str`|
|[CComBSTR::operatör +=](#operator_add_eq)|Nesneye `CComBSTR` bir ekler.|
|[CComBSTR::operatör <](#operator_lt)|Bir `CComBSTR` dize ile karşılaştırır.|
|[CComBSTR::operatör =](#operator_eq)|`m_str`Bir değer atar.|
|[CComBSTR::operatör ==](#operator_eq_eq)|Bir `CComBSTR` dize ile karşılaştırır.|
|[CComBSTR::operatör >](#operator_gt)|Bir `CComBSTR` dize ile karşılaştırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComBSTR::m_str](#m_str)|Nesneyle ilişkili BSTR'yi `CComBSTR` içerir.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CComBSTR` uzunluk önceden belirlenmiş dizeleri olan TÇ'ler için bir sarmalayıcıdır. Uzunluk, dizedeki verilerden önceki bellek konumunda bir alıcı olarak depolanır.

Bir [BSTR,](/previous-versions/windows/desktop/automat/bstr) son sayılan karakterden sonra geçersiz sayılır, ancak dize içinde gömülü null karakterleri de içerebilir. Dize uzunluğu, ilk null karaktere göre değil, karakter sayısına göre belirlenir.

> [!NOTE]
> Sınıf, `CComBSTR` ANSI veya Unicode dizelerini bağımsız değişken olarak alan bir dizi üye (oluşturucular, atama işleçleri ve karşılaştırma işleçleri) sağlar. Geçici Unicode dizeleri genellikle dahili olarak oluşturulduğundan, bu işlevlerin ANSI sürümleri Unicode karşılıklarından daha az verimlidir. Verimlilik için mümkün olduğunca Unicode sürümlerini kullanın.

> [!NOTE]
> Visual Studio .NET'te uygulanan gelişmiş arama davranışı nedeniyle, önceki sürümlerde derlenmiş olabilecek `bstr = L"String2" + bstr;`kod yerine `bstr = CStringW(L"String2") + bstr`.

Kullanırken `CComBSTR`dikkat edilmesi gerektiği ne kadar önemli bir liste için, [CComBSTR ile Programlama](../../atl/programming-with-ccombstr-atl.md)bölümüne bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccombstrappend"></a><a name="append"></a>CComBSTR::Ek

Ekler ya *lpsz* veya *bstrSrc BSTR* üyesi [m_str](#m_str).

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
[içinde] Ekinde bir `CComBSTR` nesne.

*Caner*<br/>
[içinde] Eklemek için bir karakter.

*lpsz*<br/>
[içinde] Eklemek için sıfır sonlandırılmış karakter dizesi. LpCOLESTR aşırı yüklemesi veya LPCSTR sürümü aracılığıyla ANSI dizesi üzerinden bir Unicode dizesini geçirebilirsiniz.

*nLen*<br/>
[içinde] *Lpsz'den* ek karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir standart HRESULT hata değeri.

### <a name="remarks"></a>Açıklamalar

Bir ANSI dizesi eklenmeden önce Unicode'a dönüştürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

## <a name="ccombstrappendbstr"></a><a name="appendbstr"></a>CComBSTR::EkBSTR

[m_str](#m_str)için belirtilen BSTR ekler.

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Bir BSTR eklemek için.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir standart HRESULT hata değeri.

### <a name="remarks"></a>Açıklamalar

Bu yönteme sıradan bir geniş karakter dizesini geçirmeyin. Derleyici hatayı yakalayamaz ve çalışma süresi hataları oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

## <a name="ccombstrappendbytes"></a><a name="appendbytes"></a>CComBSTR::EklerBytes

Dönüşüm olmadan [m_str](#m_str) için belirtilen bayt sayısını ekler.

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
[içinde] Eklemek için bir dizi bayt için bir işaretçi.

*P*<br/>
[içinde] Ekinde eklenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir standart HRESULT hata değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

## <a name="ccombstrarraytobstr"></a><a name="arraytobstr"></a>CComBSTR::ArrayToBSTR

`CComBSTR` Nesnede tutulan varolan herhangi bir dizeyi boşaltır, ardından safearray'deki her öğenin ilk `CComBSTR` karakterinden bir BSTR oluşturur ve nesneye bağlar.

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
[içinde] Dize oluşturmak için kullanılan öğeleri içeren safearray.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir standart HRESULT hata değeri.

## <a name="ccombstrassignbstr"></a><a name="assignbstr"></a>CComBSTR::AtamaBSTR

[m_str](#m_str)bir BSTR atar.

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
[içinde] Geçerli `CComBSTR` nesneye atamak için bir BSTR.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir standart HRESULT hata değeri.

## <a name="ccombstrattach"></a><a name="attach"></a>CComBSTR::Ekle

`CComBSTR` [m_str](#m_str) üyeyi *src'ye*ayarlayarak nesneye bir BSTR bağlar.

```
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[içinde] Nesneye takmak için BSTR.

### <a name="remarks"></a>Açıklamalar

Bu yönteme sıradan bir geniş karakter dizesini geçirmeyin. Derleyici hatayı yakalayamaz ve çalışma süresi hataları oluşur.

> [!NOTE]
> Null olmayan `m_str` bu yöntem ileri sürecektir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

## <a name="ccombstrbstrtoarray"></a><a name="bstrtoarray"></a>CComBSTR::BSTRToArray

Dizinin her öğesinin `CComBSTR` nesneden bir karakter olduğu sıfır tabanlı tek boyutlu bir safearray oluşturur.

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>Parametreler

*ppArray*<br/>
[çıkış] İşlevin sonuçlarını tutmak için kullanılan güvenli dizi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir standart HRESULT hata değeri.

## <a name="ccombstrbytelength"></a><a name="bytelength"></a>CComBSTR::ByteLength

Sonlandırıcı null karakteri hariç `m_str`olmak üzere bayt sayısını verir.

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

baytlarda [m_str](#m_str) üyenin uzunluğu.

### <a name="remarks"></a>Açıklamalar

NULL ise `m_str` 0 döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

## <a name="ccombstrccombstr"></a><a name="ccombstr"></a>CComBSTR::CComBSTR

Oluşturucu. Varsayılan oluşturucu [m_str](#m_str) üyesini NULL olarak ayarlar.

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
[içinde] Sz'den kopyalanması *sz* gereken karakter sayısı veya karakterlerdeki `CComBSTR`ilk boyut.

*Sz*<br/>
[içinde] Kopyalanması gereken bir dize. Unicode sürümü bir LPCOLESTR belirtir; ANSI sürümü bir LPCSTR belirtir.

*pSrc*<br/>
[içinde] Kopyalanması gereken bir dize. Unicode sürümü bir LPCOLESTR belirtir; ANSI sürümü bir LPCSTR belirtir.

*src*<br/>
[içinde] Bir `CComBSTR` nesne.

*Guıd*<br/>
[içinde] Bir `GUID` yapıya gönderme.

### <a name="remarks"></a>Açıklamalar

Kopya oluşturucu `m_str` *src*BSTR üyesinin bir kopyasını ayarlar. Oluşturucu GUID'i `REFGUID` kullanarak `StringFromGUID2` bir dize dönüştürür ve sonucu depolar.

Diğer oluşturucular `m_str` belirtilen dize bir kopyasına ayarlayın. *nSize*için bir değer geçerseniz, yalnızca *nSize* karakterleri kopyalanır ve ardından sonlandırıcı null karakter elde eve geçer.

`CComBSTR`taşıma semantikini destekler. Nesneyi kopyalama ek yükü olmadan, bağımsız değişken olarak`&&`geçtiğiniz eski nesneyle aynı temel verileri kullanan yeni bir nesne oluşturmak için taşı oluşturucuyu (rvalue başvurusu alan oluşturucu ( ) kullanabilirsiniz.

Yıkıcı tarafından işaret `m_str`edilen dize serbest.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

## <a name="ccombstrccombstr"></a><a name="dtor"></a>CComBSTR::~CComBSTR

Yıkıcı.

```
~CComBSTR();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı tarafından işaret `m_str`edilen dize serbest.

## <a name="ccombstrcopy"></a><a name="copy"></a>CComBSTR::Kopyala

Bir kopyasını ayırır ve `m_str`döndürür.

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[m_str](#m_str) üyenin bir kopyası. NULL `m_str` ise, NULL döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

## <a name="ccombstrcopyto"></a><a name="copyto"></a>CComBSTR::CopyTo

Parametre üzerinden [m_str](#m_str) bir kopyasını ayırır ve döndürür.

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>Parametreler

*pbstr*<br/>
[çıkış] Bu yöntemtarafından ayrılan dize yi döndürecek bir BSTR'nin adresi.

*pvarDest*<br/>
[çıkış] Bu yöntemtarafından ayrılan dize dönmek için bir VARYANT adresi.

### <a name="return-value"></a>Dönüş Değeri

Kopyanın başarısını veya başarısızlığını gösteren standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi aradıktan sonra, *pvarDest* tarafından işaret edilen VARIANT tip VT_BSTR olacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

## <a name="ccombstrdetach"></a><a name="detach"></a>CComBSTR::Detach

[m_str](#m_str) `CComBSTR` nesneden ayırır ve `m_str` NULL'a ayarlar.

```
BSTR Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CComBSTR` Nesneyle ilişkili BSTR.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

## <a name="ccombstrempty"></a><a name="empty"></a>CComBSTR::Boş

[m_str](#m_str) üyeyi serbest.

```
void Empty() throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

## <a name="ccombstrlength"></a><a name="length"></a>CComBSTR::Uzunluk

Sonlandırıcı null karakter `m_str`hariç, karakter sayısını verir.

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[m_str](#m_str) üyenin uzunluğu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

## <a name="ccombstrloadstring"></a><a name="loadstring"></a>CComBSTR::LoadString

*NID* tarafından belirtilen bir dize kaynağı yükler ve bu nesnede depolar.

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>Parametreler

Bkz. Windows SDK'daki [LoadString.](/windows/win32/api/winuser/nf-winuser-loadstringw)

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla yüklenirse TRUE döndürür; aksi takdirde, FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

İlk işlev, *hInst* parametresi aracılığıyla sizin belirlediğiniz modülden kaynağı yükler. İkinci işlev, bu projede kullanılan [CComModule](../../atl/reference/ccommodule-class.md)türetilmiş nesneyle ilişkili kaynak modülünden kaynağı yükler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

## <a name="ccombstrm_str"></a><a name="m_str"></a>CComBSTR::m_str

Nesneyle ilişkili BSTR'yi `CComBSTR` içerir.

```
BSTR m_str;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

## <a name="ccombstroperator-bstr"></a><a name="operator_bstr"></a>CComBSTR::operatör BSTR

Bir `CComBSTR` nesneyi BSTR'ye atar.

```
operator BSTR() const throw();
```

### <a name="remarks"></a>Açıklamalar

BSTR parametrelerine `CComBSTR` **sahip** işlevlere nesneleri geçirmenizi sağlar.

### <a name="example"></a>Örnek

[CComBSTR örneğine bakın:m_str.](#m_str)

## <a name="ccombstroperator-"></a><a name="operator_not"></a>CComBSTR::operatör !

BSTR dizesi NULL olup olmadığını denetler.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[m_str](#m_str) üyesi NULL ise TRUE döndürür; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu işleç boş bir dize için değil, yalnızca null değerini denetler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

## <a name="ccombstroperator-"></a><a name="operator_neq"></a>CComBSTR::operatör !=

[İşleç ==](#operator_eq_eq)mantıksal tersini verir.

```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
[içinde] Bir `CComBSTR` nesne.

*pszSrc*<br/>
[içinde] Sıfır sonlandırılmış dize.

*nNull*<br/>
[içinde] NULL olmalı.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe `CComBSTR` nesneye eşit değilse TRUE döndürür; aksi takdirde, FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CComBSTR`ler, kullanıcının varsayılan yerel alanı bağlamında metinsel olarak karşılaştırılır. Son karşılaştırma işleci sadece NULL karşı içerdiği dize karşılaştırır.

## <a name="ccombstroperator-amp"></a><a name="operator_amp"></a>CComBSTR::operatör&amp;

[m_str](#m_str) üyesinde depolanan BSTR'nin adresini verir.

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>Açıklamalar

`CComBstr operator &`bellek sızıntılarını belirlemeye yardımcı olmak için onunla ilişkili özel bir iddiası vardır. `m_str` Program, üye nin para yada başharfe basılan zaman ortaya koyacağını iddia edecektir. Bu iddia, bir programcının ilk `& operator` tahsisatını serbest etmeden `m_str` üyeye yeni bir `m_str`değer atamak için kullandığı durumları tanımlamak için oluşturulmuştur. NULL `m_str` eşittirse, program m_str henüz tahsis olmadığını varsayar. Bu durumda, program iddia etmez.

Bu seçme varsayılan olarak etkinleştir Bu iddiayı etkinleştirmek için ATL_CCOMBSTR_ADDRESS_OF_ASSERT tanımlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

## <a name="ccombstroperator-"></a><a name="operator_add_eq"></a>CComBSTR::operatör +=

`CComBSTR` Nesneye bir dize ekler.

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
[içinde] Ekinde bir `CComBSTR` nesne.

*pszSrc*<br/>
[içinde] Eklemek için sıfır sonlandırılmış bir dize.

### <a name="remarks"></a>Açıklamalar

`CComBSTR`ler, kullanıcının varsayılan yerel alanı bağlamında metinsel olarak karşılaştırılır. LPCOLESTR karşılaştırması her `memcmp` dizedeki ham veriler kullanılarak yapılır. *LPCSTR karşılaştırması, pszSrc'nin* geçici unicode kopyası oluşturulduktan sonra aynı şekilde gerçekleştirilir. Son karşılaştırma işleci sadece NULL karşı içerdiği dize karşılaştırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

## <a name="ccombstroperator-lt"></a><a name="operator_lt"></a>CComBSTR::operatör&lt;

Bir `CComBSTR` dize ile karşılaştırır.

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe `CComBSTR` nesneden daha azsa TRUE döndürür; aksi takdirde, FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırma, kullanıcının varsayılan yerel alanı kullanılarak gerçekleştirilir.

## <a name="ccombstroperator-"></a><a name="operator_eq"></a>CComBSTR::operatör =

[m_str](#m_str) üyeyi *pSrc'nin* bir kopyasına veya *BSTR*üyesinin bir kopyasına ayarlar. Taşıma atama sıyrık kopyalamadan hareket eder. `src`

```
CComBSTR& operator= (const CComBSTR& src);
CComBSTR& operator= (LPCOLESTR pSrc);
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>Açıklamalar

*pSrc* parametresi, Unicode sürümleri için LPCOLESTR veya ANSI sürümleri için LPCSTR belirtir.

### <a name="example"></a>Örnek

CComBSTR için örneğe [bakın:Kopyala.](#copy)

## <a name="ccombstroperator-"></a><a name="operator_eq_eq"></a>CComBSTR::operatör ==

Bir `CComBSTR` dize ile karşılaştırır. `CComBSTR`ler, kullanıcının varsayılan yerel alanı bağlamında metinsel olarak karşılaştırılır.

```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```

### <a name="parameters"></a>Parametreler

*bstrSrc*<br/>
[içinde] Bir `CComBSTR` nesne.

*pszSrc*<br/>
[içinde] Sıfır sonlandırılmış dize.

*nNull*<br/>
[içinde] NULL olmalı.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe nesneye eşitse `CComBSTR` TRUE döndürür; aksi takdirde, FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Son karşılaştırma işleci sadece NULL karşı içerdiği dize karşılaştırır.

## <a name="ccombstroperator-gt"></a><a name="operator_gt"></a>CComBSTR::operatör&gt;

Bir `CComBSTR` dize ile karşılaştırır.

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe `CComBSTR` nesneden büyükse TRUE döndürür; aksi takdirde, FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırma, kullanıcının varsayılan yerel alanı kullanılarak gerçekleştirilir.

## <a name="ccombstrreadfromstream"></a><a name="readfromstream"></a>CComBSTR::ReadFromStream

[m_str](#m_str) üyesini belirtilen akışta bulunan BSTR'ye ayarlar.

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[içinde] Verileri içeren akıştaki [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`ReadToStream`geçerli konumdaki akış içeriğinin [WriteToStream'e](#writetostream)yapılan bir çağrı yla yazılmış veri biçimiyle uyumlu olmasını gerektirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

## <a name="ccombstrtolower"></a><a name="tolower"></a>CComBSTR::ToLower

İçerdiği dizeyi küçük harfe dönüştürür.

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Dönüşümün nasıl gerçekleştirildiği hakkında daha fazla bilgi için bkz. `CharLowerBuff`

## <a name="ccombstrtoupper"></a><a name="toupper"></a>CComBSTR::ToUpper

İçerdiği dizeyi büyük harfe dönüştürür.

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Dönüşümün nasıl gerçekleştirildiği hakkında daha fazla bilgi için bkz. `CharUpperBuff`

## <a name="ccombstrwritetostream"></a><a name="writetostream"></a>CComBSTR::Writetostream

[m_str](#m_str) üyeyi bir akışa kaydeder.

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[içinde] Akış üzerindeki [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

[ReadFromStream](#readfromstream) işlevini kullanarak akışın içeriğinden bir BSTR oluşturabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[ATL ve MFC String Dönüşüm Makroları](string-conversion-macros.md)
