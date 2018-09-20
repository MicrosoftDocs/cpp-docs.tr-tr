---
title: OLE denetimlerinin kalıcılığı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43edcfcd7319406bb03c2b04dddcc527cdf5ab8d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395771"
---
# <a name="persistence-of-ole-controls"></a>OLE Denetimlerinin Kalıcılığı

OLE denetimlerinin bir yetenek olduğu özellik kalıcılığı (veya seri hale getirme) okumak veya özellik değerleri için ve bir dosya veya akış yazmak OLE denetim sağlar. Kapsayıcılı bir uygulama seri hale getirme sonra bile, uygulama denetimi yok bir denetimin özellik değerlerini depolamak için kullanabilirsiniz. OLE denetim özelliği değerlerinin ardından dosyasından okunabilir veya daha sonraki bir zamanda akış denetimi yeni bir örneği oluşturulur.

### <a name="persistence-of-ole-controls"></a>OLE Denetimlerinin Kalıcılığı

|||
|-|-|
|[PX_Blob](#px_blob)|İkili büyük nesne (BLOB) veri depolayan bir denetim özelliğini değiştirir.|
|[PX_Bool](#px_bool)|Bir denetim özelliği türünün birbiriyle değiştirir **BOOL**.|
|[PX_Color](#px_color)|Bir denetimin bir renk özelliğine birbiriyle değiştirir.|
|[PX_Currency](#px_currency)|Bir denetim özelliği türünün birbiriyle değiştirir **CY**.|
|[PX_DataPath](#px_datapath)|Bir denetim özelliği türünün birbiriyle değiştirir `CDataPathProperty`.|
|[PX_Double](#px_double)|Bir denetim özelliği türünün birbiriyle değiştirir **çift**.|
|[PX_Font](#px_font)|Bir denetimin bir yazı tipi özelliğini değiştirir.|
|[PX_Float](#px_float)|Bir denetim özelliği türünün birbiriyle değiştirir **float**.|
|[Px_ıunknown](#px_iunknown)|Bir denetim özelliği Tanımsız Tür birbiriyle değiştirir.|
|[PX_Long](#px_long)|Bir denetim özelliği türünün birbiriyle değiştirir **uzun**.|
|[PX_Picture](#px_picture)|Bir denetimin resim özelliği birbiriyle değiştirir.|
|[PX_Short](#px_short)|Bir denetim özelliği türünün birbiriyle değiştirir **kısa**.|
|[PX_ULong](#px_ulong)|Bir denetim özelliği türünün birbiriyle değiştirir **ULONG**.|
|[PX_UShort](#px_ushort)|Bir denetim özelliği türünün birbiriyle değiştirir **USHORT**.|
|[PXstring](#px_string)|Bir karakter dizesi denetim özelliğini değiştirir.|
|[PX_VBXFontConvert](#px_vbxfontconvert)|VBX denetimin yazı tipi ilgili özellikler bir OLE denetim yazı tipi özelliğini değiştirir.|

Ayrıca, `AfxOleTypeMatchGuid` genel işlev bir TYPEDESC ve belirli bir GUID arasında bir eşleşme için test etmek için sağlanır.

##  <a name="px_blob"></a>  PX_Blob

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya ikili büyük nesne (BLOB) veri depolayan bir özelliğini başlatmak için üye işlevi.

```
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*hBlob*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*hBlobDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya değişkeni tarafından başvurulan yazılan *hBlob*uygun şekilde. Bu değişken NULL olarak ilk kez çağrılmadan önce başlatılmalıdır `PX_Blob` ilk kez (genellikle, bu denetimin oluşturucuda yapılabilir). Varsa *hBlobDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin başlatma veya seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

Tutamaçları *hBlob* ve *hBlobDefault* aşağıdakileri içeren bellek bloğuna bakın:

- Bayt cinsinden uzunluğu, aşağıdaki ikili veri içeren bir DWORD hemen bunun ardından

- Gerçek ikili veriler içeren bir bellek bloğu.

Unutmayın `PX_Blob` Windows kullanarak belleği ayırır [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) BLOB türü özellikleri yüklenirken API. Bu bellek boşaltma için sorumlu olursunuz. Bu nedenle, yok edici denetiminizin çağırmalıdır [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) herhangi bir BLOB türü özelliği, denetim için ayrılan belleği boşaltmak için tutamaçları yukarı.

##  <a name="px_bool"></a>  PX_Bool

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` seri hale getirmek ya da BOOL türünde bir özellik başlatmak için üye işlevi.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*bDeğer*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*bVarsayılan*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya değişkeni tarafından başvurulan yazılan *bDeğer*uygun şekilde. Varsa *bVarsayılan* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_color"></a>  PX_Color

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya OLE_COLOR türünde bir özellik başlatmak için üye işlevi.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*clrValue*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*clrDefault*<br/>
Varsayılan denetim geliştiricisi tarafından tanımlanan bir özellik için değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya değişkeni tarafından başvurulan yazılan *clrValue*uygun şekilde. Varsa *clrDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_currency"></a>  PX_Currency

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya vlastnost typu başlatmak için üye işlevi **para birimi**.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*cyValue*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*cyDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya değişkeni tarafından başvurulan yazılan *cyValue*uygun şekilde. Varsa *cyDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_datapath"></a>  PX_DataPath

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya türünde bir veri yolu özellik başlatmak için üye işlevi [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md).

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*dataPathProperty*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Veri yolu özellikleri zaman uyumsuz denetim özelliği uygular. Özelliğin değerini okumak veya değişkeni tarafından başvurulan yazılan *dataPathProperty*uygun şekilde.

##  <a name="px_double"></a>  PX_Double

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya vlastnost typu başlatmak için üye işlevi **çift**.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*doubleValue*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*doubleDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya tarafından başvurulan değişken yazılan *doubleValue*uygun şekilde. Varsa *doubleDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_font"></a>  PX_Font

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya türü yazı tipi özelliğini başlatmak için üye işlevi.

```
BOOL PX_Font(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC FAR* pFontDesc = NULL,
    LPFONTDISP pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*Yazı tipi*<br/>
Bir başvuru bir `CFontHolder` font özelliği içeren nesne.

*pFontDesc*<br/>
Bir işaretçi bir `FONTDESC` durumda font özelliği varsayılan durumu başlatılırken kullanılacak değerler içeren yapıya burada *pFontDispAmbient* null.

*pFontDispAmbient*<br/>
Bir işaretçi `IFontDisp` font özelliğinin varsayılan durum başlatılırken kullanmak için bir yazı tipi arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri okuma veya yazma `font`, `CFontHolder` başvurusu, uygun olduğunda. Varsa *pFontDesc* ve *pFontDispAmbient* belirtilirse, bunlar özelliğin varsayılan değeri, gerektiğinde başlatmak için kullanılır. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değerler kullanılır. Genellikle, NULL geçirmek *pFontDesc* ve tarafından döndürülen değeri, ortam `COleControl::AmbientFont` için *pFontDispAmbient*. Yazı tipi nesnesi tarafından döndürülen Not `COleControl::AmbientFont` yapılan bir çağrıyla serbest bırakılması gereken `IFontDisp::Release` üye işlevi.

##  <a name="px_float"></a>  PX_Float

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya vlastnost typu başlatmak için üye işlevi **float**.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*floatValue*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*floatDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya tarafından başvurulan değişken yazılan *floatValue*uygun şekilde. Varsa *floatDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_iunknown"></a>  Px_ıunknown

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya sahip nesne tarafından temsil edilen bir özelliğini başlatmak için üye işlevi bir `IUnknown`-arabirimi türetilir.

```
BOOL PX_IUnknown(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    LPUNKNOWN& pUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault = NULL);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*pUnk*<br/>
Özelliğinin değeri temsil eden nesnenin arabirimi içeren bir değişken başvuru.

*IID*<br/>
Özellik nesnenin hangi arabirimi denetim tarafından kullanılan belirten bir arabirim kimliği.

*pUnkDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya tarafından başvurulan değişken yazılan *pUnk*uygun şekilde. Varsa *pUnkDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_long"></a>  PX_Long

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya vlastnost typu başlatmak için üye işlevi **uzun**.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*lValue*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*lDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya tarafından başvurulan değişken yazılan *lValue*uygun şekilde. Varsa *lDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_picture"></a>  PX_Picture

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya resim özelliği denetiminizin başlatmak için üye işlevi.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*PICT*<br/>
Başvuru bir [CPictureHolder](../../mfc/reference/cpictureholder-class.md) özelliği depolandığı nesne (genellikle, sınıfın üye değişkeni).

*pictDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya tarafından başvurulan değişken yazılan *PICT*uygun şekilde. Varsa *pictDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_short"></a>  PX_Short

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya vlastnost typu başlatmak için üye işlevi **kısa**.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*sValue*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*sDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya tarafından başvurulan değişken yazılan *sValue*uygun şekilde. Varsa *sDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_ulong"></a>  PX_ULong

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya vlastnost typu başlatmak için üye işlevi **ULONG**.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*ulValue*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*ulDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya tarafından başvurulan değişken yazılan *ulValue*uygun şekilde. Varsa *ulDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_ushort"></a>  PX_UShort

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya vlastnost typu başlatmak için üye işlevi **işaretsiz**.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*usValue*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*usDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya tarafından başvurulan değişken yazılan *usValue*uygun şekilde. Varsa *usDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_string"></a>  PXstring

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` serileştirmek veya bir karakter dize özelliğini başlatmak için üye işlevi.

```
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
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*strValue*<br/>
Başvuru özelliği depolandığı değişken (genellikle, sınıfın üye değişkeni).

*strDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değerini okumak veya tarafından başvurulan değişken yazılan *strValue*uygun şekilde. Varsa *strDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.

##  <a name="px_vbxfontconvert"></a>  PX_VBXFontConvert

Denetiminizin içinde bu işlevi çağırın `DoPropExchange` VBX denetimin yazı tipi ilgili özellikler dönüştürerek bir yazı tipi özelliğini başlatmak için üye işlevi.

```
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>Parametreler

*pPX*<br/>
İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).

*Yazı tipi*<br/>
Yazı tipi dönüştürülmüş VBX yazı tipi ile ilgili özellikleri içeren OLE denetim özelliği.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, VBX denetimi doğrudan bir ardılı olarak tasarlanmış bir OLE denetimi tarafından kullanılmalıdır. Visual Basic geliştirme ortamını karşılık gelen değişiklik OLE denetimi kullanmak için VBX denetimi içeren bir form dönüştürülürken, denetimin göndereceği `IDataObject::SetData` işlevini VBX denetimin özellik verileri içeren bir özellik kümesi. Bu işlem, denetimin neden `DoPropExchange` çağrılacak işlev. `DoPropExchange` çağırabilirsiniz `PX_VBXFontConvert` VBX denetimin yazı tipi ilgili özellikler dönüştürmek için (örneğin, "FontName," "FontSize" vb.) içine OLE denetimin yazı tipi özelliğine karşılık gelen bileşenleri.

`PX_VBXFontConvert` Denetim aslında bir VBX form uygulamasından dönüştürülen zaman yalnızca çağrılmalıdır. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
