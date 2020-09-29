---
title: Cotadatetimespan sınıfı
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
ms.openlocfilehash: 5934a456b519d14def14018f966c7bff8206c3c4
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500130"
---
# <a name="coledatetimespan-class"></a>Cotadatetimespan sınıfı

Bir zaman aralığını göreli bir zaman temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class COleDateTimeSpan
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copadatetimespan:: Cotadatetimespan](#coledatetimespan)|Bir `COleDateTimeSpan` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotadatetimespan:: Format](#format)|Bir nesnenin biçimli dize temsilini oluşturur `COleDateTimeSpan` .|
|[Cotadatetimespan:: GetDays](#getdays)|Bu `COleDateTimeSpan` nesnenin temsil ettiği gün bölümünü döndürür.|
|[Cotadatetimespan:: Gethosta](#gethours)|Bu `COleDateTimeSpan` nesnenin temsil ettiği saat bölümünü döndürür.|
|[Cotadatetimespan:: GetMinutes](#getminutes)|Bu nesnenin gösterdiği yayılımın dakika kısmını döndürür `COleDateTimeSpan` .|
|[Cotadatetimespan:: GetSeconds](#getseconds)|Bu nesnenin gösterdiği yayılma alanının ikinci bölümünü döndürür `COleDateTimeSpan` .|
|[Cotadatetimespan:: GetStatus](#getstatus)|Bu nesnenin durumunu (geçerlilik) alır `COleDateTimeSpan` .|
|[Cotadatetimespan:: GetTotalDays](#gettotaldays)|Bu `COleDateTimeSpan` nesnenin temsil ettiği gün sayısını döndürür.|
|[Cotadatetimespan:: GetTotalHours](#gettotalhours)|Bu `COleDateTimeSpan` nesnenin temsil ettiği saat sayısını döndürür.|
|[Cotadatetimespan:: GetTotalMinutes](#gettotalminutes)|Bu `COleDateTimeSpan` nesnenin temsil ettiği dakika sayısını döndürür.|
|[Cotadatetimespan:: GetTotalSeconds](#gettotalseconds)|Bu `COleDateTimeSpan` nesnenin temsil ettiği saniye sayısını döndürür.|
|[Cotadatetimespan:: SetDateTimeSpan](#setdatetimespan)|Bu nesnenin değerini ayarlar `COleDateTimeSpan` .|
|[Cotadatetimespan:: SetStatus](#setstatus)|Bu nesnenin durumunu (geçerlilik) ayarlar `COleDateTimeSpan` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|-|-|
|[işleç +,-](#operator_add_-)|Değerler için işareti ekleyin, çıkarın ve değiştirin `COleDateTimeSpan` .|
|[işleç + =,-=](#operator_add_eq_-_eq)|`COleDateTimeSpan`Bu değerden bir değer ekleyin ve değeri çıkarın `COleDateTimeSpan` .|
|[işleç =](#operator_eq)|Bir `COleDateTimeSpan` değeri kopyalar.|
|[işleç = =, <, <=](#coledatetimespan_relational_operators)|İki `COleDateTimeSpan` değeri karşılaştırın.|
|[Double işleci](#operator_double)|Bu `COleDateTimeSpan` değeri bir değerine dönüştürür **`double`** .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cotadatetimespan:: m_span](#m_span)|**`double`** Bu nesne için temeldeki öğesini içerir `COleDateTimeSpan` .|
|[Cotadatetimespan:: m_status](#m_status)|Bu nesnenin durumunu içerir `COleDateTimeSpan` .|

## <a name="remarks"></a>Açıklamalar

`COleDateTimeSpan` taban sınıfına sahip değildir.

`COleDateTimeSpan`Gün cinsinden zaman tutar.

`COleDateTimeSpan` , yardımcı sınıfı [Copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md)ile kullanılır. `COleDateTime``DATE`OLE otomasyonunun veri türünü kapsüller. `COleDateTime` mutlak zaman değerlerini temsil eder. Tüm `COleDateTime` hesaplamalar `COleDateTimeSpan` değer içerir. Bu sınıflar arasındaki ilişki, [CTime](../../atl-mfc-shared/reference/ctime-class.md) ve [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)arasında bir değer ile benzerdir.

Ve sınıfları hakkında daha fazla bilgi için `COleDateTime` `COleDateTimeSpan` bkz. [Tarih ve Saat: Otomasyon desteği](../date-and-time.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** ATLComTime. h

## <a name="coledatetimespan-relational-operators"></a><a name="coledatetimespan_relational_operators"></a> Cotadatetimespan Ilişkisel Işleçleri

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

*Tarih yayılımı*<br/>
`COleDateTimeSpan`Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Bu işleçler iki tarih/saat yayılım değerini karşılaştırır ve koşul true ise TRUE döndürür; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Her iki işlenen de geçersiz olursa bir ATLASSERT meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

## <a name="coledatetimespancoledatetimespan"></a><a name="coledatetimespan"></a> Copadatetimespan:: Cotadatetimespan

Bir `COleDateTimeSpan` nesnesi oluşturur.

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Parametreler

*dblSpanSrc*<br/>
Yeni nesneye kopyalanacak gün sayısı `COleDateTimeSpan` .

*Ldays*, *nhours*, *nmins*, *nSaniye*<br/>
Yeni nesneye kopyalanacak gün ve saat değerlerini belirtin `COleDateTimeSpan` .

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuların hepsi `COleDateTimeSpan` , belirtilen değere başlatılan yeni nesneler oluşturur. Bu oluşturucuların her birinin kısa bir açıklaması aşağıdadır:

- **Cotadatetimespan ()** 0 ' a `COleDateTimeSpan` başlatılan bir nesne oluşturur.

- **Copadatetimespan (** `dblSpanSrc` **)** `COleDateTimeSpan` kayan noktalı değerden bir nesne oluşturur.

- **Cotadatetimespan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)** `COleDateTimeSpan` belirtilen sayısal değerlere başlatılan bir nesne oluşturur.

Yeni `COleDateTimeSpan` nesnenin durumu geçerli olarak ayarlanır.

Değerlerin sınırları hakkında daha fazla bilgi için `COleDateTimeSpan` bkz. [Tarih ve Saat: Otomasyon desteği](../date-and-time.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

## <a name="coledatetimespanformat"></a><a name="format"></a> Cotadatetimespan:: Format

Bir nesnenin biçimli dize temsilini oluşturur `COleDateTimeSpan` .

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Parametreler

*pFormat*<br/>
Biçimlendirme dizesine benzer bir biçimlendirme dizesi `printf` . Bir yüzde ( `%` ) işaretinden önce gelen biçimlendirme kodları ilgili `COleDateTimeSpan` bileşenle değiştirilmiştir. Biçimlendirme dizesindeki diğer karakterler, döndürülen dizeye değiştirilmeden kopyalanır. İçin biçimlendirme kodlarının değeri ve anlamı `Format` aşağıda listelenmiştir:

- **% H** Geçerli gündeki saat

- **% D** Geçerli saat içindeki dakika sayısı

- **% S** Geçerli dakikadaki Saniyeler

- **%%** Yüzde işareti

Yukarıda listelenen dört biçim kodu, biçimin kabul edileceği tek kodlardır.

-

*NID*<br/>
Biçim denetimi dizesinin kaynak KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

`CString`Biçimli tarih/saat aralığı değerini içeren bir.

### <a name="remarks"></a>Açıklamalar

Zaman aralığı değerinin biçimli bir gösterimini oluşturmak için bu işlevleri çağırın. Bu `COleDateTimeSpan` nesnenin durumu null ise, dönüş değeri boş bir dizedir. Durum geçersiz ise, dönüş dizesi IDS_INVALID_DATETIMESPAN dize kaynağı tarafından belirtilir.

Bu işleve ait formların kısa bir açıklaması aşağıdadır:

**Biçim (** *pformat* **)**<br/>
Bu form, ' de olduğu gibi yüzde işareti (%) ile başlayan özel biçimlendirme kodlarını içeren biçim dizesini kullanarak değeri biçimlendirir `printf` . Biçimlendirme dizesi, işleve parametre olarak geçirilir.

**Biçim (** *NID* **)**<br/>
Bu form, ' de olduğu gibi yüzde işareti (%) ile başlayan özel biçimlendirme kodlarını içeren biçim dizesini kullanarak değeri biçimlendirir `printf` . Biçimlendirme dizesi bir kaynaktır. Bu dize kaynağının KIMLIĞI parametre olarak geçirilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

## <a name="coledatetimespangetdays"></a><a name="getdays"></a> Cotadatetimespan:: GetDays

Bu tarih/saat aralığı değerinin gün kısmını alır.

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değerinin gün bölümü.

### <a name="remarks"></a>Açıklamalar

Bu işlevden döndürülen değerler yaklaşık-3.615.000 ve 3.615.000 arasında değişir.

Bir nesnenin değerini sorgulayan diğer işlevler için `COleDateTimeSpan` aşağıdaki üye işlevlere bakın:

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

## <a name="coledatetimespangethours"></a><a name="gethours"></a> Cotadatetimespan:: Gethosta

Bu tarih/saat aralığı değerinin saat kısmını alır.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değerinin saat kısmı.

### <a name="remarks"></a>Açıklamalar

Bu işlevden gelen dönüş değerleri-23 ile 23 arasında değişir.

Bir nesnenin değerini sorgulayan diğer işlevler için `COleDateTimeSpan` aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

## <a name="coledatetimespangetminutes"></a><a name="getminutes"></a> Cotadatetimespan:: GetMinutes

Bu tarih/saat aralığı değerinin dakika kısmını alır.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değerinin dakika kısmı.

### <a name="remarks"></a>Açıklamalar

Bu işlevden döndürülen değerler-59 ile 59 arasında değişir.

Bir nesnenin değerini sorgulayan diğer işlevler için `COleDateTimeSpan` aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

## <a name="coledatetimespangetseconds"></a><a name="getseconds"></a> Cotadatetimespan:: GetSeconds

Bu tarih/saat aralığı değerinin ikinci kısmını alır.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değerinin saniye kısmı.

### <a name="remarks"></a>Açıklamalar

Bu işlevden döndürülen değerler-59 ile 59 arasında değişir.

Bir nesnenin değerini sorgulayan diğer işlevler için `COleDateTimeSpan` aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

## <a name="coledatetimespangetstatus"></a><a name="getstatus"></a> Cotadatetimespan:: GetStatus

Bu nesnenin durumunu (geçerlilik) alır `COleDateTimeSpan` .

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTimeSpan` değerin durumu.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri, `DateTimeSpanStatus` sınıfı içinde tanımlanan, numaralandırılmış tür tarafından tanımlanır `COleDateTimeSpan` .

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
};
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleDateTimeSpan::valid` Bu `COleDateTimeSpan` nesnenin geçerli olduğunu gösterir.

- `COleDateTimeSpan::invalid` Bu `COleDateTimeSpan` nesnenin geçersiz olduğunu gösterir; diğer bir deyişle, değeri yanlış olabilir.

- `COleDateTimeSpan::null` Bu `COleDateTimeSpan` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlanmadığını gösterir. (Bu, C++ NULL değerinin aksine "hiçbir değer olmadan" veritabanı açısından "null" değeridir.)

Bir `COleDateTimeSpan` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Bu nesne bir aritmetik atama işlemi sırasında bir `+=` taşma veya yetersiz `-=`

- Bu nesneye geçersiz bir değer atanmışsa.

- Bu nesnenin durumu, kullanılarak açıkça geçersiz olarak ayarlandıysa `SetStatus` .

Durumu geçersiz olarak ayarlayaetkileyebilecek işlemler hakkında daha fazla bilgi için bkz. [COleDateTimeSpan:: operator +,-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) ve [COleDateTimeSpan:: operator + =,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

Değerlerin sınırları hakkında daha fazla bilgi için `COleDateTimeSpan` bkz. [Tarih ve Saat: Otomasyon desteği](../date-and-time.md).

## <a name="coledatetimespangettotaldays"></a><a name="gettotaldays"></a> Cotadatetimespan:: GetTotalDays

Gün olarak ifade edilen bu tarih/saat aralığı değerini alır.

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değeri gün olarak ifade edilir. Bu işlev bir Double döndürecek şekilde prototipi oluşturulmuş olsa da, her zaman bir tamsayı değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlevden döndürülen değerler, yaklaşık-3.65 E6 ve 3.65 E6 arasında değişir.

Bir nesnenin değerini sorgulayan diğer işlevler için `COleDateTimeSpan` aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

## <a name="coledatetimespangettotalhours"></a><a name="gettotalhours"></a> Cotadatetimespan:: GetTotalHours

Saat cinsinden ifade edilen bu tarih/saat aralığı değerini alır.

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değeri saat cinsinden ifade edilir. Bu işlev bir Double döndürecek şekilde prototipi oluşturulmuş olsa da, her zaman bir tamsayı değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlevden döndürülen değerler, yaklaşık-8.77 E7 ve 8.77 E7 arasında değişir.

Bir nesnenin değerini sorgulayan diğer işlevler için `COleDateTimeSpan` aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[GetTotalDays](#gettotaldays)örneğine bakın.

## <a name="coledatetimespangettotalminutes"></a><a name="gettotalminutes"></a> Cotadatetimespan:: GetTotalMinutes

Bu tarih/saat aralığı değerini dakika cinsinden alır.

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değeri dakikalar içinde ifade edilir. Bu işlev bir Double döndürecek şekilde prototipi oluşturulmuş olsa da, her zaman bir tamsayı değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlevden döndürülen değerler, yaklaşık-5.26 E9 ve 5.26 E9 arasında değişir.

Bir nesnenin değerini sorgulayan diğer işlevler için `COleDateTimeSpan` aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Örnek

[GetTotalDays](#gettotaldays)örneğine bakın.

## <a name="coledatetimespangettotalseconds"></a><a name="gettotalseconds"></a> Cotadatetimespan:: GetTotalSeconds

Saniye olarak ifade edilen bu tarih/saat aralığı değerini alır.

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu tarih/saat aralığı değeri saniye cinsinden ifade edilir. Bu işlev bir Double döndürecek şekilde prototipi oluşturulmuş olsa da, her zaman bir tamsayı değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlevden döndürülen değerler, yaklaşık-3.16 E11 ile 3.16 E11 arasında değişir.

Bir nesnenin değerini sorgulayan diğer işlevler için `COleDateTimeSpan` aşağıdaki üye işlevlere bakın:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

### <a name="example"></a>Örnek

[GetTotalDays](#gettotaldays)örneğine bakın.

## <a name="coledatetimespanm_span"></a><a name="m_span"></a> Cotadatetimespan:: m_span

**`double`** Bu nesnenin temel alınan değeri `COleDateTime` .

```
double m_span;
```

### <a name="remarks"></a>Açıklamalar

Bu değer, tarih/saat aralığını gün olarak ifade eder.

> [!CAUTION]
> Veri üyesinde değeri değiştirmek, **`double`** Bu nesnenin değerini değiştirecek `COleDateTimeSpan` . Bu nesnenin durumunu değiştirmez `COleDateTimeSpan` .

## <a name="coledatetimespanm_status"></a><a name="m_status"></a> Cotadatetimespan:: m_status

Bu veri üyesinin türü, `DateTimeSpanStatus` sınıfı içinde tanımlanan, numaralandırılmış türüdür `COleDateTimeSpan` .

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

- `COleDateTimeSpan::valid` Bu `COleDateTimeSpan` nesnenin geçerli olduğunu gösterir.

- `COleDateTimeSpan::invalid` Bu `COleDateTimeSpan` nesnenin geçersiz olduğunu gösterir; diğer bir deyişle, değeri yanlış olabilir.

- `COleDateTimeSpan::null` Bu `COleDateTimeSpan` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlanmadığını gösterir. (Bu, C++ NULL değerinin aksine "hiçbir değer olmadan" veritabanı açısından "null" değeridir.)

Bir `COleDateTimeSpan` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Bu nesne bir aritmetik atama işlemi sırasında bir `+=` taşma veya yetersiz `-=`

- Bu nesneye geçersiz bir değer atanmışsa.

- Bu nesnenin durumu, [SetStatus](#setstatus)kullanılarak açıkça geçersiz olarak ayarlandıysa.

Durumu geçersiz olarak ayarlayaetkileyebilecek işlemler hakkında daha fazla bilgi için bkz. [COleDateTimeSpan:: operator +,-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) ve [COleDateTimeSpan:: operator + =,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

> [!CAUTION]
> Bu veri üyesi gelişmiş programlama durumlarına yöneliktir. [GetStatus](#getstatus) ve [SetStatus](#setstatus)satır içi üye işlevlerini kullanmanız gerekir. `SetStatus`Bu veri üyesini açıkça ayarlamayla ilgili daha fazla uyarı için bkz..

Değerlerin sınırları hakkında daha fazla bilgi için `COleDateTimeSpan` bkz. [Tarih ve Saat: Otomasyon desteği](../date-and-time.md).

## <a name="coledatetimespanoperator-"></a><a name="operator_eq"></a> COleDateTimeSpan:: operator =

Bir `COleDateTimeSpan` değeri kopyalar.

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklenmiş atama işleci, kaynak tarih/saat aralığı değerini bu nesneye kopyalar `COleDateTimeSpan` .

## <a name="coledatetimespanoperator---"></a><a name="operator_add_-"></a> COleDateTimeSpan:: operator +,-

Değerler için işareti ekleyin, çıkarın ve değiştirin `COleDateTimeSpan` .

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>Açıklamalar

İlk iki operatör tarih/saat yayılım değerleri eklemenizi ve çıkartabilir. Üçüncü, tarih/saat aralığı değerinin işaretini değiştirmenize izin verir.

İşlenenden biri null ise, sonuçta elde edilen `COleDateTimeSpan` değerin durumu null olur.

İşlenenden biri geçersiz ve diğeri null değilse, sonuçta elde edilen `COleDateTimeSpan` değerin durumu geçersizdir.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

## <a name="coledatetimespanoperator---"></a><a name="operator_add_eq_-_eq"></a> COleDateTimeSpan:: operator + =,-=

`COleDateTimeSpan`Bu değerden bir değer ekleyin ve değeri çıkarın `COleDateTimeSpan` .

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleçler, bu nesneden tarih/saat yayılım değerleri eklemenizi ve çıkartabilir `COleDateTimeSpan` . İşlenenden biri null ise, sonuçta elde edilen `COleDateTimeSpan` değerin durumu null olur.

İşlenenden biri geçersiz ve diğeri null değilse, sonuçta elde edilen `COleDateTimeSpan` değerin durumu geçersizdir.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

## <a name="coledatetimespanoperator-double"></a><a name="operator_double"></a> COleDateTimeSpan:: operator double

Bu `COleDateTimeSpan` değeri bir değerine dönüştürür **`double`** .

```
operator double() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, bu `COleDateTimeSpan` değerin değerini kayan noktalı gün sayısı olarak döndürür.

## <a name="coledatetimespansetdatetimespan"></a><a name="setdatetimespan"></a> Cotadatetimespan:: SetDateTimeSpan

Bu tarih/saat aralığı değerinin değerini ayarlar.

```cpp
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Parametreler

*Ldays*, *nhours*, *nmins*, *nSaniye*<br/>
Bu nesneye kopyalanacak Tarih-span ve zaman aralığı değerlerini belirtin `COleDateTimeSpan` .

### <a name="remarks"></a>Açıklamalar

Bir nesnenin değerini sorgulayan işlevler için `COleDateTimeSpan` aşağıdaki üye işlevlere bakın:

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

## <a name="coledatetimespansetstatus"></a><a name="setstatus"></a> Cotadatetimespan:: SetStatus

Bu nesnenin durumunu (geçerlilik) ayarlar `COleDateTimeSpan` .

```cpp
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>Parametreler

*durumlarına*<br/>
Bu nesnenin yeni durum değeri `COleDateTimeSpan` .

### <a name="remarks"></a>Açıklamalar

*Durum* parametresi değeri, `DateTimeSpanStatus` sınıfı içinde tanımlanan, numaralandırılmış tür tarafından tanımlanır `COleDateTimeSpan` .

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleDateTimeSpan::valid` Bu `COleDateTimeSpan` nesnenin geçerli olduğunu gösterir.

- `COleDateTimeSpan::invalid` Bu `COleDateTimeSpan` nesnenin geçersiz olduğunu gösterir; diğer bir deyişle, değeri yanlış olabilir.

- `COleDateTimeSpan::null` Bu `COleDateTimeSpan` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlanmadığını gösterir. (Bu, C++ NULL değerinin aksine "hiçbir değer olmadan" veritabanı açısından "null" değeridir.)

   > [!CAUTION]
   > Bu işlev, gelişmiş programlama durumları içindir. Bu işlev, bu nesnedeki verileri değiştirmez. En sık, durumu **null** veya **geçersiz**olarak ayarlamak için kullanılır. Atama işlecinin ([operator =](#operator_eq)) ve [SetDateTimeSpan](#setdatetimespan) değerinin, kaynak değer (ler) temelinde nesnenin durumunu ayarlandığını unutmayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Cotadatetime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md)<br/>
[CTime sınıfı](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
