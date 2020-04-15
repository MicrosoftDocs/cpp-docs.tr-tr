---
title: CTimeSpan Sınıfı
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
ms.openlocfilehash: 14aa5eb52e2c631a92e40ae7053c566284e00e57
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317497"
---
# <a name="ctimespan-class"></a>CTimeSpan Sınıfı

Zaman aralığındaki saniye sayısı olarak dahili olarak depolanan bir süre.

## <a name="syntax"></a>Sözdizimi

```
class CTimeSpan
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CTimeSpan::CTimeSpan](#ctimespan)|Nesneleri `CTimeSpan` çeşitli şekillerde inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTimeSpan::Biçim](#format)|A'yı `CTimeSpan` biçimlendirilmiş bir dize dönüştürür.|
|[CTimeSpan::GetDays](#getdays)|Bu `CTimeSpan`işlemdeki tam gün sayısını temsil eden bir değer verir.|
|[CTimeSpan::GetHours](#gethours)|Geçerli gündeki saat sayısını (-23'ten 23'e) temsil eden bir değer döndürür.|
|[CTimeSpan::GetMinutes](#getminutes)|Geçerli saatteki dakika sayısını temsil eden bir değer döndürür (-59 ile 59 arası).|
|[CTimeSpan::GetSeconds](#getseconds)|Geçerli dakikadaki saniye sayısını temsil eden bir değer döndürür (-59'dan 59'a kadar).|
|[CTimeSpan::GetTimeSpan](#gettimespan)|`CTimeSpan` Nesnenin değerini döndürür.|
|[CTimeSpan::GetTotalHours](#gettotalhours)|Bu `CTimeSpan`işlemdeki toplam saat sayısını temsil eden bir değer verir.|
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Bu `CTimeSpan`işlemdeki toplam dakika sayısını temsil eden bir değer verir.|
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Bu `CTimeSpan`işlemdeki toplam saniye sayısını temsil eden bir değer verir.|
|[CTimeSpan::Serialize64](#serialize64)|Arşive veya arşivden gelen verileri seri hale getirmek.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operatör + -](#operator_add_-)|`CTimeSpan` Nesneleri ekler ve çıkarır.|
|[işleç += -=](#operator_add_eq_-_eq)|Bir `CTimeSpan` nesne ekler ve çıkarır. `CTimeSpan`|
|[işleci == < vb.](#ctimespan_comparison_operators)|İki göreli zaman değerini karşılaştırır.|

## <a name="remarks"></a>Açıklamalar

`CTimeSpan`taban sınıfa sahip değildir.

`CTimeSpan`işlevler saniyeleri gün, saat, dakika ve saniyenin çeşitli kombinasyonlarına dönüştürür.

Nesne `CTimeSpan` 8 bayt olan **bir __time64_t** yapısında depolanır.

Bir arkadaşı sınıf, [CTime](../../atl-mfc-shared/reference/ctime-class.md), mutlak bir zaman temsil eder.

`CTime` Ve `CTimeSpan` sınıflar türetme için tasarlanmaz. Sanal işlev ler olmadığından, hem `CTime` nesnelerin `CTimeSpan` hem de nesnelerin boyutu tam olarak 8 bayttır. Üye işlevlerin çoğu satır lıdır.

`CTimeSpan`Kullanma hakkında daha fazla bilgi için, *Run-Time Kitaplığı Başvurusu'ndaki* [Tarih ve Saat](../../atl-mfc-shared/date-and-time.md)ve [Zaman Yönetimi](../../c-runtime-library/time-management.md) makalelerini görün.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltime.h

## <a name="ctimespan-comparison-operators"></a><a name="ctimespan_comparison_operators"></a>CTimeSpan Karşılaştırma Operatörleri

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

*Span*<br/>
Karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu işleçler iki göreli zaman değerlerini karşılaştırır. Koşul doğruysa TRUE döndürerler; aksi takdirde YANLIŞ.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

## <a name="ctimespanctimespan"></a><a name="ctimespan"></a>CTimeSpan::CTimeSpan

Nesneleri `CTimeSpan` çeşitli şekillerde inşa eder.

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

*timeSpanSrc*<br/>
Zaten `CTimeSpan` var olan bir nesne.

*time*<br/>
Zaman aralığındaki saniye sayısı olan **__time64_t** bir zaman değeri.

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
Sırasıyla günler, saatler, dakikalar ve saniyeler.

### <a name="remarks"></a>Açıklamalar

Tüm bu oluşturucular, `CTimeSpan` belirtilen göreli süreyle birlikte baş harfe getirilmiş yeni bir nesne oluştururlar. Her yapıcı aşağıda açıklanmıştır:

- `CTimeSpan( );`Başledilmemiş `CTimeSpan` bir nesne oluşturuyor.

- `CTimeSpan( const CTimeSpan& );`Bir nesneyi başka `CTimeSpan` bir `CTimeSpan` değerden inşa eder.

- `CTimeSpan( __time64_t );``CTimeSpan` **__time64_t** türünden bir nesne oluşturuyor.

- `CTimeSpan( LONG, int, int, int );`Aşağıdaki aralıklarla sınırlandırılmış her bileşene sahip bileşenlerden bir `CTimeSpan` nesne oluşur:

   |Bileşen|Aralık|
   |---------------|-----------|
   |*lGün sayısı*|0-25.000 (yaklaşık)|
   |*nHours*|0-23|
   |*nMins*|0-59|
   |*nSecs*|0-59|

Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümünün, gün içinde yapılan bileşenlerden biri veya daha fazlası kapsama alanı dışında ysa bunu öne sürttürün. Aramadan önce argümanları doğrulamak sizin sorumluluğunuzdadır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

## <a name="ctimespanformat"></a><a name="format"></a>CTimeSpan::Biçim

Buna `CTimeSpan`karşılık gelen biçimlendirilmiş bir dize oluşturur.

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Parametreler

*pFormat*, *pszFormat*<br/>
Biçimlendirme dizesine `printf` benzer bir biçimlendirme dizesi. Bir yüzde ( )`%`işaretinden önce biçimlendirme kodları ilgili `CTimeSpan` bileşen tarafından değiştirilir. Biçimlendirme dizesindeki diğer karakterler döndürülen dize değişmeden kopyalanır. Biçimlendirme kodlarının `Format` değeri ve anlamı aşağıda listelenmiştir:

- **%D** Bu toplam gün`CTimeSpan`

- **%H** Geçerli gündeki saatler

- **%M** Geçerli saatteki dakikalar

- **%S** Geçerli dakikadaki saniyeler

- **%%** Yüzde işareti

*Nıd*<br/>
Bu biçimi tanımlayan dize kimliği.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilmiş zamanı içeren bir `CString` nesne.

### <a name="remarks"></a>Açıklamalar

Kitaplığın Hata Ayıklama sürümü biçimlendirme kodlarını denetler ve kod yukarıdaki listede değilse ileri sürüler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

## <a name="ctimespangetdays"></a><a name="getdays"></a>CTimeSpan::GetDays

Bu `CTimeSpan`işlemdeki tam gün sayısını temsil eden bir değer verir.

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Zaman aralığında tam 24 saatlik gün sayısını verir. Zaman aralığı negatifse bu değer negatif olabilir.

### <a name="remarks"></a>Açıklamalar

Gün ışığından yararlanma `GetDays` saatinin şaşırtıcı olabilecek bir sonucu döndürebileceğini unutmayın. Örneğin, DST geçerli olduğunda, `GetDays` Nisan ayında bir gün bir saat kısaltıldığından ve bu nedenle tam bir gün olarak sayılmaz, çünkü 1 Nisan ve 1 Mayıs arasındaki gün sayısını 29 değil, 30 olarak bildirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

## <a name="ctimespangethours"></a><a name="gethours"></a>CTimeSpan::GetHours

Geçerli gündeki saat sayısını (-23'ten 23'e) temsil eden bir değer döndürür.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli gündeki saat sayısını verir. Aralık -23 ile 23 arasındadır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

## <a name="ctimespangetminutes"></a><a name="getminutes"></a>CTimeSpan::GetMinutes

Geçerli saatteki dakika sayısını temsil eden bir değer döndürür (-59 ile 59 arası).

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli saatteki dakika sayısını verir. Menzil -59 ile 59 arası.

### <a name="example"></a>Örnek

[GetHours](#gethours)örneğine bakın.

## <a name="ctimespangetseconds"></a><a name="getseconds"></a>CTimeSpan::GetSeconds

Geçerli dakikadaki saniye sayısını temsil eden bir değer döndürür (-59'dan 59'a kadar).

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dakikadaki saniye sayısını döndürür. Menzil -59 ile 59 arası.

### <a name="example"></a>Örnek

[GetHours](#gethours)örneğine bakın.

## <a name="ctimespangettimespan"></a><a name="gettimespan"></a>CTimeSpan::GetTimeSpan

`CTimeSpan` Nesnenin değerini döndürür.

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CTimeSpan` Nesnenin geçerli değerini döndürür.

## <a name="ctimespangettotalhours"></a><a name="gettotalhours"></a>CTimeSpan::GetTotalHours

Bu `CTimeSpan`işlemdeki toplam saat sayısını temsil eden bir değer verir.

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CTimeSpan`işlemdeki toplam tam saat sayısını verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

## <a name="ctimespangettotalminutes"></a><a name="gettotalminutes"></a>CTimeSpan::GetTotalMinutes

Bu `CTimeSpan`işlemdeki toplam dakika sayısını temsil eden bir değer verir.

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CTimeSpan`işlemdeki toplam dakika sayısını verir.

### <a name="example"></a>Örnek

[GetTotalHours](#gettotalhours)örneğine bakın.

## <a name="ctimespangettotalseconds"></a><a name="gettotalseconds"></a>CTimeSpan::GetTotalSeconds

Bu `CTimeSpan`işlemdeki toplam saniye sayısını temsil eden bir değer verir.

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CTimeSpan`işlemdeki toplam saniye sayısını verir.

### <a name="example"></a>Örnek

[GetTotalHours](#gettotalhours)örneğine bakın.

## <a name="ctimespanoperator---"></a><a name="operator_add_-"></a>CTimeSpan::operatör +, -

`CTimeSpan` Nesneleri ekler ve çıkarır.

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*<br/>
`CTimeSpan` Nesneye eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

İşlemin sonucunu temsil eden bir `CTimeSpan` nesne.

### <a name="remarks"></a>Açıklamalar

Bu iki işleç, `CTimeSpan` nesneleri birbirlerinden ve nesneleri eklemenize ve çıkarmanıza izin verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

## <a name="ctimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>CTimeSpan::işleç +=, -=

Bir `CTimeSpan` nesne ekler ve çıkarır. `CTimeSpan`

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*Span*<br/>
`CTimeSpan` Nesneye eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTimeSpan` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleçler, bir `CTimeSpan` nesne eklemenize ve `CTimeSpan`bu maddeden çıkarmanıza izin verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

## <a name="ctimespanserialize64"></a><a name="serialize64"></a>CTimeSpan::Serialize64

> [!NOTE]
> Bu yöntem yalnızca MFC projelerinde kullanılabilir.

Bir arşive veya arşivden üye değişkenle ilişkili verileri seri hale getirmek.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
Güncelleştirmek istediğiniz `CArchive` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CArchive` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
