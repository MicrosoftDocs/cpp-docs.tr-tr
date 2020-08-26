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
ms.openlocfilehash: 9133c30dd1ac069145862d4bf61ba0bc0d504838
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837365"
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE Denetimleri için İletişim Kutusu Veri Değişimi İşlevleri

Bu konu başlığı altında, bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir veri üyesi içindeki OLE denetiminin bir özelliği arasında veri alışverişi yapmak için kullanılan DDX_OC işlevleri listelenmektedir.

### <a name="ddx_oc-functions"></a>DDX_OC Işlevleri

|Ad|Açıklama|
|-|-|
|[DDX_OCBool](#ddx_ocbool)|Bir OLE denetiminin ve **bool** veri üyesinin bir özelliği arasında **bool** verilerinin aktarılmasını yönetir.|
|[DDX_OCBoolRO](#ddx_ocboolro)|Bir OLE denetiminin salt okunurdur özelliği ve **bool** veri üyesi arasında **bool** verilerinin aktarılmasını yönetir.|
|[DDX_OCColor](#ddx_occolor)|OLE denetiminin bir özelliği ve bir **OLE_COLOR** veri üyesi arasında **OLE_COLOR** verilerinin aktarımını yönetir.|
|[DDX_OCColorRO](#ddx_occolorro)|Bir OLE denetiminin salt okunurdur özelliği ve bir **OLE_COLOR** veri üyesi arasında **OLE_COLOR** verilerinin aktarımını yönetir.|
|[DDX_OCFloat](#ddx_ocfloat)|Bir **`float`** **`double`** OLE denetimi ve **`float`** (veya **`double`** ) veri üyesi özelliği arasındaki (veya) verilerin aktarımını yönetir.|
|[DDX_OCFloatRO](#ddx_ocfloatro)|Bir **`float`** **`double`** OLE denetiminin ve **`float`** (veya) veri üyesinin salt okunurdur özelliği arasındaki (veya) verilerin aktarımını yönetir **`double`** .|
|[DDX_OCInt](#ddx_ocint)|Bir **`int`** **`long`** OLE denetimi ve **`int`** (veya **`long`** ) veri üyesi özelliği arasındaki (veya) verilerin aktarımını yönetir.|
|[DDX_OCIntRO](#ddx_ocintro)|**`int`** **`long`** Bir OLE denetiminin salt okunurdur özelliği ve **`int`** (veya) veri üyesi arasındaki (veya) verilerin aktarılmasını yönetir **`long`** .|
|[DDX_OCShort](#ddx_ocshort)|**`short`** OLE denetiminin ve veri üyesinin bir özelliği arasında veri aktarımını yönetir **`short`** .|
|[DDX_OCShortRO](#ddx_ocshortro)|**`short`** BIR OLE denetiminin ve bir veri üyesinin salt okunurdur özelliği arasında veri aktarımını yönetir **`short`** .|
|[DDX_OCText](#ddx_octext)|OLE denetiminin ve **CString** veri üyesinin bir özelliği arasında **CString** verilerinin aktarımını yönetir.|
|[DDX_OCTextRO](#ddx_octextro)|Bir OLE denetiminin salt okunurdur özelliği ve **CString** veri üyesi arasında **CString** verilerinin aktarımını yönetir.|

## <a name="ddx_ocbool"></a><a name="ddx_ocbool"></a> DDX_OCBool

`DDX_OCBool`İşlevi, bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **bool** veri ÜYESI içindeki bir OLE denetimi özelliği arasında **bool** verilerinin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi:** AfxDisp. h

## <a name="ddx_ocboolro"></a><a name="ddx_ocboolro"></a> DDX_OCBoolRO

`DDX_OCBoolRO`İşlevi, bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **bool** veri ÜYESI içindeki bir OLE denetiminin salt okunurdur özelliği arasında **bool** verilerinin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="ddx_occolor"></a><a name="ddx_occolor"></a> DDX_OCColor

`DDX_OCColor`İşlevi bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir OLE_COLOR veri üyesi içindeki BIR OLE denetimi özelliği arasında OLE_COLOR verilerinin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="ddx_occolorro"></a><a name="ddx_occolorro"></a> DDX_OCColorRO

`DDX_OCColorRO`İşlevi bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir OLE_COLOR veri üyesi içindeki BIR OLE denetiminin salt okunurdur özelliği arasında OLE_COLOR verilerinin aktarımını yönetir.

```cpp
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="ddx_ocfloat"></a><a name="ddx_ocfloat"></a> DDX_OCFloat

`DDX_OCFloat`İşlevi, **`float`** **`double`** bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve **`float`** **`double`** iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir (veya) veri üyesi içindeki bir OLE denetimi özelliği arasında veri aktarımını (veya) yönetir.

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

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="ddx_ocfloatro"></a><a name="ddx_ocfloatro"></a> DDX_OCFloatRO

`DDX_OCFloatRO`İşlevi, **`float`** **`double`** bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve **`float`** **`double`** iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir (veya) veri üyesi içindeki bir OLE denetiminin salt okunurdur özelliği arasında veri aktarımını yönetir.

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

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="ddx_ocint"></a><a name="ddx_ocint"></a> DDX_OCInt

`DDX_OCInt`İşlevi, **`int`** **`long`** bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve **`int`** **`long`** iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir (veya) veri üyesi içindeki bir OLE denetimi özelliği arasında veri aktarımını (veya) yönetir.

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

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="ddx_ocintro"></a><a name="ddx_ocintro"></a> DDX_OCIntRO

`DDX_OCIntRO`İşlevi, **`int`** **`long`** bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve **`int`** **`long`** iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir (veya) veri üyesi içindeki bir OLE denetiminin salt okunurdur özelliği arasında veri aktarımını yönetir.

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

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="ddx_ocshort"></a><a name="ddx_ocshort"></a> DDX_OCShort

`DDX_OCShort`İşlevi bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin kısa veri üyesi içindeki BIR OLE denetimi özelliği arasında kısa verilerin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="ddx_ocshortro"></a><a name="ddx_ocshortro"></a> DDX_OCShortRO

`DDX_OCShortRO`İşlevi bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin kısa bir veri üyesi olan BIR OLE denetiminin salt okunurdur özelliği arasında kısa verilerin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="ddx_octext"></a><a name="ddx_octext"></a> DDX_OCText

**DDX_OCText** işlevi bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir **CString** VERI üyesi içindeki bir OLE denetimi özelliği arasında **CString** verilerinin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_OCText(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
**CDataExchange** nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="ddx_octextro"></a><a name="ddx_octextro"></a> DDX_OCTextRO

`DDX_OCTextRO`İşlevi `CString` bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve `CString` iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir veri ÜYESI olan bir OLE denetiminin salt okunurdur özelliği arasında veri aktarımını yönetir.

```cpp
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki OLE denetiminin KIMLIĞI.

*dı*<br/>
Denetimin bir özelliğinin dağıtım KIMLIĞI.

*deeri*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
