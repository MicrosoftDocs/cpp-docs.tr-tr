---
description: 'Daha fazla bilgi edinin: CTimeSpan sınıfı'
title: CTimeSpan sınıfı
ms.date: 10/18/2018
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
ms.openlocfilehash: b15fa247baaa4de77c5caab12d584a80321b9420
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166583"
---
# <a name="ctimespan-class"></a>CTimeSpan sınıfı

Zaman aralığında geçen saniye sayısı olarak dahili olarak depolanan bir süre.

## <a name="syntax"></a>Syntax

```
class CTimeSpan
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTimeSpan:: CTimeSpan](#ctimespan)|`CTimeSpan`Nesneleri çeşitli şekillerde oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTimeSpan:: biçim](#format)|Bir öğesini `CTimeSpan` biçimli bir dizeye dönüştürür.|
|[CTimeSpan:: GetDays](#getdays)|Bu, tüm gün sayısını temsil eden bir değer döndürür `CTimeSpan` .|
|[CTimeSpan:: Gethosta](#gethours)|Geçerli gündeki saat sayısını temsil eden bir değer döndürür (-23 ile 23 arasında).|
|[CTimeSpan:: GetMinutes](#getminutes)|Geçerli saat içindeki dakika sayısını temsil eden bir değer döndürür (-59 ile 59 arasında).|
|[CTimeSpan:: GetSeconds](#getseconds)|Geçerli dakikadaki saniye sayısını temsil eden bir değer döndürür (-59 ile 59 arasında).|
|[CTimeSpan:: GetTimeSpan](#gettimespan)|Nesnenin değerini döndürür `CTimeSpan` .|
|[CTimeSpan:: GetTotalHours](#gettotalhours)|Bu, tüm saatlerin toplam sayısını temsil eden bir değer döndürür `CTimeSpan` .|
|[CTimeSpan:: GetTotalMinutes](#gettotalminutes)|Bu, tüm dakikalarının toplam sayısını temsil eden bir değer döndürür `CTimeSpan` .|
|[CTimeSpan:: GetTotalSeconds](#gettotalseconds)|Bu, toplam tam saniye sayısını temsil eden bir değer döndürür `CTimeSpan` .|
|[CTimeSpan:: Serialize64](#serialize64)|Verileri bir arşivye veya bir arşive seri hale getirir.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç +-](#operator_add_-)|Nesneleri ekler ve çıkartır `CTimeSpan` .|
|[işleç + =-=](#operator_add_eq_-_eq)|`CTimeSpan`Nesnesine ve öğesinden bir nesne ekler ve çıkartır `CTimeSpan` .|
|[işleç = = < vb.](#ctimespan_comparison_operators)|İki göreli zaman değerini karşılaştırır.|

## <a name="remarks"></a>Açıklamalar

`CTimeSpan` taban sınıfına sahip değildir.

`CTimeSpan` işlevler saniyeleri gün, saat, dakika ve saniye birleşimlerine dönüştürür.

`CTimeSpan`Nesnesi, 8 bayt olan **__time64_t** yapısında saklanır.

Yardımcı bir sınıf, [CTime](../../atl-mfc-shared/reference/ctime-class.md), mutlak bir zamanı temsil eder.

`CTime`Ve `CTimeSpan` sınıfları türetme için tasarlanmamıştır. Sanal işlev olmadığından, hem hem de `CTime` `CTimeSpan` nesnelerinin boyutu tam olarak 8 bayttır. Çoğu üye işlevleri satır içidir.

Kullanma hakkında daha fazla bilgi için `CTimeSpan` bkz. *çalışma zamanı kitaplık başvurusunda* makalelerin [Tarih ve saat](../../atl-mfc-shared/date-and-time.md)ve [saat yönetimi](../../c-runtime-library/time-management.md) .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltime. h

## <a name="ctimespan-comparison-operators"></a><a name="ctimespan_comparison_operators"></a> CTimeSpan karşılaştırma Işleçleri

Karşılaştırma işleçleri.

```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu işleçler iki göreli zaman değerini karşılaştırır. Koşul true ise TRUE döndürür; Aksi halde yanlış.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

## <a name="ctimespanctimespan"></a><a name="ctimespan"></a> CTimeSpan:: CTimeSpan

`CTimeSpan`Nesneleri çeşitli şekillerde oluşturur.

```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(
    LONG lDays,
    int nHours,
    int nMins,
    int nSecs) throw();
```

### <a name="parameters"></a>Parametreler

*Zaman zaman*<br/>
`CTimeSpan`Zaten var olan bir nesne.

*ışınızda*<br/>
Zaman aralığında geçen saniye sayısı olan **__time64_t** saat değeri.

*Ldays*, *nhours*, *nmins*, *nSaniye*<br/>
Gün, saat, dakika ve saniye sırasıyla.

### <a name="remarks"></a>Açıklamalar

Tüm bu oluşturucular `CTimeSpan` , belirtilen göreli zaman ile başlatılan yeni bir nesne oluşturur. Her Oluşturucu aşağıda açıklanmıştır:

- `CTimeSpan( );` Başlatılmamış bir `CTimeSpan` nesne oluşturur.

- `CTimeSpan( const CTimeSpan& );` Başka bir `CTimeSpan` değerden bir nesne oluşturur `CTimeSpan` .

- `CTimeSpan( __time64_t );``CTimeSpan` **__Time64_t** türünden bir nesne oluşturur.

- `CTimeSpan( LONG, int, int, int );``CTimeSpan`Her bileşeni aşağıdaki aralıklar için kısıtlanmış olan bileşenlerden bir nesne oluşturur:

   |Bileşen|Aralık|
   |---------------|-----------|
   |*lDays*|0-25000 (yaklaşık)|
   |*Nsaat*|0-23|
   |*NDK*|0-59|
   |*nSaniye*|0-59|

Microsoft Foundation Class Kitaplığı hata ayıklama sürümünün, bir veya daha fazla zaman günü bileşeni Aralık dışında olup olmadığını onaydığına göz atın. Çağrılmadan önce bağımsız değişkenlerin doğrulanması sizin sorumluluğunuzdadır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

## <a name="ctimespanformat"></a><a name="format"></a> CTimeSpan:: biçim

Buna karşılık gelen biçimli bir dize oluşturur `CTimeSpan` .

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Parametreler

*pformat*, *pszFormat*<br/>
Biçimlendirme dizesine benzer bir biçimlendirme dizesi `printf` . Bir yüzde ( `%` ) işaretinden önce gelen biçimlendirme kodları ilgili `CTimeSpan` bileşenle değiştirilmiştir. Biçimlendirme dizesindeki diğer karakterler, döndürülen dizeye değiştirilmeden kopyalanır. İçin biçimlendirme kodlarının değeri ve anlamı `Format` aşağıda listelenmiştir:

- **% D** Bu toplam gün `CTimeSpan`

- **% H** Geçerli gündeki saat

- **% D** Geçerli saat içindeki dakika sayısı

- **% S** Geçerli dakikadaki Saniyeler

- **%%** Yüzde işareti

*NID*<br/>
Bu biçimi tanımlayan dizenin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

`CString`Biçimlendirilen saati içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Kitaplığın hata ayıklama sürümü biçimlendirme kodlarını denetler ve kodun yukarıdaki listede olup olmadığını onaylar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

## <a name="ctimespangetdays"></a><a name="getdays"></a> CTimeSpan:: GetDays

Bu, tüm gün sayısını temsil eden bir değer döndürür `CTimeSpan` .

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Zaman aralığında tam 24 saatlik gün sayısını döndürür. Zaman aralığı negatifse bu değer negatif olabilir.

### <a name="remarks"></a>Açıklamalar

Gün ışığından yararlanma saatinin `GetDays` potansiyel olarak ortaya çıkmış bir sonuç döndürmesine neden olabileceğini unutmayın. Örneğin, DST etkin olduğunda, `GetDays` Nisan 'daki bir gün bir saatten kısa bir süre tarafından kısaltılması ve bu nedenle tüm gün olarak saymadığı için 1 Nisan ve 1 Mayıs tarihleri arasındaki gün sayısını 30 olarak raporlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

## <a name="ctimespangethours"></a><a name="gethours"></a> CTimeSpan:: Gethosta

Geçerli gündeki saat sayısını temsil eden bir değer döndürür (-23 ile 23 arasında).

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli gündeki saat sayısını döndürür. Aralık-23 ile 23 arasındadır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

## <a name="ctimespangetminutes"></a><a name="getminutes"></a> CTimeSpan:: GetMinutes

Geçerli saat içindeki dakika sayısını temsil eden bir değer döndürür (-59 ile 59 arasında).

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli saatteki dakika sayısını döndürür. Aralık-59 ile 59 arasındadır.

### <a name="example"></a>Örnek

[Gethoi](#gethours)için örneğe bakın.

## <a name="ctimespangetseconds"></a><a name="getseconds"></a> CTimeSpan:: GetSeconds

Geçerli dakikadaki saniye sayısını temsil eden bir değer döndürür (-59 ile 59 arasında).

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dakikadaki saniye sayısını döndürür. Aralık-59 ile 59 arasındadır.

### <a name="example"></a>Örnek

[Gethoi](#gethours)için örneğe bakın.

## <a name="ctimespangettimespan"></a><a name="gettimespan"></a> CTimeSpan:: GetTimeSpan

Nesnenin değerini döndürür `CTimeSpan` .

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin geçerli değerini döndürür `CTimeSpan` .

## <a name="ctimespangettotalhours"></a><a name="gettotalhours"></a> CTimeSpan:: GetTotalHours

Bu, tüm saatlerin toplam sayısını temsil eden bir değer döndürür `CTimeSpan` .

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu, tüm saatlerin toplam sayısını döndürür `CTimeSpan` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

## <a name="ctimespangettotalminutes"></a><a name="gettotalminutes"></a> CTimeSpan:: GetTotalMinutes

Bu, tüm dakikalarının toplam sayısını temsil eden bir değer döndürür `CTimeSpan` .

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu, tüm dakikaların toplam sayısını döndürür `CTimeSpan` .

### <a name="example"></a>Örnek

[GetTotalHours](#gettotalhours)örneğine bakın.

## <a name="ctimespangettotalseconds"></a><a name="gettotalseconds"></a> CTimeSpan:: GetTotalSeconds

Bu, toplam tam saniye sayısını temsil eden bir değer döndürür `CTimeSpan` .

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu, toplam tam saniye sayısını döndürür `CTimeSpan` .

### <a name="example"></a>Örnek

[GetTotalHours](#gettotalhours)örneğine bakın.

## <a name="ctimespanoperator---"></a><a name="operator_add_-"></a> CTimeSpan:: operator +,-

Nesneleri ekler ve çıkartır `CTimeSpan` .

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Nesneye eklenecek değer `CTimeSpan` .

### <a name="return-value"></a>Dönüş Değeri

`CTimeSpan`İşlemin sonucunu temsil eden nesne.

### <a name="remarks"></a>Açıklamalar

Bu iki işleç, `CTimeSpan` birbirine ve birbirlerine nesne eklemenize ve bunları çıkareklemenize olanak tanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

## <a name="ctimespanoperator---"></a><a name="operator_add_eq_-_eq"></a> CTimeSpan:: operator + =,-=

`CTimeSpan`Nesnesine ve öğesinden bir nesne ekler ve çıkartır `CTimeSpan` .

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Nesneye eklenecek değer `CTimeSpan` .

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTimeSpan` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleçler, `CTimeSpan` Bu nesneye ve öğesinden bir nesne eklemenize ve çıkareklemenize olanak tanır `CTimeSpan` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

## <a name="ctimespanserialize64"></a><a name="serialize64"></a> CTimeSpan:: Serialize64

> [!NOTE]
> Bu yöntem yalnızca MFC projelerinde kullanılabilir.

Üye değişkeniyle ilişkili verileri bir arşivden veya bir arşive serileştirir.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
`CArchive`Güncelleştirmek istediğiniz nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CArchive` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
