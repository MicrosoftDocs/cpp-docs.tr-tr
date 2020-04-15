---
title: OLE Denetimleri için İletişim Kutusu Veri Değişimi İşlevleri
ms.date: 11/04/2016
f1_keywords:
- AFXDISP/DDX_OCBool
- AFXDISP/DDX_OCBoolRO
- AFXDISP/DDX_OCColor
- AFXDISP/DDX_OCColorRO
- AFXDISP/DDX_OCFloat
- AFXDISP/DDX_OCFloatRO
- AFXDISP/DDX_OCInt
- AFXDISP/DDX_OCIntRO
- AFXDISP/DDX_OCShort
- AFXDISP/DDX_OCShortRO
- AFXDISP/DDX_OCText
- AFXDISP/DDX_OCTextRO
helpviewer_keywords:
- OLE controls [MFC], DDX functions
- DDX (dialog data exchange), OLE support
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
ms.openlocfilehash: 61a5983eec13902ed4b0e397e3befca4860977d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365763"
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE Denetimleri için İletişim Kutusu Veri Değişimi İşlevleri

Bu konu, iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin veri üyesi bir OLE denetiminin özelliği arasında veri alışverişi için kullanılan DDX_OC işlevleri listeler.

### <a name="ddx_oc-functions"></a>DDX_OC Fonksiyonları

|||
|-|-|
|[DDX_OCBool](#ddx_ocbool)|**BOOL** verilerinin Bir OLE denetiminin özelliği ile **BOOL** veri üyesi arasında aktarılmasını yönetir.|
|[DDX_OCBoolRO](#ddx_ocboolro)|**BOOL** verilerinin bir OLE denetiminin salt okunur özelliği ile **BOOL** veri üyesi arasında aktarılmasını yönetir.|
|[DDX_OCColor](#ddx_occolor)|**OLE** denetiminin özelliği ile **OLE_COLOR** veri üyesi arasında OLE_COLOR veri aktarımını yönetir.|
|[DDX_OCColorRO](#ddx_occolorro)|OLE denetiminin salt okunur özelliği ile **OLE_COLOR** veri üyesi arasında **OLE_COLOR** veri aktarımını yönetir.|
|[DDX_OCFloat](#ddx_ocfloat)|Bir OLE denetiminin özelliği ile **float** (veya **double)** veri üyesi arasında **float** (veya **çift)** veri aktarımı yönetir.|
|[DDX_OCFloatRO](#ddx_ocfloatro)|Bir OLE denetiminin salt okunur özelliği ile **float** (veya **çift)** veri üyesi arasında **float** (veya **çift)** veri aktarımı yönetir.|
|[DDX_OCInt](#ddx_ocint)|**Int** (veya **uzun)** verilerinin Bir OLE denetiminin özelliği ile bir **int** (veya **uzun)** veri üyesi arasında aktarılmasını yönetir.|
|[DDX_OCIntRO](#ddx_ocintro)|**Int** (veya **uzun)** verilerinin Bir OLE denetiminin salt okunur özelliği ile **int** (veya **uzun)** veri üyesi arasında aktarılmasını yönetir.|
|[DDX_OCShort](#ddx_ocshort)|**Kısa** veri aktarımını bir OLE denetiminin özelliği ile **kısa** bir veri üyesi arasında yönetir.|
|[DDX_OCShortRO](#ddx_ocshortro)|**Kısa** veri aktarımını, bir OLE denetiminin salt okunur özelliği ile **kısa** bir veri üyesi arasında yönetir.|
|[DDX_OCText](#ddx_octext)|**CString** verilerinin bir OLE denetiminin özelliği ile **CString** veri üyesi arasında aktarılmasını yönetir.|
|[DDX_OCTextRO](#ddx_octextro)|**CString** verilerinin bir OLE denetiminin salt okunur özelliği ile **CString** veri üyesi arasında aktarılmasını yönetir.|

## <a name="ddx_ocbool"></a><a name="ddx_ocbool"></a>DDX_OCBool

İşlev, `DDX_OCBool` bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **BOOL** veri üyesi bir OLE denetiminin özelliği arasında **BOOL** verilerinin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi:** afxdisp.h

## <a name="ddx_ocboolro"></a><a name="ddx_ocboolro"></a>DDX_OCBoolRO

İşlev, `DDX_OCBoolRO` bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **BOOL** veri üyesi bir OLE denetiminin salt okunur özelliği arasında **BOOL** verilerinin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="ddx_occolor"></a><a name="ddx_occolor"></a>DDX_OCColor

İşlev, `DDX_OCColor` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin OLE_COLOR bir veri üyesindeki bir OLE denetiminin özelliği arasında OLE_COLOR veri aktarımı yönetir.

```cpp
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="ddx_occolorro"></a><a name="ddx_occolorro"></a>DDX_OCColorRO

İşlev, `DDX_OCColorRO` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin OLE_COLOR veri üyesindeki bir OLE denetiminin salt okunur özelliği arasında OLE_COLOR veri aktarımını yönetir.

```cpp
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="ddx_ocfloat"></a><a name="ddx_ocfloat"></a>DDX_OCFloat

İşlev, `DDX_OCFloat` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **float** (veya **çift)** veri üyesindeki bir OLE denetiminin özelliği arasında **float** (veya **çift)** veri aktarımı yönetir.

```cpp
void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    float& value);

void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    double& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="ddx_ocfloatro"></a><a name="ddx_ocfloatro"></a>DDX_OCFloatRO

İşlev, `DDX_OCFloatRO` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **float** (veya **çift)** veri üyesinde bir OLE denetiminin salt okunur özelliği arasında **float** (veya **çift)** veri aktarımı yönetir.

```cpp
void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    float& value);

void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    double& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="ddx_ocint"></a><a name="ddx_ocint"></a>DDX_OCInt

İşlev, `DDX_OCInt` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **int** (veya **uzun)** veri üyesindeki bir OLE denetiminin özelliği arasında **int** (veya **uzun)** verilerin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_OCInt(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    int& value);

void AFXAPI DDX_OCInt(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    long& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="ddx_ocintro"></a><a name="ddx_ocintro"></a>DDX_OCIntRO

İşlev, `DDX_OCIntRO` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **int** (veya **uzun)** veri üyesibir ole denetiminin salt okunur özelliği arasında **int** (veya **uzun)** verilerin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    int& value);

void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    long& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="ddx_ocshort"></a><a name="ddx_ocshort"></a>DDX_OCShort

İşlev, `DDX_OCShort` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin kısa bir veri üyesindeki bir OLE denetiminin özelliği arasında kısa veri aktarımını yönetir.

```cpp
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="ddx_ocshortro"></a><a name="ddx_ocshortro"></a>DDX_OCShortRO

İşlev, `DDX_OCShortRO` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin kısa bir veri üyesindeki bir OLE denetiminin salt okunur özelliği arasında kısa veri aktarımını yönetir.

```cpp
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="ddx_octext"></a><a name="ddx_octext"></a>DDX_OCText

**DDX_OCText** işlevi, bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **CString** veri üyesi bir OLE denetiminin özelliği arasında **CString** veri aktarımını yönetir.

```cpp
void AFXAPI DDX_OCText(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
**CDataExchange** nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="ddx_octextro"></a><a name="ddx_octextro"></a>DDX_OCTextRO

İşlev, `DDX_OCTextRO` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü `CString` veya denetim görünümü nesnesinin veri üyesindeki bir OLE denetiminin salt okunur özelliği arasındaki veri aktarımını `CString` yönetir.

```cpp
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusundaki OLE denetiminin kimliği, form görünümü veya denetim görünümü nesnesi.

*Dıspıd*<br/>
Denetimin bir özelliğinin sevk kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
