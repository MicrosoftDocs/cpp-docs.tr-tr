---
title: Standart İletişim Kutusu Veri Doğrulama Rutinleri
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: 19d1858d67802a7c464a9be783e4c1fb96fe3fae
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844489"
---
# <a name="standard-dialog-data-validation-routines"></a>Standart İletişim Kutusu Veri Doğrulama Rutinleri

Bu konu başlığı altında, genel MFC iletişim denetimleri için kullanılan standart iletişim kutusu veri doğrulama (DDV) yordamları listelenmektedir.

> [!NOTE]
> Standart iletişim kutusu veri değişimi yordamları afxdd_. h üstbilgi dosyasında tanımlanmıştır. Ancak, uygulamalar Afxwin. h 'yi içermelidir.

### <a name="ddv-functions"></a>DDV Işlevleri

|Ad|Açıklama|
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|Belirli bir denetim değerindeki karakterlerin sayısını, verilen en fazla sayıyı aşmadığını doğrular.|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Verilen bir denetim değerinin belirtilen bir **bayt** aralığını aşmadığını doğrular.|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Verilen bir denetim değerinin belirli bir zaman aralığını aşmadığını doğrular.|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Verilen bir denetim değerinin verilen bir aralığı aşmadığını doğrular **`double`** .|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Verilen bir denetim değerinin belirli bir **DWORD** aralığını aşmadığını doğrular.|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Verilen bir denetim değerinin verilen bir aralığı aşmadığını doğrular **`float`** .|
|[DDV_MinMaxInt](#ddv_minmaxint)|Verilen bir denetim değerinin verilen bir aralığı aşmadığını doğrular **`int`** .|
|[DDV_MinMaxLong](#ddv_minmaxlong)|Verilen bir denetim değerinin verilen bir aralığı aşmadığını doğrular **`long`** .|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Verilen bir denetim değerinin, verili bir **longlong** aralığını aşmadığını doğrular.|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Verilen bir denetim değerinin belirli bir tarih aralığını aşmadığını doğrular.|
|[DDV_MinMaxShort](#ddv_minmaxshort)|Verilen bir denetim değerinin verilen bir aralığı aşmadığını doğrular **`short`** .|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Verilen bir kaydırıcı denetim değerinin verilen aralık dahilinde olduğunu doğrular.|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Verilen bir denetim değerinin belirli bir **UINT** aralığını aşmadığını doğrular.|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|Verilen bir denetim değerinin belirtilen iki değer arasında olduğunu doğrular.|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Verilen bir denetim değerinin belirtilen bir **ULONGLONG** aralığını aşmadığını doğrular.|

## <a name="ddv_maxchars"></a><a name="ddv_maxchars"></a> DDV_MaxChars

`DDV_MaxChars`Denetimdeki metinle ilişkili karakter miktarının *nchar*değerlerini aşmadığını doğrulamak için çağırın *value* .

```cpp
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*Nchar 'lar*<br/>
İzin verilen en fazla karakter sayısı.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxbyte"></a><a name="ddv_minmaxbyte"></a> DDV_MinMaxByte

`DDV_MinMaxByte` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (bayt türünde) izin verilir.

*maxVal*<br/>
İzin verilen en büyük değer (bayt türü).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxdatetime"></a><a name="ddv_minmaxdatetime"></a> DDV_MinMaxDateTime

`DDV_MinMaxDateTime` *Refvalue* ile ilişkili tarih ve saat seçici denetimindeki ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) zaman/tarih değerinin *refMinRange* ve *refMaxRange*arasında olduğunu doğrulamak için çağırın.

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

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar. Bu nesneyi silmeniz gerekmez.

*refValue*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin üye değişkeniyle ilişkili bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya [cotadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine başvuru. Bu nesne Doğrulanacak verileri içerir.

*refMinRange*<br/>
İzin verilen en düşük tarih/saat değeri.

*refMaxRange*<br/>
İzin verilen en uzun tarih/saat değeri.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxdouble"></a><a name="ddv_minmaxdouble"></a> DDV_MinMaxDouble

`DDV_MinMaxDouble` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (türü **`double`** ) izin verilir.

*maxVal*<br/>
İzin verilen en büyük değer (türü **`double`** ).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxdword"></a><a name="ddv_minmaxdword"></a> DDV_MinMaxDWord

`DDV_MinMaxDWord` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (DWORD türünde) izin verilir.

*maxVal*<br/>
İzin verilen en büyük değer (DWORD türü).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxfloat"></a><a name="ddv_minmaxfloat"></a> DDV_MinMaxFloat

`DDV_MinMaxFloat` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (türü **`float`** ) izin verilir.

*maxVal*<br/>
İzin verilen en büyük değer (türü **`float`** ).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxint"></a><a name="ddv_minmaxint"></a> DDV_MinMaxInt

`DDV_MinMaxInt` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (türü **`int`** ) izin verilir.

*maxVal*<br/>
İzin verilen en büyük değer (türü **`int`** ).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxlong"></a><a name="ddv_minmaxlong"></a> DDV_MinMaxLong

`DDV_MinMaxLong` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (türü **`long`** ) izin verilir.

*maxVal*<br/>
İzin verilen en büyük değer (türü **`long`** ).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxlonglong"></a><a name="ddv_minmaxlonglong"></a> DDV_MinMaxLongLong

`DDV_MinMaxLongLong` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (LONGLONG türünde) izin verilir.

*maxVal*<br/>
En büyük değer (LONGLONG türünde) izin verilir.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxmonth"></a><a name="ddv_minmaxmonth"></a> DDV_MinMaxMonth

`DDV_MinMaxMonth` *Refvalue* ile ilişkili aylık takvim denetimindeki ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) saat/tarih değerinin *refMinRange* ve *refMaxRange*arasında olduğunu doğrulamak için çağırın.

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

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*refValue*<br/>
`CTime` `COleDateTime` İletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir üye değişkeniyle ilişkili veya türü bir nesneye başvuru. Bu nesne Doğrulanacak verileri içerir. Çağrıldığında, MFC bu başvuruyu geçirir `DDV_MinMaxMonth` .

*refMinRange*<br/>
İzin verilen en düşük tarih/saat değeri.

*refMaxRange*<br/>
İzin verilen en uzun tarih/saat değeri.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxshort"></a><a name="ddv_minmaxshort"></a> DDV_MinMaxShort

`DDV_MinMaxShort` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (türü **`short`** ) izin verilir.

*maxVal*<br/>
İzin verilen en büyük değer (türü **`short`** ).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxslider"></a><a name="ddv_minmaxslider"></a> DDV_MinMaxSlider

`DDV_MinMaxSlider` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
Doğrulanacak değere bir başvuru. Bu parametre kaydırıcı denetiminin geçerli Thumb konumunu tutar veya ayarlar.

*minVal*<br/>
İzin verilen en düşük değer.

*maxVal*<br/>
İzin verilen en büyük değer.

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Kaydırıcı denetimleri hakkında daha fazla bilgi için bkz. [CSliderCtrl kullanma](../../mfc/using-csliderctrl.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxuint"></a><a name="ddv_minmaxuint"></a> DDV_MinMaxUInt

`DDV_MinMaxUInt` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (UINT türünde) izin verilir.

*maxVal*<br/>
İzin verilen en büyük değer (UINT türünde).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxulonglong"></a><a name="ddv_minmaxulonglong"></a> DDV_MinMaxULongLong

`DDV_MinMaxULongLong` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

```cpp
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (ULONGLONG türünde) izin verilir.

*maxVal*<br/>
İzin verilen en büyük değer (ULONGLONG türünde).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddv_minmaxunsigned"></a>DDV_MinMaxUnsigned

`DDV_MinMaxUnsigned` *Değer* ile Ilişkili denetimdeki değerin *minval* ve *maxVal*arasında olduğunu doğrulamak için çağırın.

### <a name="syntax"></a>Söz dizimi

```cpp
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*deeri*<br/>
İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünümü nesnesinin üye değişkenine başvuru.

*minVal*<br/>
En küçük değer (türü **`unsigned`** ) izin verilir.

*maxVal*<br/>
İzin verilen en büyük değer (türü **`unsigned`** ).

### <a name="remarks"></a>Açıklamalar

DDV hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxdd_. h

## <a name="see-also"></a>Ayrıca bkz.

[Standart Iletişim kutusu veri değişimi yordamları](standard-dialog-data-exchange-routines.md)<br/>
[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[DDX_Slider](standard-dialog-data-exchange-routines.md#ddx_slider)<br/>
[DDX_FieldSlider](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md#ddx_fieldslider)
