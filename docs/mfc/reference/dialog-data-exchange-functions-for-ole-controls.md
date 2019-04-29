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
ms.openlocfilehash: df96d44cefeb15d89653538c3006d109a97a21a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322572"
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE Denetimleri için İletişim Kutusu Veri Değişimi İşlevleri

Bu konuda, bir iletişim kutusu, form görünümü veya denetim view nesnesinin bir OLE denetim özelliği iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi arasında veri değişimi için kullanılan DDX_OC işlevleri listeler.

### <a name="ddxoc-functions"></a>DDX_OC işlevleri

|||
|-|-|
|[DDX_OCBool](#ddx_ocbool)|Aktarımını yöneten **BOOL** OLE denetimin bir özelliğine arasında veri ve **BOOL** veri üyesi.|
|[DDX_OCBoolRO](#ddx_ocboolro)|Aktarımını yöneten **BOOL** salt okunur bir özellik bir OLE denetim arasında verileri ve **BOOL** veri üyesi.|
|[DDX_OCColor](#ddx_occolor)|Aktarımını yöneten **OLE_COLOR** OLE denetimin bir özelliğine arasında veri ve **OLE_COLOR** veri üyesi.|
|[DDX_OCColorRO](#ddx_occolorro)|Aktarımını yöneten **OLE_COLOR** salt okunur bir özellik bir OLE denetim arasında verileri ve bir **OLE_COLOR** veri üyesi.|
|[DDX_OCFloat](#ddx_ocfloat)|Aktarımını yöneten **float** (veya **çift**) arasında bir OLE denetimin bir özelliğine veri ve **float** (veya **çift**) veri üyesi.|
|[DDX_OCFloatRO](#ddx_ocfloatro)|Aktarımını yöneten **float** (veya **çift**) bir OLE denetimi salt okunur bir özellik arasında verileri ve **float** (veya **çift**) veri üye.|
|[Ddx_ocınt](#ddx_ocint)|Aktarımını yöneten **int** (veya **uzun**) arasında bir OLE denetimin bir özelliğine veri ve **int** (veya **uzun**) veri üyesi.|
|[DDX_OCIntRO](#ddx_ocintro)|Aktarımını yöneten **int** (veya **uzun**) bir OLE denetimi salt okunur bir özellik arasında verileri ve bir **int** (veya **uzun**) veri üyesi.|
|[DDX_OCShort](#ddx_ocshort)|Aktarımını yöneten **kısa** OLE denetimin bir özelliğine arasında veri ve **kısa** veri üyesi.|
|[DDX_OCShortRO](#ddx_ocshortro)|Aktarımını yöneten **kısa** salt okunur bir özellik bir OLE denetim arasında verileri ve **kısa** veri üyesi.|
|[DDX_OCText](#ddx_octext)|Aktarımını yöneten **CString** OLE denetimin bir özelliğine arasında veri ve **CString** veri üyesi.|
|[DDX_OCTextRO](#ddx_octextro)|Aktarımını yöneten **CString** salt okunur bir özellik bir OLE denetim arasında verileri ve **CString** veri üyesi.|

##  <a name="ddx_ocbool"></a>  DDX_OCBool

`DDX_OCBool` İşlevi aktarımını yöneten **BOOL** arasında bir iletişim kutusunda, bir OLE denetimin bir özelliğine veri görünümü veya denetim görünüm nesnesi oluşturur ve bir **BOOL** form görünümü, iletişim kutusunun veri üyesi veya Denetim Görünüm nesnesi.

```
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Başlık:** afxdisp.h

##  <a name="ddx_ocboolro"></a>  DDX_OCBoolRO

`DDX_OCBoolRO` İşlevi aktarımını yöneten **BOOL** salt okunur bir özellik bir iletişim kutusunda, bir OLE denetim arasında verileri form görünümü veya denetim görünüm nesnesi ve bir **BOOL** iletişim kutusunun veri üyesi Form görünümü veya denetim görünüm nesnesi.

```
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="ddx_occolor"></a>  DDX_OCColor

`DDX_OCColor` İşlevi arasındaki iletişim kutusunda, form görünümü bir OLE denetimin bir özelliğine OLE_COLOR veri aktarımını yönetir veya denetim görünüm nesnesi ve iletişim kutusunda, OLE_COLOR veri üyesi form görünümü ya da Denetim Görünüm nesnesi.

```
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="ddx_occolorro"></a>  DDX_OCColorRO

`DDX_OCColorRO` İşlevi bir OLE denetim iletişim kutusunda, form görünümü salt okunur bir özellik arasında OLE_COLOR veri aktarımını yönetir veya denetim görünüm nesnesi ve iletişim kutusunda, OLE_COLOR veri üyesi form görünümü ya da Denetim Görünüm nesnesi.

```
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="ddx_ocfloat"></a>  DDX_OCFloat

`DDX_OCFloat` İşlevi aktarımını yöneten **float** (veya **çift**) arasında bir iletişim kutusunda, bir OLE denetimin bir özelliğine veri görünümü veya denetim görünüm nesnesi oluşturur ve bir **float** (veya **çift**) iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

```
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
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="ddx_ocfloatro"></a>  DDX_OCFloatRO

`DDX_OCFloatRO` İşlevi aktarımını yöneten **float** (veya **çift**) iletişim kutusundaki bir OLE denetimi salt okunur bir özellik arasında verileri form görünümü veya denetim görünüm nesnesi ve bir  **float** (veya **çift**) iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

```
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
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="ddx_ocint"></a>  Ddx_ocınt

`DDX_OCInt` İşlevi aktarımını yöneten **int** (veya **uzun**) arasında bir iletişim kutusunda, bir OLE denetimin bir özelliğine veri görünümü veya denetim görünüm nesnesi oluşturur ve bir **int**(veya **uzun**) iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

```
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
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="ddx_ocintro"></a>  DDX_OCIntRO

`DDX_OCIntRO` İşlevi aktarımını yöneten **int** (veya **uzun**) iletişim kutusundaki bir OLE denetimi salt okunur bir özellik arasında verileri form görünümü veya denetim görünüm nesnesi ve bir **int** (veya **uzun**) iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

```
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
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="ddx_ocshort"></a>  DDX_OCShort

`DDX_OCShort` İşlevi arasındaki iletişim kutusunda, form görünümü bir OLE denetimin bir özelliğine kısa veri aktarımını yönetir veya denetim görünüm nesnesi ve iletişim kutusunda, kısa veri üyesi form görünümü ya da Denetim Görünüm nesnesi.

```
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="ddx_ocshortro"></a>  DDX_OCShortRO

`DDX_OCShortRO` İşlevi bir OLE denetim iletişim kutusunda, form görünümü salt okunur bir özellik arasında kısa veri aktarımını yönetir veya denetim görünüm nesnesi ve iletişim kutusunda, kısa veri üyesi form görünümü ya da Denetim Görünüm nesnesi.

```
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="ddx_octext"></a>  DDX_OCText

**DDX_OCText** işlevi aktarımını yöneten **CString** arasında bir iletişim kutusunda, bir OLE denetimin bir özelliğine veri görünümü veya denetim görünüm nesnesi oluşturur ve bir **CString** veri iletişim kutusu, form görünümü veya denetim görünüm nesnesi üyesi.

```
void AFXAPI DDX_OCText(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir **CDataExchange** nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="ddx_octextro"></a>  DDX_OCTextRO

`DDX_OCTextRO` İşlevi aktarımını yöneten `CString` salt okunur bir özellik bir iletişim kutusunda, bir OLE denetim arasında verileri form görünümü veya denetim görünüm nesnesi ve bir `CString` iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

```
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir OLE denetim iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*DISPID*<br/>
Denetimin bir özelliğine gönderme kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
