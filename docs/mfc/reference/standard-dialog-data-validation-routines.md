---
title: Standart İletişim Kutusu Veri Doğrulama Rutinleri
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: 83e3e215ec8d66321bbac5a4a308b04ef69dc68c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372898"
---
# <a name="standard-dialog-data-validation-routines"></a>Standart İletişim Kutusu Veri Doğrulama Rutinleri

Bu konu, ortak MFC iletişim denetimleri için kullanılan standart iletişim veri doğrulama (DDV) yordamlarını listeler.

> [!NOTE]
> Standart iletişim veri alışverişi yordamları afxdd_.h. üstbilgi dosyasında tanımlanır. Ancak, uygulamalar afxwin.h içermelidir.

### <a name="ddv-functions"></a>DDV Fonksiyonları

|||
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|Belirli bir denetim değerindeki karakter sayısının belirli bir maksimumu aşmadığını doğrular.|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Verilen bir denetim değerinin belirli bir **BYTE** aralığını aşmadığını doğrular.|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Verilen denetim değerinin belirli bir zaman aralığını aşmadığını doğrular.|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Verilen denetim değerinin belirli bir **çift** aralığı aşmadığını doğrular.|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Belirli bir denetim değerinin belirli bir **DWORD** aralığını aşmadığını doğrular.|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Verilen denetim değerinin belirli bir **float** aralığını aşmadığını doğrular.|
|[DDV_MinMaxInt](#ddv_minmaxint)|Verilen denetim değerinin belirli bir **int** aralığını aşmadığını doğrular.|
|[DDV_MinMaxLong](#ddv_minmaxlong)|Verilen denetim değerinin belirli bir **uzun** aralığı aşmadığını doğrular.|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Verilen bir denetim değerinin belirli bir **UZUN aralığı** aşmadığını doğrular.|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Verilen denetim değerinin belirli bir tarih aralığını aşmadığını doğrular.|
|[DDV_MinMaxShort](#ddv_minmaxshort)|Verilen denetim değerinin belirli bir **kısa** aralığı aşmadığını doğrular.|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Belirli bir kaydırıcı denetim değerinin verilen aralıkta düştüğünü doğrular.|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Verilen bir denetim değerinin belirli bir **UINT** aralığını aşmadığını doğrular.|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|Verilen denetim değerinin iki belirtilen değer arasında düştüğünü doğrular.|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Verilen bir denetim değerinin belirli bir **ULONGLONG** aralığını aşmadığını doğrular.|

## <a name="ddv_maxchars"></a><a name="ddv_maxchars"></a>DDV_MaxChars

`DDV_MaxChars` *Değerle* ilişkili denetimdeki karakter miktarının *nChars'ı*aşmadığını doğrulamak için arayın.

```cpp
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*nChars*<br/>
İzin verilen maksimum karakter sayısı.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxbyte"></a><a name="ddv_minmaxbyte"></a>DDV_MinMaxByte

`DDV_MinMaxByte` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
İzin verilen minimum değer (BYTE türünden).

*Maxval*<br/>
Maksimum değer (byTE türü) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxdatetime"></a><a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime

*RefValue* ile ilişkili tarih ve saat seçici [kontrolündeki](../../mfc/reference/cdatetimectrl-class.md)saat/tarih değerinin *refMinRange* ve *refMaxRange*arasında düştüğünü doğrulamak için arayın. `DDV_MinMaxDateTime`

```cpp
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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar. Bu nesneyi silmeniz gerekmez.

*refValue*<br/>
İletişim kutusunun, form görünümünün veya denetim görünümü nesnesinin üye değişkeniyle ilişkili bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine yapılan başvuru. Bu nesne doğrulanacak verileri içerir.

*refMinRange*<br/>
İzin verilen minimum tarih/saat değeri.

*refMaxRange*<br/>
İzin verilen maksimum tarih/saat değeri.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxdouble"></a><a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble

`DDV_MinMaxDouble` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
İzin verilen minimum değer **(çift**tip).

*Maxval*<br/>
Maksimum değer **(tip çift)** izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxdword"></a><a name="ddv_minmaxdword"></a>DDV_MinMaxDWord

`DDV_MinMaxDWord` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
İzin verilen minimum değer (DWORD türünden).

*Maxval*<br/>
Maksimum değer (DWORD türü) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxfloat"></a><a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat

`DDV_MinMaxFloat` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
İzin verilen minimum değer (tür **float)**

*Maxval*<br/>
Maksimum değer (tür **float)** izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxint"></a><a name="ddv_minmaxint"></a>DDV_MinMaxInt

`DDV_MinMaxInt` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
Minimum değer (tür **int)** izin verilir.

*Maxval*<br/>
Maksimum değer (tür **int)** izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxlong"></a><a name="ddv_minmaxlong"></a>DDV_MinMaxLong

`DDV_MinMaxLong` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
İzin verilen minimum değer **(uzun**tür)

*Maxval*<br/>
Maksimum değer **(uzun**tür) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxlonglong"></a><a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong

`DDV_MinMaxLongLong` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
Minimum değer (longlong türü) izin verilir.

*Maxval*<br/>
Maksimum değer (longlong türü) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxmonth"></a><a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth

RefValue ile ilişkili ay takvim [kontrolündeki](../../mfc/reference/cmonthcalctrl-class.md)saat/tarih değerinin *refMinRange* ve *refMaxRange*arasında düştüğünü doğrulamak için arayın. *refValue* `DDV_MinMaxMonth`

```cpp
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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*refValue*<br/>
İletişim kutusu, form `CTime` görünümü `COleDateTime` veya denetim görünümü nesnesinin üye değişkeniyle ilişkili türdeki veya bir nesneye yapılan başvuru. Bu nesne doğrulanacak verileri içerir. MFC çağrıldığında `DDV_MinMaxMonth` bu başvurugeçer.

*refMinRange*<br/>
İzin verilen minimum tarih/saat değeri.

*refMaxRange*<br/>
İzin verilen maksimum tarih/saat değeri.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxshort"></a><a name="ddv_minmaxshort"></a>DDV_MinMaxShort

`DDV_MinMaxShort` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
Minimum değer **(kısa**tür) izin verilir.

*Maxval*<br/>
Maksimum değer **(kısa**tür) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxslider"></a><a name="ddv_minmaxslider"></a>DDV_MinMaxSlider

`DDV_MinMaxSlider` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
Doğrulanacak değere bir başvuru. Bu parametre kaydırıcı denetiminin geçerli başparmak konumunu tutar veya ayarlar.

*minVal*<br/>
İzin verilen minimum değer.

*Maxval*<br/>
İzin verilen maksimum değer.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. Kaydırıcı denetimleri hakkında daha fazla bilgi için [Bkz. CSliderCtrl'yi kullanma.](../../mfc/using-csliderctrl.md)

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxuint"></a><a name="ddv_minmaxuint"></a>DDV_MinMaxUInt

`DDV_MinMaxUInt` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
Minimum değer (UINT türü) izin verilir.

*Maxval*<br/>
Maksimum değer (UINT türü) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxulonglong"></a><a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong

`DDV_MinMaxULongLong` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

```cpp
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
Minimum değer (ULONGLONG türü) izin verilir.

*Maxval*<br/>
Maksimum değer (ULONGLONG türü) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddv_minmaxunsigned"></a>DDV_MinMaxUnsigned

`DDV_MinMaxUnsigned` *Değerle* ilişkili denetimdeki değerin *minVal* ve *maxVal*arasında düştüğünü doğrulamak için arayın.

### <a name="syntax"></a>Sözdizimi

```cpp
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin doğrulandığı denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*minVal*<br/>
Minimum değer **(imzasız** tür) izin verilir.

*Maxval*<br/>
Maksimum değer **(imzasız** tür) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdd_.h

## <a name="see-also"></a>Ayrıca bkz.

[Standart İletişim Veri Alışverişi Yordamları](standard-dialog-data-exchange-routines.md)<br/>
[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
[DDX_Slider](standard-dialog-data-exchange-routines.md#ddx_slider)<br/>
[DDX_FieldSlider](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md#ddx_fieldslider)
