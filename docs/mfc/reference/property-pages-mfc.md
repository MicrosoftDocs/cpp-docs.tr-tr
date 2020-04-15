---
title: Özellik Sayfaları (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages [MFC], global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
ms.openlocfilehash: 1064cd99d1820ae8865fa632c3097441172c78c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372990"
---
# <a name="property-pages-mfc"></a>Özellik Sayfaları (MFC)

Özellik sayfaları, iletişim veri alışverişine (DDX) dayalı bir veri eşleme mekanizmasını destekleyerek görüntüleme ve düzenleme için özelleştirilebilir, grafiksel bir arabirimde belirli OLE denetim özelliklerinin geçerli değerlerini görüntüler.

Bu veri eşleme mekanizması özellik sayfası denetimlerini OLE denetiminin tek tek özellikleriyle eşler. Denetim özelliğinin değeri, özellik sayfası denetiminin durumunu veya içeriğini yansıtır. Özellik sayfası denetimleri ve özellikleri **DDP_** arasındaki eşleme, özellik sayfasının `DoDataExchange` üye işlevindeki DDP_ işlev çağrıları tarafından belirtilir. Aşağıda, denetiminizin özellik sayfasını kullanarak girilen veri alışverişi yapan **DDP_** işlevlerin bir listesi verilmiştir:

### <a name="property-page-data-transfer"></a>Özellik Sayfası Veri Aktarımı

|||
|-|-|
|[DDP_CBIndex](#ddp_cbindex)|Seçili dizenin dizini bir açılan kutuya denetim özelliğiyle bağlar.|
|[DDP_CBString](#ddp_cbstring)|Seçili dizeyi bir açılan kutuya denetim özelliğiyle bağlar. Seçili dize özelliğin değeriyle aynı harflerle başlayabilir, ancak tam olarak eşleşmesi gerekmez.|
|[DDP_CBStringExact](#ddp_cbstringexact)|Seçili dizeyi bir açılan kutuya denetim özelliğiyle bağlar. Seçili dize ve özelliğin dize değeri tam olarak eşleşmelidir.|
|[DDP_Check](#ddp_check)|Denetimin özellik sayfasındaki bir onay kutusunu denetimin özelliğiyle bağlar.|
|[DDP_LBIndex](#ddp_lbindex)|Seçili dizenin dizinini bir liste kutusuna denetim özelliğiyle bağlar.|
|[DDP_LBString](#ddp_lbstring)|Seçili dizeyi bir liste kutusuna denetim özelliğiyle bağlar. Seçili dize özelliğin değeriyle aynı harflerle başlayabilir, ancak tam olarak eşleşmesi gerekmez.|
|[DDP_LBStringExact](#ddp_lbstringexact)|Seçili dizeyi bir liste kutusuna denetim özelliğiyle bağlar. Seçili dize ve özelliğin dize değeri tam olarak eşleşmelidir.|
|[DDP_PostProcessing](#ddp_postprocessing)|Mülk değerlerinin denetiminizden aktarılmasını tamamlar.|
|[DDP_Radio](#ddp_radio)|Denetimin özellik sayfasındaki bir radyo düğmesi grubunu denetimin özelliğiyle bağlar.|
|[DDP_Text](#ddp_text)|Denetimin özellik sayfasındaki denetimi denetimin özelliğiyle bağlar. Bu işlev, **çift,** **kısa,** BSTR ve **uzun**gibi birkaç farklı türde özelliği işler.|

`DoDataExchange` İşlev ve özellik sayfaları hakkında daha fazla bilgi için [ActiveX Denetimleri makalesine bakın: Özellik Sayfaları.](../../mfc/mfc-activex-controls-property-pages.md)

Aşağıda, OLE denetimi için özellik sayfalarını oluşturmak ve yönetmek için kullanılan makroların listesi ve

### <a name="property-pages"></a>Özellik Sayfaları

|||
|-|-|
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|Özellik sayfası iYeliklerinin listesini başlatın.|
|[END_PROPPAGEIDS](#end_proppageids)|Özellik sayfası iYelikleri listesini sona erdirer.|
|[PROPPAGEID](#proppageid)|Denetim sınıfının özellik sayfasını bildirir.|

## <a name="ddp_cbindex"></a><a name="ddp_cbindex"></a>DDP_CBIndex

Bir tamsayı özelliğinin değerini `DoDataExchange` özellik sayfasındaki açılan kutudaki geçerli seçimin diziniyle eşitlemek için özellik sayfanızın işlevinde bu işlevi çağırın.

```
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Kimliği*<br/>
*pszPropName*tarafından belirtilen denetim özelliği ile ilişkili açılan kutu denetiminin kaynak kimliği.

*Üye*<br/>
*Id* tarafından belirtilen özellik sayfası denetimi ile ilişkili üye değişkeni ve *pszPropName*tarafından belirtilen özellik .

*pszPropName*<br/>
Kimlik *tarafından*belirtilen açılan kutu kontrolü ile değiştirilecek kontrol özelliğinin özelliği.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ilgili `DDX_CBIndex` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="ddp_cbstring"></a><a name="ddp_cbstring"></a>DDP_CBString

Bir dize özelliğinin değerini `DoDataExchange` özellik sayfasındaki açılan kutudaki geçerli seçimle eşitlemek için özellik sayfanızın işlevinde bu işlevi çağırın.

```
void AFXAPI DDP_CBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Kimliği*<br/>
*pszPropName*tarafından belirtilen denetim özelliği ile ilişkili açılan kutu denetiminin kaynak kimliği.

*Üye*<br/>
*Id* tarafından belirtilen özellik sayfası denetimi ile ilişkili üye değişkeni ve *pszPropName*tarafından belirtilen özellik .

*pszPropName*<br/>
*Id*tarafından belirtilen açılan kutu dizesi ile değiştirilecek kontrol özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ilgili `DDX_CBString` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="ddp_cbstringexact"></a><a name="ddp_cbstringexact"></a>DDP_CBStringExact

Özellik sayfasındaki açılan kutudaki `DoDataExchange` geçerli seçimle tam olarak eşleşen bir dize özelliğinin değerini eşitlemek için özellik sayfanızın işlevinde bu işlevi çağırın.

```
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Kimliği*<br/>
*pszPropName*tarafından belirtilen denetim özelliği ile ilişkili açılan kutu denetiminin kaynak kimliği.

*Üye*<br/>
*Id* tarafından belirtilen özellik sayfası denetimi ile ilişkili üye değişkeni ve *pszPropName*tarafından belirtilen özellik .

*pszPropName*<br/>
*Id*tarafından belirtilen açılan kutu dizesi ile değiştirilecek kontrol özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ilgili `DDX_CBStringExact` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="ddp_check"></a><a name="ddp_check"></a>DDP_Check

Özelliğin değerini ilişkili özellik `DoDataExchange` sayfası onay kutusu denetimiyle eşitlemek için özellik sayfanızın işlevinde bu işlevi çağırın.

```
void AFXAPI DDP_Check(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Kimliği*<br/>
*pszPropName*tarafından belirtilen denetim özelliği ile ilişkili onay kutusu denetiminin kaynak kimliği.

*Üye*<br/>
*Id* tarafından belirtilen özellik sayfası denetimi ile ilişkili üye değişkeni ve *pszPropName*tarafından belirtilen özellik .

*pszPropName*<br/>
Kimlik *tarafından*belirtilen onay kutusu denetimi ile değiştirilecek kontrol özelliğinin özelliği.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ilgili `DDX_Check` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="ddp_lbindex"></a><a name="ddp_lbindex"></a>DDP_LBIndex

Bir tamsayı özelliğinin değerini `DoDataExchange` özellik sayfasındaki bir liste kutusundageçerli seçimin diziniyle eşitlemek için özellik sayfanızın işlevinde bu işlevi çağırın.

```
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Kimliği*<br/>
*pszPropName*tarafından belirtilen denetim özelliği ile ilişkili liste kutusu denetiminin kaynak kimliği.

*Üye*<br/>
*Id* tarafından belirtilen özellik sayfası denetimi ile ilişkili üye değişkeni ve *pszPropName*tarafından belirtilen özellik .

*pszPropName*<br/>
*Id*tarafından belirtilen liste kutusu dizeile değiştirilecek kontrol özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ilgili `DDX_LBIndex` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="ddp_lbstring"></a><a name="ddp_lbstring"></a>DDP_LBString

Özellik sayfasındaki liste kutusunda `DoDataExchange` geçerli seçimle bir dize özelliğinin değerini eşitlemek için özellik sayfanızın işlevinde bu işlevi çağırın.

```
void AFXAPI DDP_LBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Kimliği*<br/>
*pszPropName*tarafından belirtilen denetim özelliği ile ilişkili liste kutusu denetiminin kaynak kimliği.

*Üye*<br/>
*Id* tarafından belirtilen özellik sayfası denetimi ile ilişkili üye değişkeni ve *pszPropName*tarafından belirtilen özellik .

*pszPropName*<br/>
*Id*tarafından belirtilen liste kutusu dizeile değiştirilecek kontrol özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ilgili `DDX_LBString` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="ddp_lbstringexact"></a><a name="ddp_lbstringexact"></a>DDP_LBStringExact

Özellik sayfasındaki liste kutusunda `DoDataExchange` geçerli seçimle tam olarak eşleşen bir dize özelliğinin değerini eşitlemek için özellik sayfanızın işlevinde bu işlevi çağırın.

```
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Kimliği*<br/>
*pszPropName*tarafından belirtilen denetim özelliği ile ilişkili liste kutusu denetiminin kaynak kimliği.

*Üye*<br/>
*Id* tarafından belirtilen özellik sayfası denetimi ile ilişkili üye değişkeni ve *pszPropName*tarafından belirtilen özellik .

*pszPropName*<br/>
*Id*tarafından belirtilen liste kutusu dizeile değiştirilecek kontrol özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ilgili `DDX_LBStringExact` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="ddp_postprocessing"></a><a name="ddp_postprocessing"></a>DDP_PostProcessing

Özellik değerleri kaydedilirken özellik `DoDataExchange` sayfasından denetiminize özellik değerlerinin transferini tamamlamak için özellik sayfanızın işlevinde bu işlevi arayın.

```
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

### <a name="remarks"></a>Açıklamalar

Tüm veri alışverişi işlevleri tamamlandıktan sonra bu işlev çağrılmalıdır. Örneğin:

[!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="ddp_radio"></a><a name="ddp_radio"></a>DDP_Radio

İlgili özellik sayfası radyo `DoPropExchange` düğmesi denetimi ile özelliğin değerini senkronize etmek için denetiminizin işlevinde bu işlevi arayın.

```
void AFXAPI DDP_Radio(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Kimliği*<br/>
*pszPropName*tarafından belirtilen kontrol özelliği ile ilişkili radyo düğmesi denetiminin kaynak kimliği.

*Üye*<br/>
*Id* tarafından belirtilen özellik sayfası denetimi ile ilişkili üye değişkeni ve *pszPropName*tarafından belirtilen özellik .

*pszPropName*<br/>
Id *tarafından*belirtilen radyo düğmesi kontrolü ile değiştirilecek kontrol özelliğinin özelliği.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ilgili `DDX_Radio` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="ddp_text"></a><a name="ddp_text"></a>DDP_Text

Özelliğin değerini ilişkili özellik `DoDataExchange` sayfası denetimiyle eşitlemek için denetiminizin işlevinde bu işlevi çağırın.

```
void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    BYTE & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    UINT & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    long & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    DWORD & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    float & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    double & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    CString & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*Kimliği*<br/>
*pszPropName*tarafından belirtilen denetim özelliği ile ilişkili denetimin kaynak kimliği.

*Üye*<br/>
*Id* tarafından belirtilen özellik sayfası denetimi ile ilişkili üye değişkeni ve *pszPropName*tarafından belirtilen özellik .

*pszPropName*<br/>
Kimlik *tarafından*belirtilen kontrol ile değiştirilecek kontrol özelliğinin özelliği.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ilgili `DDX_Text` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="begin_proppageids"></a><a name="begin_proppageids"></a>BEGIN_PROPPAGEIDS

Denetiminizin özellik sayfası iYelikleri listesinin tanımını başla.

```
BEGIN_PROPPAGEIDS(class_name,  count)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Özellik sayfalarının belirtildiği denetim sınıfının adı.

*Sayısı*<br/>
Denetim sınıfı tarafından kullanılan özellik sayfası sayısı.

### <a name="remarks"></a>Açıklamalar

Sınıfınızın üye işlevlerini tanımlayan uygulama (.cpp) dosyasında, özellik sayfası listesini BEGIN_PROPPAGEIDS makrosuyla başlatın, ardından her mülk sayfanız için makro girişleri ekleyin ve END_PROPPAGEIDS makrosuyla özellik sayfası listesini tamamlayın.

Özellik sayfaları hakkında daha fazla bilgi için [ActiveX Denetimleri: Özellik Sayfaları](../../mfc/mfc-activex-controls-property-pages.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="end_proppageids"></a><a name="end_proppageids"></a>END_PROPPAGEIDS

Özellik sayfası kimlik listenizin tanımını sona erdirer.

```
END_PROPPAGEIDS(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Özellik sayfasının sahibi denetim sınıfının adı.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="proppageid"></a><a name="proppageid"></a>PROPPAGEID

OLE denetiminiz tarafından kullanılmak üzere bir özellik sayfası ekler.

```
PROPPAGEID(clsid)
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
Özellik sayfasının benzersiz sınıf kimliği.

### <a name="remarks"></a>Açıklamalar

Tüm PROPPAGEID makroları, denetiminizin uygulama dosyasındaki BEGIN_PROPPAGEIDS ve END_PROPPAGEIDS makrolar arasına yerleştirilmelidir.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
