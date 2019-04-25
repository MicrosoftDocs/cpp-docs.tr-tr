---
title: Standart İletişim Kutusu Veri Doğrulama Rutinleri
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: 77b08945c99b9e9e2652a40e5710d8c4e89846b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309999"
---
# <a name="standard-dialog-data-validation-routines"></a>Standart İletişim Kutusu Veri Doğrulama Rutinleri

Bu konu, genel MFC iletişim kutusu denetimleri için kullanılan standart iletişim kutusu veri doğrulama (DDV) yordamlarını listeler.

> [!NOTE]
>  Standart iletişim kutusu veri değişimi rutinleri üstbilgi dosyası afxdd_.h içinde tanımlanır. Ancak, uygulamaları afxwin.h içermelidir.

### <a name="ddv-functions"></a>DDV işlevleri

|||
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|Verilen denetim değerindeki karakter sayısını, belirli bir maksimum değeri aşmadığını denetler.|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Verilen denetim değerini aşmayan doğrular bir verilen **bayt** aralığı.|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Belirtilen zaman aralığı verilen denetim değeri aşmadığını denetler.|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Verilen denetim değerini aşmayan doğrular bir verilen **çift** aralığı.|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Verilen denetim değerini aşmayan doğrular bir verilen **DWORD** aralığı.|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Verilen denetim değerini aşmayan doğrular bir verilen **float** aralığı.|
|[DDV_MinMaxInt](#ddv_minmaxint)|Verilen denetim değerini aşmayan doğrular bir verilen **int** aralığı.|
|[DDV_MinMaxLong](#ddv_minmaxlong)|Verilen denetim değerini aşmayan doğrular bir verilen **uzun** aralığı.|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Verilen denetim değerini aşmayan doğrular bir verilen **LONGLONG** aralığı.|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Belirli bir tarih aralığındaki verilen denetim değeri aşmadığını denetler.|
|[DDV_MinMaxShort](#ddv_minmaxshort)|Verilen denetim değerini aşmayan doğrular bir verilen **kısa** aralığı.|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Belirtilen aralık içinde verilen kaydırıcı denetimi değeri doğrular.|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Verilen denetim değerini aşmayan doğrular bir verilen **UINT** aralığı.|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|Belirtilen iki değerin arasındadır verilen denetim değeri düştüğünde doğrular.|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Verilen denetim değerini aşmayan doğrular bir verilen **ULONGLONG** aralığı.|

##  <a name="ddv_maxchars"></a>  DDV_MaxChars

Çağrı `DDV_MaxChars` denetim karakterleri miktarı ile ilişkili olduğunu doğrulamak için *değer* aşmayan *nChars*.

```
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*nChars*<br/>
İzin verilen karakter sayısı.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxbyte"></a>  DDV_MinMaxByte

Çağrı `DDV_MinMaxByte` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
İzin verilen minimum değer (bayt türünde).

*maxVal*<br/>
İzin verilen en büyük değer (bayt türünde).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxdatetime"></a>  DDV_MinMaxDateTime

Çağrı `DDV_MinMaxDateTime` saat/tarih değerini tarih ve Saat Seçici denetim doğrulamak için ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) ile ilişkili *refValue* arasında kalan *refMinRange*ve *refMaxRange*.

```
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar. Bu nesne silmeniz gerekmez.

*refValue*<br/>
Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) üye değişkeni iletişim kutusu, form görünümü veya denetim görünüm nesnesi ile ilişkilendirilmiş nesne. Bu nesne, doğrulanmak üzere verileri içerir.

*refMinRange*<br/>
En küçük tarih/saat değerine izin verilir.

*refMaxRange*<br/>
İzin verilen maksimum tarih/saat değeri.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxdouble"></a>  DDV_MinMaxDouble

Çağrı `DDV_MinMaxDouble` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
En düşük değer (tür **çift**) izin verilir.

*maxVal*<br/>
En büyük değeri (tür **çift**) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxdword"></a>  DDV_MinMaxDWord

Çağrı `DDV_MinMaxDWord` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
İzin verilen minimum değer (DWORD türünde).

*maxVal*<br/>
İzin verilen en büyük değeri (DWORD türünde).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxfloat"></a>  DDV_MinMaxFloat

Çağrı `DDV_MinMaxFloat` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
En düşük değer (tür **float**) izin verilir.

*maxVal*<br/>
En büyük değeri (tür **float**) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxint"></a>  Ddv_minmaxınt

Çağrı `DDV_MinMaxInt` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
En düşük değer (tür **int**) izin verilir.

*maxVal*<br/>
En büyük değeri (tür **int**) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxlong"></a>  DDV_MinMaxLong

Çağrı `DDV_MinMaxLong` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
En düşük değer (tür **uzun**) izin verilir.

*maxVal*<br/>
En büyük değeri (tür **uzun**) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxlonglong"></a>  DDV_MinMaxLongLong

Çağrı `DDV_MinMaxLongLong` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
İzin verilen minimum değer (LONGLONG türünde).

*maxVal*<br/>
İzin verilen en büyük değeri (LONGLONG türünde).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxmonth"></a>  DDV_MinMaxMonth

Çağrı `DDV_MinMaxMonth` saat/tarih değeri aylık takvim denetimi doğrulamak için ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) ile ilişkili *refValue* arasında kalan *refMinRange* ve *refMaxRange*.

```
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*refValue*<br/>
Türü bir nesneye başvuru `CTime` veya `COleDateTime` iletişim kutusunun üye değişkeni ile ilişkili, form görünümü veya denetim görünüm nesnesi. Bu nesne, doğrulanmak üzere verileri içerir. Bu başvuru ne zaman MFC geçişleri `DDV_MinMaxMonth` çağrılır.

*refMinRange*<br/>
En küçük tarih/saat değerine izin verilir.

*refMaxRange*<br/>
İzin verilen maksimum tarih/saat değeri.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxshort"></a>  DDV_MinMaxShort

Çağrı `DDV_MinMaxShort` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
En düşük değer (tür **kısa**) izin verilir.

*maxVal*<br/>
En büyük değeri (tür **kısa**) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxslider"></a>  DDV_MinMaxSlider

Çağrı `DDV_MinMaxSlider` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
Doğrulanacak değerine bir başvuru. Bu parametre, tutan veya kaydırıcı denetiminin geçerli parmak konumu ayarlar.

*minVal*<br/>
İzin verilen minimum değer.

*maxVal*<br/>
İzin verilen maksimum değer.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Kaydırıcı denetimleri hakkında daha fazla bilgi için bkz. [CSliderCtrl kullanma](../../mfc/using-csliderctrl.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxuint"></a>  DDV_MinMaxUInt

Çağrı `DDV_MinMaxUInt` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
İzin verilen minimum değer (UINT türünde).

*maxVal*<br/>
İzin verilen en büyük değeri (UINT türünde).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddv_minmaxulonglong"></a>  DDV_MinMaxULongLong

Çağrı `DDV_MinMaxULongLong` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

```
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
İzin verilen minimum değer (ULONGLONG türünde).

*maxVal*<br/>
İzin verilen en büyük değeri (ULONGLONG türünde).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

## <a name="ddvminmaxunsigned"></a>DDV_MinMaxUnsigned

Çağrı `DDV_MinMaxUnsigned` denetimi değeri ile ilişkili doğrulamak için *değer* arasında kalan *minVal* ve *maxVal*.

### <a name="syntax"></a>Sözdizimi

```
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri doğrulanır üye değişkeninin bir başvuru.

*minVal*<br/>
En düşük değer (tür **işaretsiz** ) izin verilir.

*maxVal*<br/>
En büyük değeri (tür **işaretsiz** ) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdd_.h

## <a name="see-also"></a>Ayrıca bkz.

[Standart İletişim Kutusu Veri Değişimi Rutinleri](standard-dialog-data-exchange-routines.md)<br/>
[Makroları ve genel öğeleri](mfc-macros-and-globals.md)<br/>
[DDX_Slider](standard-dialog-data-exchange-routines.md#ddx_slider)<br/>
[DDX_FieldSlider](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md#ddx_fieldslider)
