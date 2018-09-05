---
title: CTimeSpan sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6703c177b20230d7308ebd22b3b54edbdb1d2a14
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758712"
---
# <a name="ctimespan-class"></a>CTimeSpan sınıfı

Bir zaman aralığı saniye sayısı olarak dahili olarak depolanan bir zaman miktarı.

## <a name="syntax"></a>Sözdizimi

```
class CTimeSpan
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTimeSpan::CTimeSpan](#ctimespan)|Yapıları `CTimeSpan` çeşitli yollarla nesneleri.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTimeSpan::Format](#format)|Dönüştürür bir `CTimeSpan` olarak biçimlendirilmiş bir dize.|
|[CTimeSpan::GetDays](#getdays)|Bu tam gün sayısını gösteren bir değer döndürür `CTimeSpan`.|
|[CTimeSpan::GetHours](#gethours)|(-23-23) geçerli günün saat sayısını temsil eden bir değer döndürür.|
|[CTimeSpan::GetMinutes](#getminutes)|Geçerli saatte (-59-59) dakika sayısını temsil eden bir değer döndürür.|
|[CTimeSpan::GetSeconds](#getseconds)|Geçerli dakika (-59-59) saniye sayısını gösteren bir değer döndürür.|
|[CTimeSpan::GetTimeSpan](#gettimespan)|Değerini döndürür `CTimeSpan` nesne.|
|[CTimeSpan::GetTotalHours](#gettotalhours)|Bu tam bir saat toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.|
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Bu tam dakika toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.|
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Bu tam saniye toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.|
|[CTimeSpan::Serialize64](#serialize64)|Bir arşiv veri serileştirir.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator + -](#operator_add_-)|Ekler ve çıkarır `CTimeSpan` nesneleri.|
|[operator +=-=](#operator_add_eq_-_eq)|Ekler ve çıkaran bir `CTimeSpan` nesne için ve bu `CTimeSpan`.|
|[işleç == < vs.](#ctimespan_comparison_operators)|İki göreli zaman değerleri karşılaştırır.|

## <a name="remarks"></a>Açıklamalar

`CTimeSpan` bir temel sınıfa sahip değil.

`CTimeSpan` işlevleri saniye çeşitli birleşimlerini gün, saat, dakika ve saniye dönüştürür.

`CTimeSpan` Nesne içinde depolandığı bir **__time64_t** 8 bayt olan yapısı.

Bir yardımcı sınıfı [CTime](../../atl-mfc-shared/reference/ctime-class.md), mutlak bir zamanı temsil eder.

`CTime` Ve `CTimeSpan` sınıflar türetmeyi için tasarlanmamıştır. Hiçbir sanal işlevler, her ikisi de boyutu olduğundan `CTime` ve `CTimeSpan` nesneleri, tam olarak 8 bayt. Çoğu üye satır içi işlevlerdir.

Kullanma hakkında daha fazla bilgi için `CTimeSpan`, makalelere göz atın [tarih ve saat](../../atl-mfc-shared/date-and-time.md), ve [zaman Yönetimi](../../c-runtime-library/time-management.md) içinde *çalışma zamanı kitaplığı başvurusu*.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atltime.h

##  <a name="ctimespan_comparison_operators"></a>  CTimeSpan Karşılaştırma işleçleri

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

*yayılma*

Karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu işleçler, iki göreli zaman değerleri karşılaştırın. Koşul true ise, TRUE döndürür; Aksi durumda FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

##  <a name="ctimespan"></a>  CTimeSpan::CTimeSpan

Yapıları `CTimeSpan` çeşitli yollarla nesneleri.

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

*timeSpanSrc*  
A `CTimeSpan` zaten var. nesne.

*saat*  
A **__time64_t** zaman değeri, zaman aralığı içinde saniye sayısı.

*lDays*, *nHours*, *nMins*, *nSecs*  
Gün, saat, dakika ve saniye, sırasıyla.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucular yeni bir oluşturma `CTimeSpan` nesne belirtilen göreli zaman ile başlatıldı. Her Oluşturucu, aşağıda açıklanmıştır:

- `CTimeSpan( );` Başlatılmamış bir yapıları `CTimeSpan` nesne.

- `CTimeSpan( const CTimeSpan& );` Oluşturur bir `CTimeSpan` başka bir nesne `CTimeSpan` değeri.

- `CTimeSpan( __time64_t );` Oluşturur bir `CTimeSpan` nesnesinden bir **__time64_t** türü.

- `CTimeSpan( LONG, int, int, int );` Oluşturur bir `CTimeSpan` nesne bileşenlerinden her bileşeni ile kısıtlanmış aşağıdaki aralıklara:

    |Bileşen|Aralık|  
    |---------------|-----------|  
    |*lDays*|0-25.000 (yaklaşık)|  
    |*nHours*|0-23|  
    |*nMins*|0-59|  
    |*nSecs*|0-59|

Bir Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar not ya da daha fazla zaman günlük bileşen je mimo rozsah. Bu bağımsız değişkenler çağrılmadan önce doğrulamak için sizin sorumluluğunuzdur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

##  <a name="format"></a>  CTimeSpan::Format

Bunun için karşılık gelen bir biçimlendirilmiş dize üretir `CTimeSpan`.

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Parametreler

*pFormat*, *pszFormat*  
Bir biçimlendirme dizesi benzer `printf` biçimlendirme dizesi. Biçimlendirme kodları, öncesinde bir yüzde (`%`) oturum açın, ilgili değiştirilir `CTimeSpan` bileşeni. Biçimlendirme dizesi diğer karakterler döndürülen dizeye değiştirilmeden kopyalanır. Değer ve biçimlendirme kodları anlamını `Format` aşağıda listelenmiştir:

- **%D** toplam bu gün `CTimeSpan`

- **%H** geçerli günün saat

- **%M** geçerli bir saatteki dakika

- **%S** geçerli dakika, saniye

- **%%** Yüzde işareti

*nID*  
Bu biçim tanımlayan dize kimliği.

### <a name="return-value"></a>Dönüş Değeri

A `CString` biçimlendirilmiş zamanı içeren nesne.

### <a name="remarks"></a>Açıklamalar

Kitaplığı hata ayıklama sürümü, biçimlendirme kodlarını denetler ve kodu yukarıdaki listede değilse, onaylar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

##  <a name="getdays"></a>  CTimeSpan::GetDays

Bu tam gün sayısını gösteren bir değer döndürür `CTimeSpan`.

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Zaman aralığı içinde 24 saat tam gün sayısını döndürür. Bu değer, negatif bir zaman aralığı ise negatif olabilir.

### <a name="remarks"></a>Açıklamalar

Gün ışığından yararlanma saatine neden olabilecek bir Not `GetDays` potansiyel olarak şaşırtıcı bir sonuç döndürmek için. Örneğin, hedef olduğunda aslında `GetDays` Nisan bir günde bir saatlik olarak kısaltılır ve bu nedenle bir tam gün sayılmaz olduğundan, 29, 30, 1 Nisan ve Mayıs 1 arasındaki gün sayısını raporlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

##  <a name="gethours"></a>  CTimeSpan::GetHours

(-23-23) geçerli günün saat sayısını temsil eden bir değer döndürür.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli gün içinde saat sayısını döndürür. -23-23 aralığındadır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

##  <a name="getminutes"></a>  CTimeSpan::GetMinutes

Geçerli saatte (-59-59) dakika sayısını temsil eden bir değer döndürür.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dakika sayısı geçerli saati döndürür. -59 59 aralığındadır.

### <a name="example"></a>Örnek

Örneğin bakın [GetHours](#gethours).

##  <a name="getseconds"></a>  CTimeSpan::GetSeconds

Geçerli dakika (-59-59) saniye sayısını gösteren bir değer döndürür.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dakika içinde saniye sayısını döndürür. -59 59 aralığındadır.

### <a name="example"></a>Örnek

Örneğin bakın [GetHours](#gethours).

##  <a name="gettimespan"></a>  CTimeSpan::GetTimeSpan

Değerini döndürür `CTimeSpan` nesne.

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli değerini döndürür `CTimeSpan` nesne.

##  <a name="gettotalhours"></a>  CTimeSpan::GetTotalHours

Bu tam bir saat toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tam bir saat toplam sayısını döndürür `CTimeSpan`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

##  <a name="gettotalminutes"></a>  CTimeSpan::GetTotalMinutes

Bu tam dakika toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tam dakika toplam sayısını döndürür `CTimeSpan`.

### <a name="example"></a>Örnek

Örneğin bakın [GetTotalHours](#gettotalhours).

##  <a name="gettotalseconds"></a>  CTimeSpan::GetTotalSeconds

Bu tam saniye toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tam saniye sayısını döndürür `CTimeSpan`.

### <a name="example"></a>Örnek

Örneğin bakın [GetTotalHours](#gettotalhours).

##  <a name="operator_add_-"></a>  CTimeSpan::operator +, -

Ekler ve çıkarır `CTimeSpan` nesneleri.

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*  
Eklenecek değer `CTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

A `CTimeSpan` işleminin sonucunu temsil eden nesne.

### <a name="remarks"></a>Açıklamalar

Bu iki işleç ekleme ve çıkarmayı izin `CTimeSpan` nesneler birbirlerine gelen ve giden.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  CTimeSpan::operator +=-=

Ekler ve çıkaran bir `CTimeSpan` nesne için ve bu `CTimeSpan`.

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*  
Eklenecek değer `CTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTimeSpan` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleçler, ekleme ve çıkarmayı sağlar bir `CTimeSpan` nesne için ve bu `CTimeSpan`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

##  <a name="serialize64"></a>  CTimeSpan::Serialize64

> [!NOTE]
>  Bu yöntem yalnızca MFS projelerinde kullanılabilir.

Bir arşiv bilgisayardan veya bir üye değişkeni ile ilişkili verileri serileştirir.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*ar*  
`CArchive` Güncelleştirmek istediğiniz bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CArchive` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
[_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
[gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
[localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
[_time64 _time32, saat](../../c-runtime-library/reference/time-time32-time64.md)   
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)

