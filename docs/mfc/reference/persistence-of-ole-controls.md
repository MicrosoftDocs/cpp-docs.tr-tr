---
title: OLE Denetimlerinin Kalıcılığı
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
ms.openlocfilehash: 88707da503b1d1cdc809827dc4d1bac0ccad9b5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373006"
---
# <a name="persistence-of-ole-controls"></a>OLE Denetimlerinin Kalıcılığı

OLE denetimlerinin bir özelliği, OLE denetiminin bir dosya veya akışa ve dosyadan özellik değerlerini okumasına veya yazmasına olanak tanıyan özellik kalıcılığıdır (veya serileştirmedir). Kapsayıcı uygulaması, uygulama denetimi yok ettikten sonra bile denetimin özellik değerlerini depolamak için serileştirme yi kullanabilir. OLE denetiminin özellik değerleri daha sonra denetimin yeni bir örneği oluşturulduğunda dosyadan veya akıştan okunabilir.

### <a name="persistence-of-ole-controls"></a>OLE Denetimlerinin Kalıcılığı

|||
|-|-|
|[PX_Blob](#px_blob)|İkili büyük nesne (BLOB) verilerini depolayan bir denetim özelliğini değiştirir.|
|[PX_Bool](#px_bool)|BoOL tipi bir **BOOL**kontrol özelliği ni değiştirir.|
|[PX_Color](#px_color)|Denetimin renk özelliğini değiştirir.|
|[PX_Currency](#px_currency)|**CY**tipi bir denetim özelliğini değiştirir.|
|[PX_DataPath](#px_datapath)|Tür bir denetim özelliği `CDataPathProperty`ni değiştirir.|
|[PX_Double](#px_double)|Çift **türünde**bir denetim özelliğini değiştirir.|
|[PX_Font](#px_font)|Denetimin yazı tipi özelliğini değiştirir.|
|[PX_Float](#px_float)|Tür float bir kontrol özelliği **alışverişi.**|
|[PX_IUnknown](#px_iunknown)|Tanımlanmamış türde bir denetim özelliğini değiştirir.|
|[PX_Long](#px_long)|Uzun **tür**bir kontrol özelliği değiştirir.|
|[PX_Picture](#px_picture)|Bir denetimin resim özelliğini değiştirir.|
|[PX_Short](#px_short)|Kısa **türünde**bir denetim özelliği ni değiştirir.|
|[PX_ULong](#px_ulong)|**ULONG**tipi bir kontrol özelliğini değiştirir.|
|[PX_UShort](#px_ushort)|**USHORT**tipi bir kontrol özelliğini değiştirir.|
|[PXstring](#px_string)|Bir karakter dize denetim özelliği ni değiştirir.|
|[PX_VBXFontConvert](#px_vbxfontconvert)|VBX denetiminin yazı tipiyle ilgili özelliklerini OLE denetim yazı tipi özelliğine dönüştürür.|

Buna ek `AfxOleTypeMatchGuid` olarak, bir TYPEDESC ve belirli bir GUID arasındaki eşleşmeyi test etmek için global işlev sağlanır.

## <a name="px_blob"></a><a name="px_blob"></a>PX_Blob

İkili büyük nesne (BLOB) verilerini depolayan bir özelliği seri hale getirmek veya başlatmak için denetiminizin `DoPropExchange` üye işlevi içinde bu işlevi arayın.

```cpp
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*hBlob*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*hBlobVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Tesisin değeri, uygun olduğu şekilde *hBlob*tarafından başvurulan değişkenden okunacak veya yazılacaktır. Bu değişken ilk kez çağırmadan `PX_Blob` önce NULL'a başharfle alınmalıdır (genellikle, bu denetimin oluşturucusunda yapılabilir). *hBlobDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin başlatma veya serileştirme işlemi başarısız olursa kullanılır.

*hBlob* ve *hBlobDefault* tutamaçları aşağıdakileri içeren bir bellek bloğuna başvurur:

- Takip eden ikili verilerin uzunluğunu, baytlar içinde içeren bir DWORD, hemen ardından

- Gerçek ikili verileri içeren bir bellek bloğu.

`PX_Blob` BLOB tipi özellikleri yüklerken Windows [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) API'sını kullanarak bellek ayrılacağını unutmayın. Bu anıyı kurtarmakla sen sorumlusun. Bu nedenle, denetiminizin yıkıcısı, denetiminize ayrılan herhangi bir belleği boşaltmak için herhangi bir BLOB tipi özellik tutamaz lığıyla [GlobalFree'i](/windows/win32/api/winbase/nf-winbase-globalfree) aramalıdır.

## <a name="px_bool"></a><a name="px_bool"></a>PX_Bool

BOOL türünde bir `DoPropExchange` özelliği seri hale getirmek veya başlatmak için bu işlevi denetiminizin üye işlevi içinde arayın.

```cpp
BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue);

BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue,
    BOOL bDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*bDeğer*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*bVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *bValue*tarafından başvurulan değişkenden okunacak veya yazılacaktır. *bDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_color"></a><a name="px_color"></a>PX_Color

Tür OLE_COLOR bir özelliği `DoPropExchange` seri hale getirmek veya başlatmak için bu işlevi denetiminizin üye işlevi içinde arayın.

```cpp
BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue,
    OLE_COLOR clrDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*clrDeğer*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*clrVarsayılan varsayılan*<br/>
Denetim geliştiricisi tarafından tanımlandığı gibi, özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *clrValue*tarafından başvurulan değişkenden okunacak veya yazılacaktır. *ClrDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_currency"></a><a name="px_currency"></a>PX_Currency

Tür para biriminin bir `DoPropExchange` özelliğini seri hale getirmek veya **currency**başlatmak için bu işlevi denetiminizin üye işlevi içinde arayın.

```cpp
BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue);

BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue,
    CY cyDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*cyValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*cyVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *cyValue*tarafından başvurulan değişkenden okunacak veya yazılacaktır. *cyDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_datapath"></a><a name="px_datapath"></a>PX_DataPath

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)türünde `DoPropExchange` bir veri yolu özelliğini seri hale getirmek veya başlatmak için bu işlevi denetiminizin üye işlevi içinde arayın.

```cpp
BOOL PX_DataPath(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CDataPathProperty& dataPathProperty);

BOOL PX_DataPath(
    CPropExchange* pPX,
    CDataPathProperty& dataPathProperty);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*dataPathProperty*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Veri yolu özellikleri asynchronous denetim özellikleri uygular. Özelliğin değeri, uygun olduğu şekilde *dataPathProperty*tarafından başvurulan değişkenden okunacak veya yazılacaktır.

## <a name="px_double"></a><a name="px_double"></a>PX_Double

Bu işlevi, `DoPropExchange` **denetiminizin**üye işlevi içinde, çift türdeki bir özelliği serihale getirmek veya başlatmak için çağırın.

```cpp
BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue);

BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue,
    double doubleDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*doubleValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*doubleDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *doubleValue*ile başvurulan değişkenden okunur veya yazılır. *DoubleDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_font"></a><a name="px_font"></a>PX_Font

Tür yazı tipinin bir `DoPropExchange` özelliğini seri hale getirmek veya başlatmak için denetiminizin üye işlevi içinde bu işlevi arayın.

```cpp
BOOL PX_Font(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC FAR* pFontDesc = NULL,
    LPFONTDISP pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*Yazı tipi*<br/>
Yazı tipi `CFontHolder` özelliğini içeren bir nesneye başvuru.

*pFontDesc*<br/>
`FONTDESC` *pFontDispAmbient'in* NULL olduğu durumlarda, yazı tipi özelliğinin varsayılan durumunu başlatmada kullanılacak değerleri içeren bir yapıya işaretçi.

*pFontDispAmbient*<br/>
Yazı tipi `IFontDisp` özelliğinin varsayılan durumunu başlatmada kullanılacak bir yazı tipiarabirimine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğunda bir `font` `CFontHolder` referanstan okunur veya yazılır. *pFontDesc* ve *pFontDispAmbient* belirtilirse, gerektiğinde özelliğin varsayılan değerini başlangıç olarak kodlamak için kullanılırlar. Herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa, bu değerler kullanılır. Genellikle, *pFontDesc* için NULL geçmek ve ortam değeri `COleControl::AmbientFont` *pFontDispAmbient*için döndürülen. Döndürülen `COleControl::AmbientFont` yazı tipi nesnesinin `IFontDisp::Release` üye işleviçin bir çağrı tarafından serbest bırakılması gerektiğini unutmayın.

## <a name="px_float"></a><a name="px_float"></a>PX_Float

Bir tür **float**özelliğini `DoPropExchange` serihale getirmek veya başlatmak için denetiminizin üye işlevi içinde bu işlevi arayın.

```cpp
BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue);

BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue,
    float floatDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*floatValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*floatVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *floatValue*tarafından başvurulan değişkenden okunur veya yazılır. *FloatDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_iunknown"></a><a name="px_iunknown"></a>PX_IUnknown

Türetilmiş arabirime `DoPropExchange` sahip `IUnknown`bir nesne tarafından temsil edilen bir özelliği seri hale getirmek veya başlatmak için denetiminizin üye işlevi içindeki bu işlevi çağırın.

```cpp
BOOL PX_IUnknown(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    LPUNKNOWN& pUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault = NULL);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*Punk*<br/>
Nesnenin birim değerini temsil eden arabirimini içeren bir değişkene başvuru.

*ııd*<br/>
Özellik nesnesinin hangi arabiriminin denetim tarafından kullanıldığını gösteren bir arabirim kimliği.

*pUnkVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *pUnk*tarafından başvurulan değişkenden okunur veya yazılır. *pUnkDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_long"></a><a name="px_long"></a>PX_Long

Uzun bir tür özelliğini `DoPropExchange` seri hale getirmek veya başlatmak **long**için bu işlevi denetiminizin üye işlevi içinde arayın.

```cpp
BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue);

BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue,
    long lDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*lDeğer*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*lVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *lValue*tarafından başvurulan değişkenden okunur veya yazılır. *lDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_picture"></a><a name="px_picture"></a>PX_Picture

Denetiminizin resim özelliğini `DoPropExchange` seri hale getirmek veya başlatmak için bu işlevi denetiminizin üye işlevi içinde arayın.

```cpp
BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict);

BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict,
    CPictureHolder& pictDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*Pıct*<br/>
Özelliğin depolandığı bir [CPictureHolder](../../mfc/reference/cpictureholder-class.md) nesnesine başvuru (genellikle sınıfınızın bir üye değişkeni).

*pictVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *pict*tarafından başvurulan değişkenden okunur veya yazılır. *PictDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_short"></a><a name="px_short"></a>PX_Short

Kısa türdeki bir özelliği `DoPropExchange` seri hale getirmek veya başlatmak **short**için denetiminizin üye işlevi içinde bu işlevi arayın.

```cpp
BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue);

BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue,
    short sDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*sDeğer*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*sVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *sValue*tarafından başvurulan değişkenden okunur veya yazılır. *SDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_ulong"></a><a name="px_ulong"></a>PX_ULong

**ULONG**türünden bir `DoPropExchange` özelliği seri hale getirmek veya başlatmak için bu işlevi denetiminizin üye işlevi içinde arayın.

```cpp
BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue);

BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue,
    long ulDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*ulValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*ulDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, *ulValue*tarafından başvurulan değişkenden uygun olarak okunur veya yazılır. *ulDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_ushort"></a><a name="px_ushort"></a>PX_UShort

İmzasız kısa türdeki `DoPropExchange` bir özelliği seri hale getirmek veya **unsigned short**başlatmak için denetiminizin üye işlevi içinde bu işlevi arayın.

```cpp
BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue);

BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue,
    USHORT usDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*usValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*usVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *usValue*tarafından başvurulan değişkenden okunur veya yazılır. *usDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="pxstring"></a><a name="px_string"></a>PXstring

Bir karakter dize özelliğini seri hale getirmek veya başlatmak için denetiminizin `DoPropExchange` üye işlevi içindeki bu işlevi çağırın.

```cpp
BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue);

BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue,
    CString strDefault);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*pszPropName*<br/>
Değiştirilen mülkün adı.

*strValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*strDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun olduğu şekilde *strValue*tarafından başvurulan değişkenden okunur veya yazılır. *strDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işlemi başarısız olursa kullanılır.

## <a name="px_vbxfontconvert"></a><a name="px_vbxfontconvert"></a>PX_VBXFontConvert

VBX denetiminin yazı `DoPropExchange` tipi yle ilgili özelliklerini dönüştürerek bir yazı tipi özelliğini başlatmak için denetiminizin üye işlevi içinde bu işlevi arayın.

```cpp
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine işaretçi (genellikle bir parametre olarak `DoPropExchange`geçirilir).

*Yazı tipi*<br/>
Dönüştürülmüş VBX yazı tipi ile ilgili özellikleri içeren OLE denetiminin yazı tipi özelliği.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca VBX denetimi için doğrudan yedek olarak tasarlanmış bir OLE denetimi tarafından kullanılmalıdır. Visual Basic geliştirme ortamı, karşılık gelen yedek OLE denetimini kullanmak için VBX denetimi `IDataObject::SetData` içeren bir formu dönüştürdüğünde, VBX denetiminin özellik verilerini içeren bir özellik kümesinden geçerek denetimin işlevini çağırır. Bu işlem, sırayla, denetim `DoPropExchange` işlevinin çağrılmasını neden olur. `DoPropExchange`VBX `PX_VBXFontConvert` denetiminin yazı tipiyle ilgili özelliklerini (örneğin, "FontName", "FontSize" vb. ) OLE denetiminin yazı tipi özelliğinin ilgili bileşenlerine dönüştürmek için arayabilirsiniz.

`PX_VBXFontConvert`yalnızca denetim vbx form uygulamasından dönüştürülürken çağrılmalıdır. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
