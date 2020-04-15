---
title: COleDateTimeSpan Sınıfı
ms.date: 03/27/2019
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
ms.openlocfilehash: 7173fa0b6261ea718a02d399d944a1b5bb98b9f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317736"
---
# <a name="coledatetimespan-class"></a>COleDateTimeSpan Sınıfı

Göreceli bir zamanı, bir zaman aralığını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class COleDateTimeSpan
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|Bir `COleDateTimeSpan` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDateTimeSpan::Biçim](#format)|Nesnenin biçimlendirilmiş dize `COleDateTimeSpan` temsilini oluşturur.|
|[COleDateTimeSpan::GetDays](#getdays)|Bu `COleDateTimeSpan` nesnenin temsil edilen yayılma alanının gün kısmını döndürür.|
|[COleDateTimeSpan::GetHours](#gethours)|Bu `COleDateTimeSpan` nesnenin temsil edilen açıklığı saat kısmını döndürür.|
|[COleDateTimeSpan::GetMinutes](#getminutes)|Bu `COleDateTimeSpan` nesnenin temsil edilen yayılma alanının dakika kısmını döndürür.|
|[COleDateTimeSpan::GetSeconds](#getseconds)|Bu `COleDateTimeSpan` nesnenin temsil edilen açıklığı ikinci bölümünü döndürür.|
|[COleDateTimeSpan::GetStatus](#getstatus)|Bu `COleDateTimeSpan` nesnenin durumunu (geçerliliğini) alır.|
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Bu `COleDateTimeSpan` nesnenin temsil edilen gün sayısını döndürür.|
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|Bu `COleDateTimeSpan` nesnenin temsil edilen saat sayısını döndürür.|
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Bu `COleDateTimeSpan` nesnenin temsil eden dakika sayısını döndürür.|
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Bu `COleDateTimeSpan` nesnenin temsil eden saniye sayısını döndürür.|
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|Bu `COleDateTimeSpan` nesnenin değerini ayarlar.|
|[COleDateTimeSpan::SetStatus](#setstatus)|Bu `COleDateTimeSpan` nesnenin durumunu (geçerliliğini) ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|||
|-|-|
|[işleç +, -](#operator_add_-)|Değerler için `COleDateTimeSpan` işareti ekleyin, çıkarın ve değiştirin.|
|[işleç +=, -=](#operator_add_eq_-_eq)|Bu `COleDateTimeSpan` değerden `COleDateTimeSpan` bir değer ekleyin ve çıkarın.|
|[işleç =](#operator_eq)|Bir `COleDateTimeSpan` değeri kopyalar.|
|[işleç ==, <, <=](#coledatetimespan_relational_operators)|İki `COleDateTimeSpan` değeri karşılaştırın.|
|[operatör çift](#operator_double)|Bu `COleDateTimeSpan` değeri bir **çifte**dönüştürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleDateTimeSpan::m_span](#m_span)|Bu `COleDateTimeSpan` nesne için altta yatan **çift** içerir.|
|[COleDateTimeSpan::m_status](#m_status)|Bu `COleDateTimeSpan` nesnenin durumunu içerir.|

## <a name="remarks"></a>Açıklamalar

`COleDateTimeSpan`taban sınıfa sahip değildir.

Günlerdir `COleDateTimeSpan` vakit geçiriyor.

`COleDateTimeSpan`onun arkadaşı sınıf [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)ile kullanılır. `COleDateTime`OLE otomasyonunun `DATE` veri türünü kapsüller. `COleDateTime`mutlak zaman değerlerini temsil eder. Tüm `COleDateTime` hesaplamalar değerleri içerir. `COleDateTimeSpan` Bu sınıflar arasındaki ilişki CTime ve [CTimeSpan](../../atl-mfc-shared/reference/ctime-class.md) arasındaki ilişkiye benzer. [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)

Sınıflar ve sınıflar `COleDateTimeSpan` hakkında daha fazla bilgi için Tarih ve [Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın. `COleDateTime`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ATLComTime.h

## <a name="coledatetimespan-relational-operators"></a><a name="coledatetimespan_relational_operators"></a>COleDateTimeSpan İlişkisel Operatörler

Karşılaştırma işleçleri.

```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```

### <a name="parameters"></a>Parametreler

*tarihSpan*<br/>
Karşılaştırmak `COleDateTimeSpan` için.

### <a name="return-value"></a>Dönüş Değeri

Bu işleçler iki tarih/zaman aralığı değerlerini karşılaştırır ve koşul doğruysa TRUE döndürür; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Operand geçersiz se, bir ATLASSERT oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

## <a name="coledatetimespancoledatetimespan"></a><a name="coledatetimespan"></a>COleDateTimeSpan::COleDateTimeSpan

Bir `COleDateTimeSpan` nesne inşa eder.

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Parametreler

*dblSpanSrc*<br/>
Yeni `COleDateTimeSpan` nesneye kopyalanacak gün sayısı.

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
Yeni `COleDateTimeSpan` nesneye kopyalanacak gün ve saat değerlerini belirtin.

### <a name="remarks"></a>Açıklamalar

Tüm bu kurucular, `COleDateTimeSpan` belirtilen değere başlalanan yeni nesneler oluşturur. Bu yapıcıların her birinin kısa bir açıklaması aşağıdaki gibidir:

- **COleDateTimeSpan( )** 0'a `COleDateTimeSpan` başlatılaştırılan bir nesne yi oluşturuyor.

- **COleDateTimeSpan(** `dblSpanSrc` **)** Kayan `COleDateTimeSpan` nokta değerinden bir nesne inşa eder.

- **COleDateTimeSpan(** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)** Belirtilen sayısal `COleDateTimeSpan` değerlere başlan bir nesne yi kurar.

Yeni `COleDateTimeSpan` nesnenin durumu geçerli olarak ayarlanır.

Değerler için sınırlar hakkında `COleDateTimeSpan` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

## <a name="coledatetimespanformat"></a><a name="format"></a>COleDateTimeSpan::Biçim

Nesnenin biçimlendirilmiş dize `COleDateTimeSpan` temsilini oluşturur.

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Parametreler

*pFormat*<br/>
Biçimlendirme dizesine `printf` benzer bir biçimlendirme dizesi. Bir yüzde ( )`%`işaretinden önce biçimlendirme kodları ilgili `COleDateTimeSpan` bileşen tarafından değiştirilir. Biçimlendirme dizesindeki diğer karakterler döndürülen dize değişmeden kopyalanır. Biçimlendirme kodlarının `Format` değeri ve anlamı aşağıda listelenmiştir:

- **%H** Geçerli gündeki saatler

- **%M** Geçerli saatteki dakikalar

- **%S** Geçerli dakikadaki saniyeler

- **%%** Yüzde işareti

Yukarıda listelenen dört biçim kodu, Biçim'in kabul edeceği tek kodlardır.

-

*Nıd*<br/>
Biçim denetimi dizesi için kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilmiş tarih/zaman aralığı değerini içeren a. `CString`

### <a name="remarks"></a>Açıklamalar

Zaman aralığı değerinin biçimlendirilmiş bir gösterimi oluşturmak için bu işlevleri çağırın. Bu `COleDateTimeSpan` nesnenin durumu null ise, döndürme değeri boş bir dize. Durum geçersizse, iade dizesi dize kaynak IDS_INVALID_DATETIMESPAN tarafından belirtilir.

Bu işlev için formların kısa bir açıklaması aşağıdaki gibidir:

**Biçim(pFormat** *pFormat* **)**<br/>
Bu form, 'de olduğu gibi, yüzde işareti (%) öncesinde özel biçimlendirme kodları `printf`içeren biçimlendirme dizesini kullanarak değeri biçimlendirmektedir. Biçimlendirme dizesi işleve parametre olarak geçirilir.

**Biçim(nID** *nID* **)**<br/>
Bu form, 'de olduğu gibi, yüzde işareti (%) öncesinde özel biçimlendirme kodları `printf`içeren biçimlendirme dizesini kullanarak değeri biçimlendirmektedir. Biçimlendirme dizesi bir kaynaktır. Bu dize kaynağının kimliği parametre olarak geçirilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

## <a name="coledatetimespangetdays"></a><a name="getdays"></a>COleDateTimeSpan::GetDays

Bu tarih/zaman aralığı değerinin gün kısmını alır.

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı değerinin gün bölümü.

### <a name="remarks"></a>Açıklamalar

Bu işlevden gelen dönüş değerleri yaklaşık 3.615.000 ile 3.615.000 arasında değişir.

Nesnenin `COleDateTimeSpan` değerini sorgulayan diğer işlevler için aşağıdaki üye işlevlere bakın:

- [Çalışma Saatleri](#gethours)

- [Dakikaları Alır](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [Toplam Saat Sayısı](#gettotalhours)

- [Toplam Dakika Sayısı](#gettotalminutes)

- [Toplam Saniye leri elde edin](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

## <a name="coledatetimespangethours"></a><a name="gethours"></a>COleDateTimeSpan::GetHours

Bu tarih/zaman aralığı değerinin saat kısmını alır.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı değerinin saat kısmı.

### <a name="remarks"></a>Açıklamalar

Bu işlevden gelen dönüş değerleri - 23 ve 23 arasında değişir.

Nesnenin `COleDateTimeSpan` değerini sorgulayan diğer işlevler için aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [Dakikaları Alır](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [Toplam Saat Sayısı](#gettotalhours)

- [Toplam Dakika Sayısı](#gettotalminutes)

- [Toplam Saniye leri elde edin](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

## <a name="coledatetimespangetminutes"></a><a name="getminutes"></a>COleDateTimeSpan::GetMinutes

Bu tarih/zaman aralığı değerinin dakika kısmını alır.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı değerinin dakika bölümü.

### <a name="remarks"></a>Açıklamalar

Bu işlevden gelen dönüş değerleri - 59 ve 59 arasında değişir.

Nesnenin `COleDateTimeSpan` değerini sorgulayan diğer işlevler için aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [Çalışma Saatleri](#gethours)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [Toplam Saat Sayısı](#gettotalhours)

- [Toplam Dakika Sayısı](#gettotalminutes)

- [Toplam Saniye leri elde edin](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

## <a name="coledatetimespangetseconds"></a><a name="getseconds"></a>COleDateTimeSpan::GetSeconds

Bu tarih/zaman aralığı değerinin ikinci bölümünü alır.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı değerinin saniye bölümü.

### <a name="remarks"></a>Açıklamalar

Bu işlevden gelen dönüş değerleri - 59 ve 59 arasında değişir.

Nesnenin `COleDateTimeSpan` değerini sorgulayan diğer işlevler için aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [Çalışma Saatleri](#gethours)

- [Dakikaları Alır](#getminutes)

- [GetTotalDays](#gettotaldays)

- [Toplam Saat Sayısı](#gettotalhours)

- [Toplam Dakika Sayısı](#gettotalminutes)

- [Toplam Saniye leri elde edin](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

## <a name="coledatetimespangetstatus"></a><a name="getstatus"></a>COleDateTimeSpan::GetStatus

Bu `COleDateTimeSpan` nesnenin durumunu (geçerliliğini) alır.

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTimeSpan` değerin durumu.

### <a name="remarks"></a>Açıklamalar

İade değeri, `DateTimeSpanStatus` `COleDateTimeSpan` sınıf içinde tanımlanan numaralandırılmış türtarafından tanımlanır.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
};
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleDateTimeSpan::valid`Bu `COleDateTimeSpan` nesnenin geçerli olduğunu gösterir.

- `COleDateTimeSpan::invalid`Bu `COleDateTimeSpan` nesnenin geçersiz olduğunu gösterir; diğer bir gerçek, değeri yanlış olabilir.

- `COleDateTimeSpan::null`Bu `COleDateTimeSpan` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlandığını gösterir. (Bu, C++ NULL'un aksine veritabanında "değer sahibi olma" anlamında "null"dur.)

Bir `COleDateTimeSpan` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Bu nesne bir aritmetik atama işlemi sırasında bir taşma `+=` veya `-=`taşma yaşadıysa, yani .

- Bu nesneye geçersiz bir değer atandıysa.

- Bu nesnenin durumu açıkça kullanılarak `SetStatus`geçersiz olarak ayarlanmışsa.

Durumu geçersiz olarak ayarlayabilen işlemler hakkında daha fazla bilgi için [Bkz. COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) ve [COleDateTimeSpan::operator +=, -=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

Değerler için sınırlar hakkında `COleDateTimeSpan` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

## <a name="coledatetimespangettotaldays"></a><a name="gettotaldays"></a>COleDateTimeSpan::GetTotalDays

Gün cinsinden ifade edilen bu tarih/zaman aralığı değerini alır.

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Gün cinsinden ifade edilen bu tarih/saat aralığı değeri. Bu işlev bir çift döndürmek için prototip olsa da, her zaman bir tamsayı değeri döndürecektir.

### <a name="remarks"></a>Açıklamalar

Bu işlevden gelen dönüş değerleri yaklaşık 3.65e6 ve 3.65e6 arasında değişir.

Nesnenin `COleDateTimeSpan` değerini sorgulayan diğer işlevler için aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [Çalışma Saatleri](#gethours)

- [Dakikaları Alır](#getminutes)

- [GetSeconds](#getseconds)

- [Toplam Saat Sayısı](#gettotalhours)

- [Toplam Dakika Sayısı](#gettotalminutes)

- [Toplam Saniye leri elde edin](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

## <a name="coledatetimespangettotalhours"></a><a name="gettotalhours"></a>COleDateTimeSpan::GetTotalHours

Saat cinsinden ifade edilen bu tarih/zaman aralığı değerini alır.

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değeri saat cinsinden ifade edilir. Bu işlev bir çift döndürmek için prototip olsa da, her zaman bir tamsayı değeri döndürecektir.

### <a name="remarks"></a>Açıklamalar

Bu işlevden gelen dönüş değerleri yaklaşık 8.77e7 ve 8.77e7 arasında değişir.

Nesnenin `COleDateTimeSpan` değerini sorgulayan diğer işlevler için aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [Çalışma Saatleri](#gethours)

- [Dakikaları Alır](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [Toplam Dakika Sayısı](#gettotalminutes)

- [Toplam Saniye leri elde edin](#gettotalseconds)

### <a name="example"></a>Örnek

[GetTotalDays](#gettotaldays)için örneğe bakın.

## <a name="coledatetimespangettotalminutes"></a><a name="gettotalminutes"></a>COleDateTimeSpan::GetTotalMinutes

Dakika cinsinden ifade edilen bu tarih/zaman aralığı değerini alır.

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değeri dakika cinsinden ifade edilir. Bu işlev bir çift döndürmek için prototip olsa da, her zaman bir tamsayı değeri döndürecektir.

### <a name="remarks"></a>Açıklamalar

Bu işlevden gelen dönüş değerleri yaklaşık 5.26e9 ile 5.26e9 arasında değişir.

Nesnenin `COleDateTimeSpan` değerini sorgulayan diğer işlevler için aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [Çalışma Saatleri](#gethours)

- [Dakikaları Alır](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [Toplam Saat Sayısı](#gettotalhours)

- [Toplam Saniye leri elde edin](#gettotalseconds)

### <a name="example"></a>Örnek

[GetTotalDays](#gettotaldays)için örneğe bakın.

## <a name="coledatetimespangettotalseconds"></a><a name="gettotalseconds"></a>COleDateTimeSpan::GetTotalSeconds

Saniye cinsinden ifade edilen bu tarih/zaman aralığı değerini alır.

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değeri saniye cinsinden ifade edilir. Bu işlev bir çift döndürmek için prototip olsa da, her zaman bir tamsayı değeri döndürecektir.

### <a name="remarks"></a>Açıklamalar

Bu işlevden gelen dönüş değerleri yaklaşık - 3.16e11 ile 3.16e11 arasında değişir.

Nesnenin `COleDateTimeSpan` değerini sorgulayan diğer işlevler için aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [Çalışma Saatleri](#gethours)

- [Dakikaları Alır](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [Toplam Saat Sayısı](#gettotalhours)

- [Toplam Dakika Sayısı](#gettotalminutes)

### <a name="example"></a>Örnek

[GetTotalDays](#gettotaldays)için örneğe bakın.

## <a name="coledatetimespanm_span"></a><a name="m_span"></a>COleDateTimeSpan::m_span

Bu `COleDateTime` nesne için temel **çift** değer.

```
double m_span;
```

### <a name="remarks"></a>Açıklamalar

Bu değer, gün içinde tarih/saat aralığını ifade eder.

> [!CAUTION]
> **Çift** veri üyesindeki değeri değiştirmek bu `COleDateTimeSpan` nesnenin değerini değiştirir. Bu `COleDateTimeSpan` nesnenin durumunu değiştirmez.

## <a name="coledatetimespanm_status"></a><a name="m_status"></a>COleDateTimeSpan::m_status

Bu veri üyesinin türü, `DateTimeSpanStatus` `COleDateTimeSpan` sınıf içinde tanımlanan numaralandırılmış türüdür.

```
DateTimeSpanStatus m_status;
```

### <a name="remarks"></a>Açıklamalar

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleDateTimeSpan::valid`Bu `COleDateTimeSpan` nesnenin geçerli olduğunu gösterir.

- `COleDateTimeSpan::invalid`Bu `COleDateTimeSpan` nesnenin geçersiz olduğunu gösterir; diğer bir gerçek, değeri yanlış olabilir.

- `COleDateTimeSpan::null`Bu `COleDateTimeSpan` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlandığını gösterir. (Bu, C++ NULL'un aksine veritabanında "değer sahibi olma" anlamında "null"dur.)

Bir `COleDateTimeSpan` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Bu nesne bir aritmetik atama işlemi sırasında bir taşma `+=` veya `-=`taşma yaşadıysa, yani .

- Bu nesneye geçersiz bir değer atandıysa.

- Bu nesnenin durumu [SetStatus](#setstatus)kullanarak açıkça geçersiz olarak ayarlanmışsa.

Durumu geçersiz olarak ayarlayabilen işlemler hakkında daha fazla bilgi için [Bkz. COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) ve [COleDateTimeSpan::operator +=, -=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

> [!CAUTION]
> Bu veri üyesi gelişmiş programlama durumları içindir. Sıralı üye işlevleri kullanmalısınız [GetStatus](#getstatus) ve [SetStatus](#setstatus). Bu `SetStatus` veri üyesinin açıkça ayarlanmasıyla ilgili daha fazla uyarı için bkz.

Değerler için sınırlar hakkında `COleDateTimeSpan` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

## <a name="coledatetimespanoperator-"></a><a name="operator_eq"></a>COleDateTimeSpan::operatör =

Bir `COleDateTimeSpan` değeri kopyalar.

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklenen atama işleci, kaynak tarih/saat `COleDateTimeSpan` aralığı değerini bu nesneye kopyalar.

## <a name="coledatetimespanoperator---"></a><a name="operator_add_-"></a>COleDateTimeSpan::operatör +, -

Değerler için `COleDateTimeSpan` işareti ekleyin, çıkarın ve değiştirin.

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>Açıklamalar

İlk iki işleç, tarih/zaman aralığı değerlerini eklemenize ve çıkarmanıza izin verir. Üçüncü tarih/ zaman aralığı değeri işaretini değiştirmenizi sağlar.

Operandlardan biri null ise, elde edilen `COleDateTimeSpan` değerin durumu null'dur.

Operand'lardan biri geçersizse ve diğeri null değilse, elde edilen `COleDateTimeSpan` değerin durumu geçersizdir.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

## <a name="coledatetimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>COleDateTimeSpan::operatör +=, -=

Bu `COleDateTimeSpan` değerden `COleDateTimeSpan` bir değer ekleyin ve çıkarın.

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleçler, tarih/saat aralığı değerlerini bu `COleDateTimeSpan` nesneden eklemenize ve çıkarmanıza izin verir. Operandlardan biri null ise, elde edilen `COleDateTimeSpan` değerin durumu null'dur.

Operand'lardan biri geçersizse ve diğeri null değilse, elde edilen `COleDateTimeSpan` değerin durumu geçersizdir.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

## <a name="coledatetimespanoperator-double"></a><a name="operator_double"></a>COleDateTimeSpan::operatör çift

Bu `COleDateTimeSpan` değeri bir **çifte**dönüştürür.

```
operator double() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, bu `COleDateTimeSpan` değerin değerini kayan nokta sayısı olarak döndürür.

## <a name="coledatetimespansetdatetimespan"></a><a name="setdatetimespan"></a>COleDateTimeSpan::SetDateTimeSpan

Bu tarih/zaman aralığı değerinin değerini ayarlar.

```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Parametreler

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
Bu `COleDateTimeSpan` nesneye kopyalanacak tarih aralığı ve zaman aralığı değerlerini belirtin.

### <a name="remarks"></a>Açıklamalar

Nesnenin `COleDateTimeSpan` değerini sorgulayan işlevler için aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [Çalışma Saatleri](#gethours)

- [Dakikaları Alır](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [Toplam Saat Sayısı](#gettotalhours)

- [Toplam Dakika Sayısı](#gettotalminutes)

- [Toplam Saniye leri elde edin](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]

## <a name="coledatetimespansetstatus"></a><a name="setstatus"></a>COleDateTimeSpan::SetStatus

Bu `COleDateTimeSpan` nesnenin durumunu (geçerliliğini) ayarlar.

```
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>Parametreler

*Durum*<br/>
Bu `COleDateTimeSpan` nesne için yeni durum değeri.

### <a name="remarks"></a>Açıklamalar

*Durum* parametre değeri, `DateTimeSpanStatus` `COleDateTimeSpan` sınıf içinde tanımlanan numaralandırılmış türtarafından tanımlanır.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleDateTimeSpan::valid`Bu `COleDateTimeSpan` nesnenin geçerli olduğunu gösterir.

- `COleDateTimeSpan::invalid`Bu `COleDateTimeSpan` nesnenin geçersiz olduğunu gösterir; diğer bir gerçek, değeri yanlış olabilir.

- `COleDateTimeSpan::null`Bu `COleDateTimeSpan` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlandığını gösterir. (Bu, C++ NULL'un aksine veritabanında "değer sahibi olma" anlamında "null"dur.)

   > [!CAUTION]
   > Bu işlev gelişmiş programlama durumları içindir. Bu işlev, bu nesnedeki verileri değiştirmez. Genellikle durumu **geçersiz** veya **geçersiz**olarak ayarlamak için kullanılır. Atama işlecinin ([işleç =](#operator_eq)) ve [SetDateTimeSpan'ın](#setdatetimespan) nesnenin durumunu kaynak değeri(ler)e göre ayarladığını unutmayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[COleDateTime Sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md)<br/>
[CTime Sınıfı](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan Sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
