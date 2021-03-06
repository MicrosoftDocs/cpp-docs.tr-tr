---
description: 'Daha fazla bilgi edinin: OLE denetimlerinin kalıcılığı'
title: OLE Denetimlerinin Kalıcılığı
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
ms.openlocfilehash: 8c0ee5b81ffd21953c3ed9bcbc21a9ae30979b49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218985"
---
# <a name="persistence-of-ole-controls"></a>OLE Denetimlerinin Kalıcılığı

OLE denetimlerinin bir özelliği, OLE denetiminin bir dosya veya akışa ait özellik değerlerini okumasına veya yazmasına izin veren özellik kalıcılığı (veya serileştirme). Bir kapsayıcı uygulaması, uygulamanın denetimi yok saydıktan sonra bile bir denetimin özellik değerlerini depolamak için serileştirme kullanabilir. Daha sonra denetimin yeni bir örneği oluşturulduğunda, OLE denetiminin özellik değerleri dosyadan veya akıştan okunabilir.

### <a name="persistence-of-ole-controls"></a>OLE Denetimlerinin Kalıcılığı

|Ad|Açıklama|
|-|-|
|[PX_Blob](#px_blob)|İkili büyük nesne (BLOB) verilerini depolayan bir denetim özelliğini değiş tokuş eder.|
|[PX_Bool](#px_bool)|**Bool** türünde bir denetim özelliği değiş tokuş eder.|
|[PX_Color](#px_color)|Bir denetimin Color özelliğini değiş tokuş eder.|
|[PX_Currency](#px_currency)|**Cy** türünde bir denetim özelliği değiş tokuş eder.|
|[PX_DataPath](#px_datapath)|Türünde bir denetim özelliği değiş tokuş eder `CDataPathProperty` .|
|[PX_Double](#px_double)|Türünde bir denetim özelliği değiş tokuş eder **`double`** .|
|[PX_Font](#px_font)|Bir denetimin yazı tipi özelliğini değiş tokuş eder.|
|[PX_Float](#px_float)|Türünde bir denetim özelliği değiş tokuş eder **`float`** .|
|[PX_IUnknown](#px_iunknown)|Tanımsız türdeki bir denetim özelliğini değiş tokuş eder.|
|[PX_Long](#px_long)|Türünde bir denetim özelliği değiş tokuş eder **`long`** .|
|[PX_Picture](#px_picture)|Bir denetimin resim özelliğini değiş tokuş eder.|
|[PX_Short](#px_short)|Türünde bir denetim özelliği değiş tokuş eder **`short`** .|
|[PX_ULong](#px_ulong)|**Ulong** türünde bir denetim özelliği değiş tokuş eder.|
|[PX_UShort](#px_ushort)|**Ushort** türünde bir denetim özelliği değiş tokuş eder.|
|[PXstring](#px_string)|Bir karakter dizesi denetim özelliği değiş tokuş eder.|
|[PX_VBXFontConvert](#px_vbxfontconvert)|Bir VBX denetiminin yazı tipi ile ilgili özelliklerini OLE denetim yazı tipi özelliğine dönüştürür.|

Ayrıca, `AfxOleTypeMatchGuid` genel Işlev TYPEDESC ve verilen BIR GUID arasındaki eşleşmeyi test etmek için sağlanır.

## <a name="px_blob"></a><a name="px_blob"></a> PX_Blob

`DoPropExchange`İkili büyük nesne (blob) verilerini depolayan bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizde bu işlevi çağırın.

```cpp
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*hBlob*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*hBlobDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, *hBlob* tarafından başvurulan değişkene uygun şekilde okunacak veya buradan yazılacak. Bu değişken başlangıçta ilk kez çağrılmadan önce NULL olarak başlatılmalıdır `PX_Blob` (genellikle, denetimin oluşturucusunda bu yapılabilir). *HBlobDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin başlatılması veya serileştirme işleminin başarısız olması durumunda kullanılır.

*HBlob* ve *hBlobDefault* tanıtıcıları, aşağıdakileri içeren bir bellek bloğuna başvurur:

- Aşağıdaki ikili verilerin uzunluğunu bayt cinsinden, ardından hemen

- Gerçek ikili verileri içeren bir bellek bloğu.

`PX_Blob`BLOB türü özellikleri yüklenirken Windows [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) API 'sini kullanarak bellek ayıracağına unutmayın. Bu belleği boşaltmaktan siz sorumlusunuz. Bu nedenle, denetiminizin yıkıcısında herhangi bir BLOB türü özellik tanıtıcısında [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) çağrısı yapmanız gerekir.

## <a name="px_bool"></a><a name="px_bool"></a> PX_Bool

`DoPropExchange`Bool türünde bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın.

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*bDeğer*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*bDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, doğru şekilde *bValue* tarafından başvurulan değişkene okunacak veya yazılacak. *BDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_color"></a><a name="px_color"></a> PX_Color

`DoPropExchange`OLE_COLOR türünde bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın.

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*clrValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*clrDefault*<br/>
Özellik için denetim geliştiricisi tarafından tanımlanan varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde, *clrvalue* tarafından başvurulan değişkene göre okunacak veya bu değişkene yazılacak. Eğer *clrDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_currency"></a><a name="px_currency"></a> PX_Currency

`DoPropExchange` **Currency** türünde bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizde bu işlevi çağırın.

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*cyValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*cyDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde, *cyvalue* tarafından başvurulan değişkene okunacak veya bu değişkene yazılacak. *CyDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_datapath"></a><a name="px_datapath"></a> PX_DataPath

`DoPropExchange` [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)türünde bir veri yolu özelliğini seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın.

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*dataPathProperty*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Veri yolu özellikleri zaman uyumsuz denetim özellikleri uygular. Özelliğin değeri, uygun şekilde *Datapathproperty* tarafından başvurulan değişkene okunacak veya bu değişkene yazılacak.

## <a name="px_double"></a><a name="px_double"></a> PX_Double

`DoPropExchange`Türü bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın **`double`** .

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*doubleValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*doubleDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde *DoubleValue* tarafından başvurulan değişkene göre okunurdur veya yazılır. *DoubleDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_font"></a><a name="px_font"></a> PX_Font

`DoPropExchange`Yazı tipi türünde bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın.

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*Yazý*<br/>
`CFontHolder`Yazı tipi özelliğini içeren bir nesneye başvuru.

*pFontDesc*<br/>
`FONTDESC` *Pfontdispambuya* 'nın null olduğu durumlarda, Font özelliğinin varsayılan durumunu başlatırken kullanılacak değerleri içeren bir yapıya yönelik işaretçi.

*Pfontdispambun*<br/>
`IFontDisp`Yazı tipi özelliğinin varsayılan durumunu başlatırken kullanılacak yazı tipinin arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, `font` uygun olduğunda bir başvuruya göre okunurdur veya yazılır `CFontHolder` . *PFontDesc* ve *Pfontdispambköpek* belirtilmişse, gerektiğinde özelliğin varsayılan değerini başlatmak için kullanılır. Bu değerler, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır. Genellikle, *pFontDesc* için null ve `COleControl::AmbientFont` *Pfontdispambun* tarafından döndürülen çevresel değer ile geçiş yapabilirsiniz. Tarafından döndürülen yazı tipi nesnesinin, `COleControl::AmbientFont` üye işlevine yapılan bir çağrı tarafından yayımlanması gerektiğini unutmayın `IFontDisp::Release` .

## <a name="px_float"></a><a name="px_float"></a> PX_Float

`DoPropExchange`Türü bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın **`float`** .

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*floatValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*floatDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde, *Floatvalue* tarafından başvurulan değişkene göre okunurdur veya yazılır. *FloatDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_iunknown"></a><a name="px_iunknown"></a> PX_IUnknown

`DoPropExchange`Türetilmiş arabirime sahip bir nesne tarafından temsil edilen bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizde bu işlevi çağırın `IUnknown` .

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*pUnk dili*<br/>
Özelliğin değerini temsil eden nesnesinin arabirimini içeren bir değişkene başvuru.

*'si*<br/>
Denetim tarafından hangi özellik nesnesinin arabiriminin kullanıldığını gösteren bir arabirim KIMLIĞI.

*pUnkDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde, *punk* tarafından başvurulan değişkene göre okunurdur veya yazılır. *PUnkDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_long"></a><a name="px_long"></a> PX_Long

`DoPropExchange`Türü bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın **`long`** .

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*lValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*lDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde *lValue* tarafından başvurulan değişkene göre okunurdur veya yazılır. *LDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_picture"></a><a name="px_picture"></a> PX_Picture

`DoPropExchange`Denetiminizin bir resim özelliğini seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın.

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*resim*<br/>
Özelliğin depolandığı bir [Cpicturetutucusu](../../mfc/reference/cpictureholder-class.md) nesnesine başvuru (genellikle sınıfınızın bir üye değişkeni).

*pictDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde, *PICT* tarafından başvurulan değişkene göre okunurdur veya yazılır. *PictDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_short"></a><a name="px_short"></a> PX_Short

`DoPropExchange`Türü bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın **`short`** .

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*sValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*sDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde *Svalue* tarafından başvurulan değişkene göre okunurdur veya yazılır. Eğer *sDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_ulong"></a><a name="px_ulong"></a> PX_ULong

`DoPropExchange` **Ulong** türünde bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın.

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*ulValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*ulDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde *Ulvalue* tarafından başvurulan değişkene göre okunurdur veya yazılır. *UlDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_ushort"></a><a name="px_ushort"></a> PX_UShort

`DoPropExchange`Türü bir özelliği seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın **`unsigned short`** .

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*usValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*usDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde *Usvalue* tarafından başvurulan değişkene göre okunurdur veya yazılır. *UsDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="pxstring"></a><a name="px_string"></a> PXstring

`DoPropExchange`Bir karakter dizesi özelliğini seri hale getirmek veya başlatmak için denetimin üye işlevinizin içinde bu işlevi çağırın.

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*strValue*<br/>
Özelliğin depolandığı değişkene başvuru (genellikle sınıfınızın bir üye değişkeni).

*strDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde *strValue* tarafından başvurulan değişkene göre okunurdur veya yazılır. *StrDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme işleminin başarısız olması durumunda kullanılır.

## <a name="px_vbxfontconvert"></a><a name="px_vbxfontconvert"></a> PX_VBXFontConvert

Bir `DoPropExchange` VBX denetiminin yazı tipine ilişkin özellikleri dönüştürerek bir yazı tipi özelliğini başlatmak için bu işlevi denetiminizin member işlevinde çağırın.

```cpp
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) nesnesine yönelik işaretçi (genellikle bir parametre olarak geçirilir `DoPropExchange` ).

*Yazý*<br/>
Dönüştürülmüş VBX yazı tipi ile ilgili özellikleri içeren OLE denetiminin yazı tipi özelliği.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca bir VBX denetimi için doğrudan değiştirme olarak tasarlanan bir OLE denetimi tarafından kullanılmalıdır. Visual Basic geliştirme ortamı, bir VBX denetimi içeren bir formu karşılık gelen değiştirme OLE denetimini kullanacak şekilde dönüştürdüğünde, `IDataObject::SetData` VBX denetiminin özellik verilerini içeren bir özellik kümesini geçirerek denetimin işlevini çağırır. Bu işlem, sırasıyla denetimin `DoPropExchange` işlevinin çağrılmasına neden olur. `DoPropExchange` , `PX_VBXFontConvert` VBX denetiminin yazı tipi ile ilgili özelliklerini (örneğin, "FontName," "FontSize" vb.) OLE denetiminin yazı tipi özelliğinin karşılık gelen bileşenlerine dönüştürmek için çağrı yapabilir.

`PX_VBXFontConvert` yalnızca denetim gerçekten bir VBX form uygulamasından dönüştürüldüğünde çağrılmalıdır. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
