---
title: COleDateTimeSpan sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ee7ccca718a05529e5ebc88bccc7d23d258810c
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758368"
---
# <a name="coledatetimespan-class"></a>COleDateTimeSpan sınıfı

Göreli bir zaman, bir zaman aralığını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class COleDateTimeSpan
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|Oluşturur bir `COleDateTimeSpan` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDateTimeSpan::Format](#format)|Bir biçimlendirilmiş dize gösterimini oluşturur bir `COleDateTimeSpan` nesne.|
|[COleDateTimeSpan::GetDays](#getdays)|Bu aralık gün kısmını döndürür `COleDateTimeSpan` nesnesini temsil eder.|
|[COleDateTimeSpan::GetHours](#gethours)|Bu aralık saat bölümünü döndürür `COleDateTimeSpan` nesnesini temsil eder.|
|[COleDateTimeSpan::GetMinutes](#getminutes)|Bu aralık dakika kısmını döndürür `COleDateTimeSpan` nesnesini temsil eder.|
|[COleDateTimeSpan::GetSeconds](#getseconds)|Bu aralık saniye kısmını döndürür `COleDateTimeSpan` nesnesini temsil eder.|
|[COleDateTimeSpan::GetStatus](#getstatus)|Bu durum (geçerlilik) alır `COleDateTimeSpan` nesne.|
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Bu gün sayısını döndürür `COleDateTimeSpan` nesnesini temsil eder.|
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|Bu saat sayısını döndürür `COleDateTimeSpan` nesnesini temsil eder.|
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Bu dakika sayısını döndürür `COleDateTimeSpan` nesnesini temsil eder.|
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Bu saniye sayısını döndürür `COleDateTimeSpan` nesnesini temsil eder.|
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|Bu ayarlar `COleDateTimeSpan` nesne.|
|[COleDateTimeSpan::SetStatus](#setstatus)|' % S'durumunu (geçerlilik) Bu ayarlar `COleDateTimeSpan` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|||
|-|-|
|[operator +, -](#operator_add_-)|Ekleme, çıkarma ve işareti Değiştir `COleDateTimeSpan` değerleri.|
|[operator +=-=](#operator_add_eq_-_eq)|Ekleme ve çıkarmayı bir `COleDateTimeSpan` bu değerden `COleDateTimeSpan` değeri.|
|[işleç =](#operator_eq)|Kopya bir `COleDateTimeSpan` değeri.|
|[işleç ==, <, < =](#coledatetimespan_relational_operators)|Karşılaştırabilirsiniz `COleDateTimeSpan` değerleri.|
|[double işleci](#operator_double)|Bu dönüştürür `COleDateTimeSpan` değerini bir **çift**.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleDateTimeSpan::m_span](#m_span)|Arka plandaki içeren **çift** bu `COleDateTimeSpan` nesne.|
|[COleDateTimeSpan::m_status](#m_status)|Bu durumu içeren `COleDateTimeSpan` nesne.|

## <a name="remarks"></a>Açıklamalar

`COleDateTimeSpan` bir temel sınıfa sahip değil.

A `COleDateTimeSpan` süresi gün içinde tutar.

`COleDateTimeSpan` kendi yardımcı sınıf ile kullanılan [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime` kapsülleyen `DATE` OLE Otomasyonu nesnesi etkin veri türü. `COleDateTime` mutlak zaman değerleri temsil eder. Tüm `COleDateTime` içeren `COleDateTimeSpan` değerleri. Bu sınıflar arasındaki ilişki arasında bir benzer [CTime](../../atl-mfc-shared/reference/ctime-class.md) ve [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).

Daha fazla bilgi için `COleDateTime` ve `COleDateTimeSpan` sınıfları, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** ATLComTime.h

##  <a name="coledatetimespan_relational_operators"></a>  COleDateTimeSpan ilişkisel işleçleri

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

*dateSpan*  
`COleDateTimeSpan` Karşılaştırmak için.

### <a name="return-value"></a>Dönüş Değeri

Koşul true ise bu işleçler iki tarih/zaman aralığı değerleri ve dönüş doğru karşılaştırma; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  İki işlenenden geçersiz bir ATLASSERT meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

##  <a name="coledatetimespan"></a>  COleDateTimeSpan::COleDateTimeSpan

Oluşturur bir `COleDateTimeSpan` nesne.

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Parametreler

*dblSpanSrc*  
Yeni içine kopyalanacak gün sayısını `COleDateTimeSpan` nesne.

*lDays*, *nHours*, *nMins*, *nSecs*  
Yeni içine kopyalanacak gün ve saat değerleri belirtmek `COleDateTimeSpan` nesne.

### <a name="remarks"></a>Açıklamalar

Tüm bu oluşturucular Yeni Oluştur `COleDateTimeSpan` nesneleri belirtilen değerle başlatılır. Bu oluşturucular her kısa bir açıklaması aşağıdaki gibidir:

- **COleDateTimeSpan ()** oluşturan bir `COleDateTimeSpan` nesne 0 olarak başlatılır.

- **COleDateTimeSpan (** `dblSpanSrc` **)** oluşturan bir `COleDateTimeSpan` nesneden bir kayan nokta değeri.

- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)**  Oluşturur bir `COleDateTimeSpan` nesne belirtilen sayısal değerlerle başlatıldı.

Yeni durum `COleDateTimeSpan` nesne için geçerli olarak ayarlanır.

Sınırları hakkında daha fazla bilgi için `COleDateTimeSpan` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

##  <a name="format"></a>  COleDateTimeSpan::Format

Bir biçimlendirilmiş dize gösterimini oluşturur bir `COleDateTimeSpan` nesne.

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Parametreler

*pFormat*  
Bir biçimlendirme dizesi benzer `printf` biçimlendirme dizesi. Biçimlendirme kodları, öncesinde bir yüzde (`%`) oturum açın, ilgili değiştirilir `COleDateTimeSpan` bileşeni. Biçimlendirme dizesi diğer karakterler döndürülen dizeye değiştirilmeden kopyalanır. Değer ve biçimlendirme kodları anlamını `Format` aşağıda listelenmiştir:

- **%H** geçerli günün saat

- **%M** geçerli bir saatteki dakika

- **%S** geçerli dakika, saniye

- **%%** Yüzde işareti

Yukarıda listelenen dört biçimi kodları biçimi kabul edileceği yalnızca kodlarıdır.

-

*nID*  
Biçim Denetimi dizesi kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

A `CString` , biçimlendirilen tarih/zaman aralığı değeri içerir.

### <a name="remarks"></a>Açıklamalar

Arama zaman aralığı değeri biçimlendirilmiş bir temsilini oluşturmak için bu işlevleri. Varsa bu durum `COleDateTimeSpan` nesnesi null ise, dönüş değeri boş bir dizedir. Geçersiz durum ise, dize kaynağı IDS_INVALID_DATETIMESPAN dizesini belirtilir.

Bu işlev formlarını kısa bir açıklaması aşağıdaki gibidir:

**Biçimi (** *pFormat* **)**  
Bu formu yüzde (%) işareti tarafından öncelenen özel biçimlendirme kodlarını içerirse biçim dizesi kullanarak değeri olarak biçimlendirir. `printf`. Biçimlendirme dizesi, parametre olarak işleve geçirilir.

**Biçimi (** *nID* **)**  
Bu formu yüzde (%) işareti tarafından öncelenen özel biçimlendirme kodlarını içerirse biçim dizesi kullanarak değeri olarak biçimlendirir. `printf`. Biçimlendirme dizesi bir kaynaktır. Bu dize kaynak kimliği, parametre olarak geçirilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

##  <a name="getdays"></a>  COleDateTimeSpan::GetDays

Bu tarih/zaman aralığı değerinin gün kısmını alır.

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı değerinin gün kısmını.

### <a name="remarks"></a>Açıklamalar

Dönüş değerleri bu işlevi aralığında yaklaşık - 3,615,000 ve 3,615,000.

Değerini sorgulamak diğer işlevler için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

##  <a name="gethours"></a>  COleDateTimeSpan::GetHours

Bu tarih/zaman aralığı değerinin saat kısmını alır.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı değeri saat kısmı.

### <a name="remarks"></a>Açıklamalar

Bu işlev aralıktan - 23 ve 23 arasında bir dönüş değerleri.

Değerini sorgulamak diğer işlevler için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:

- [GetDays](#getdays)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

##  <a name="getminutes"></a>  COleDateTimeSpan::GetMinutes

Bu tarih/zaman aralığı değerinin dakika kısmını alır.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı değerinin dakika kısmını.

### <a name="remarks"></a>Açıklamalar

Dönüş değerleri bu işlevi aralıktan - 59 ile 59 arasında.

Değerini sorgulamak diğer işlevler için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

##  <a name="getseconds"></a>  COleDateTimeSpan::GetSeconds

Bu tarih/zaman aralığı değeri saniye kısmını alır.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı değerinin saniye kısmını.

### <a name="remarks"></a>Açıklamalar

Dönüş değerleri bu işlevi aralıktan - 59 ile 59 arasında.

Değerini sorgulamak diğer işlevler için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

##  <a name="getstatus"></a>  COleDateTimeSpan::GetStatus

Bu durum (geçerlilik) alır `COleDateTimeSpan` nesne.

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu durumu `COleDateTimeSpan` değeri.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri tarafından tanımlanan `DateTimeSpanStatus` listelenmiş içinde tanımlanan bir türü `COleDateTimeSpan` sınıfı.

```
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
};  
```

Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleDateTimeSpan::valid` Belirten bu `COleDateTimeSpan` nesne geçerlidir.

- `COleDateTimeSpan::invalid` Belirten bu `COleDateTimeSpan` Nesne geçersiz; diğer bir deyişle, değeri yanlış olabilir.

- `COleDateTimeSpan::null` Belirten bu `COleDateTimeSpan` nesnesi, null, diğer bir deyişle, bu nesne için hiçbir değer belirtilmiş. ("Null" bir "herhangi bir değer NULL C++ aksine kullanılmasının" veritabanı anlamında budur.)

Durumunu bir `COleDateTimeSpan` aşağıdaki durumlarda nesne geçersiz:

- Bu nesne bir taşma veya yetersiz gelme aritmetik atama işlemi sırasında yani karşılaştı, `+=` veya `-=`.

- Bu nesne için geçersiz bir değere atanırsa.

- Bu nesne durumunu kullanarak geçersiz açıkça ayarlandığını `SetStatus`.

Durumu için geçersiz olarak işlemleri hakkında daha fazla bilgi için bkz. [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) ve [COleDateTimeSpan::operator +=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

Sınırları hakkında daha fazla bilgi için `COleDateTimeSpan` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="gettotaldays"></a>  COleDateTimeSpan::GetTotalDays

Gün olarak ifade bu tarih/zaman aralığı değeri alır.

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı, gün cinsinden değeri. Bu işlev bir çift döndürülecek prototipli olsa da, her zaman bir Integer değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev aralığında yaklaşık - 3.65e6 ve 3.65e6 dönüş değerleri.

Değerini sorgulamak diğer işlevler için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

##  <a name="gettotalhours"></a>  COleDateTimeSpan::GetTotalHours

Saat cinsinden ifade bu tarih/zaman aralığı değeri alır.

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı değeri saat cinsinden ifade. Bu işlev bir çift döndürülecek prototipli olsa da, her zaman bir Integer değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev aralığında yaklaşık - 8.77e7 ve 8.77e7 dönüş değerleri.

Değerini sorgulamak diğer işlevler için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

Örneğin bakın [GetTotalDays](#gettotaldays).

##  <a name="gettotalminutes"></a>  COleDateTimeSpan::GetTotalMinutes

Bu tarih/zaman aralığı, dakika cinsinden ifade değeri alır.

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı dakika cinsinden değeri. Bu işlev bir çift döndürülecek prototipli olsa da, her zaman bir Integer değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev aralığında yaklaşık - 5.26e9 ve 5.26e9 dönüş değerleri.

Değerini sorgulamak diğer işlevler için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

Örneğin bakın [GetTotalDays](#gettotaldays).

##  <a name="gettotalseconds"></a>  COleDateTimeSpan::GetTotalSeconds

Bu tarih/zaman aralığı değeri saniyelerle ifade alır.

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/zaman aralığı değeri saniyelerle ifade edilir. Bu işlev bir çift döndürülecek prototipli olsa da, her zaman bir Integer değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev dönüş değerleri arasındaki aralığı yaklaşık - 3.16e11 için 3.16e11.

Değerini sorgulamak diğer işlevler için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

### <a name="example"></a>Örnek

Örneğin bakın [GetTotalDays](#gettotaldays).

##  <a name="m_span"></a>  COleDateTimeSpan::m_span

Arka plandaki **çift** bu değeri `COleDateTime` nesne.

```
double m_span;
```

### <a name="remarks"></a>Açıklamalar

Bu değer, tarih/zaman aralığı gün cinsinden ifade eder.

> [!CAUTION]
>  Değer değiştirme **çift** veri üyesi, bu değeri değiştirir `COleDateTimeSpan` nesne. Bu durumu değiştirmez `COleDateTimeSpan` nesne.

##  <a name="m_status"></a>  COleDateTimeSpan::m_status

Bu veri üyesi için enum türü türüdür `DateTimeSpanStatus`, içinde tanımlanan `COleDateTimeSpan` sınıfı.

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

Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleDateTimeSpan::valid` Belirten bu `COleDateTimeSpan` nesne geçerlidir.

- `COleDateTimeSpan::invalid` Belirten bu `COleDateTimeSpan` Nesne geçersiz; diğer bir deyişle, değeri yanlış olabilir.

- `COleDateTimeSpan::null` Belirten bu `COleDateTimeSpan` nesnesi, null, diğer bir deyişle, bu nesne için hiçbir değer belirtilmiş. ("Null" bir "herhangi bir değer NULL C++ aksine kullanılmasının" veritabanı anlamında budur.)

Durumunu bir `COleDateTimeSpan` aşağıdaki durumlarda nesne geçersiz:

- Bu nesne bir taşma veya yetersiz gelme aritmetik atama işlemi sırasında yani karşılaştı, `+=` veya `-=`.

- Bu nesne için geçersiz bir değere atanırsa.

- Bu nesne durumunu kullanarak geçersiz açıkça ayarlandığını [SetStatus](#setstatus).

Durumu için geçersiz olarak işlemleri hakkında daha fazla bilgi için bkz. [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) ve [COleDateTimeSpan::operator +=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

> [!CAUTION]
>  Gelişmiş programlama durumlar için bu verileri üyesidir. Satır içi üye işlevleri kullanmalıdır [GetStatus](#getstatus) ve [SetStatus](#setstatus). Bkz: `SetStatus` açıkça bu veri üyesi ayarlama ile ilgili daha fazla uyarılar için.

Sınırları hakkında daha fazla bilgi için `COleDateTimeSpan` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_eq"></a>  COleDateTimeSpan::operator =

Kopya bir `COleDateTimeSpan` değeri.

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklenmiş atama işleci kaynak tarih/zaman aralığı değeri bu kopyalar `COleDateTimeSpan` nesne.

##  <a name="operator_add_-"></a>  COleDateTimeSpan::operator +, -

Ekleme, çıkarma ve işareti Değiştir `COleDateTimeSpan` değerleri.

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>Açıklamalar

İlk iki işleç ekleyin ve tarih/zaman aralığı değerleri çıkarmayı sağlar. Üçüncü bir tarih/zaman aralığı değerinin oturum değiştirmenize olanak tanır.

İşlenenler biri geçerli olduğunda null, ortaya çıkan durumunu `COleDateTimeSpan` değeri NULL'dur.

İşlenenden ya da geçersiz ve diğerini null değilse ortaya çıkan durumu `COleDateTimeSpan` değeri geçersiz.

Geçerli, geçersiz ve boş durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  COleDateTimeSpan::operator +=-=

Ekleme ve çıkarmayı bir `COleDateTimeSpan` bu değerden `COleDateTimeSpan` değeri.

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleçler, ekleme ve bu tarih/zaman aralığı değerleri çıkarmayı sağlar `COleDateTimeSpan` nesne. İşlenenler biri geçerli olduğunda null, ortaya çıkan durumunu `COleDateTimeSpan` değeri NULL'dur.

İşlenenden ya da geçersiz ve diğerini null değilse ortaya çıkan durumu `COleDateTimeSpan` değeri geçersiz.

Geçerli, geçersiz ve boş durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

##  <a name="operator_double"></a>  COleDateTimeSpan::operator çift

Bu dönüştürür `COleDateTimeSpan` değerini bir **çift**.

```
operator double() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç bu değeri döndürür `COleDateTimeSpan` bir kayan nokta gün sayısı olarak değeri.

##  <a name="setdatetimespan"></a>  COleDateTimeSpan::SetDateTimeSpan

Bu tarih/zaman aralığı değeri ayarlar.

```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Parametreler

*lDays*, *nHours*, *nMins*, *nSecs*  
Bu kopyalanacak tarih aralığı ve zaman aralığı değerleri gösterir `COleDateTimeSpan` nesne.

### <a name="remarks"></a>Açıklamalar

Değeri, sorgu işlevleri için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]

##  <a name="setstatus"></a>  COleDateTimeSpan::SetStatus

' % S'durumunu (geçerlilik) Bu ayarlar `COleDateTimeSpan` nesne.

```
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>Parametreler

*Durumu*  
Bu yeni durum değeri `COleDateTimeSpan` nesne.

### <a name="remarks"></a>Açıklamalar

*Durumu* parametre değeri tarafından tanımlanan `DateTimeSpanStatus` listelenmiş içinde tanımlanan bir türü `COleDateTimeSpan` sınıfı.

```
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```

Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleDateTimeSpan::valid` Belirten bu `COleDateTimeSpan` nesne geçerlidir.

- `COleDateTimeSpan::invalid` Belirten bu `COleDateTimeSpan` Nesne geçersiz; diğer bir deyişle, değeri yanlış olabilir.

- `COleDateTimeSpan::null` Belirten bu `COleDateTimeSpan` nesnesi, null, diğer bir deyişle, bu nesne için hiçbir değer belirtilmiş. ("Null" bir "herhangi bir değer NULL C++ aksine kullanılmasının" veritabanı anlamında budur.)

   > [!CAUTION]
   > Bu işlev, Gelişmiş programlama durumlar için kullanılır. Bu işlev, bu nesne verileri değiştirmez. Durumu ayarlamak için en sık kullanılacak **null** veya **geçersiz**. Unutmayın atama işleci ( [işleç =](#eq)) ve [SetDateTimeSpan](#setdatetimespan) kaynak değerleri üzerinde temel bir nesnenin durumu ayarlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md)   
[CTime sınıfı](../../atl-mfc-shared/reference/ctime-class.md)   
[CTimeSpan sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)   
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)

