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
ms.openlocfilehash: e84e26bae83bd131b53d10e4561ddb60854a8a5e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378340"
---
# <a name="persistence-of-ole-controls"></a>OLE Denetimlerinin Kalıcılığı
OLE denetimlerinin bir yetenek olduğu özelliği kalıcılığı (veya seri hale getirme) okumak veya özellik değerleri için ve bir dosya veya akış yazmak OLE denetimi sağlar. Bir kapsayıcı uygulama serileştirme bile uygulama denetimi yok sonra bir denetimin özellik değerlerini depolamak için kullanabilirsiniz. OLE denetim özellik değerlerinin sonra dosyasından okunabilir veya akış denetiminin yeni örneği olduğunda daha sonraki bir zamanda oluşturulur.  
  
### <a name="persistence-of-ole-controls"></a>OLE Denetimlerinin Kalıcılığı  
  
|||  
|-|-|  
|[PX_Blob](#px_blob)|İkili büyük nesne (BLOB) verilerini depolayan bir denetim özelliğini değiş tokuş eder.|  
|[PX_Bool](#px_bool)|Türünde bir denetim özelliği alış verişleri **BOOL**.|  
|[PX_Color](#px_color)|Color özelliği bir denetimin değiş tokuş eder.|  
|[PX_Currency](#px_currency)|Türünde bir denetim özelliği alış verişleri **CY**.|  
|[PX_DataPath](#px_datapath)|Türünde bir denetim özelliği alış verişleri `CDataPathProperty`.|  
|[PX_Double](#px_double)|Türünde bir denetim özelliği alış verişleri **çift**.|  
|[PX_Font](#px_font)|Bir denetimin font özelliği değiş tokuş eder.|  
|[PX_Float](#px_float)|Türünde bir denetim özelliği alış verişleri **float**.|  
|[Px_ıunknown](#px_iunknown)|Tanımsız türünde bir denetim özelliği değiş tokuş eder.|  
|[PX_Long](#px_long)|Türünde bir denetim özelliği alış verişleri **uzun**.|  
|[PX_Picture](#px_picture)|Bir denetimin bir resim özelliğini değiş tokuş eder.|  
|[PX_Short](#px_short)|Türünde bir denetim özelliği alış verişleri **kısa**.|  
|[PX_ULong](#px_ulong)|Türünde bir denetim özelliği alış verişleri **ULONG**.|  
|[PX_UShort](#px_ushort)|Türünde bir denetim özelliği alış verişleri **USHORT**.|  
|[PXstring](#px_string)|Bir karakter dizesi denetim özelliğini değiş tokuş eder.|  
|[PX_VBXFontConvert](#px_vbxfontconvert)|VBX denetimin yazı tipi ilgili Özellikler OLE denetim font özelliği değiş tokuş eder.|  
  
 Ayrıca, `AfxOleTypeMatchGuid` genel işlevi arasında bir eşleşme için test etmek için sağlanan bir `TYPEDESC` ve belirli bir GUID.  
  
##  <a name="px_blob"></a>  PX_Blob  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya ikili büyük nesne (BLOB) verilerini depolayan bir özellik başlatmak için üye işlevi.  
  
```  
 
BOOL  
PX_Blob(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    HGLOBAL& 
hBlob  ,  
    HGLOBAL 
hBlobDefault  
= NULL);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `hBlob`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 `hBlobDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya başvurduğu değişkenine yazılmış `hBlob`uygun şekilde. Bu değişken için başlatılması **NULL** başlangıçta çağırmadan önce `PX_Blob` ilk kez (genellikle, bu denetimin oluşturucuda yapılabilir). Varsa `hBlobDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin başlatma veya seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
 Tanıtıcıları `hBlob` ve `hBlobDefault` aşağıdakileri içeren bellek bloğuna bakın:  
  
-   A `DWORD` , bayt cinsinden uzunluğu izler, ikili veri içeren göre hemen ardından  
  
-   Gerçek ikili veriler içeren bellek bloğu.  
  
 Unutmayın `PX_Blob` Windows kullandığı bellek ayırır [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) BLOB türü özellikleri yüklenirken API. Bu bellek boşaltma için sorumlu. Bu nedenle, denetiminizin yıkıcı çağırmalıdır [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) herhangi bir BLOB türü özelliğin denetiminize ayrılan belleği boşaltmak için tanıtıcıları yukarı.  
  
##  <a name="px_bool"></a>  PX_Bool  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya türünde bir özellik başlatmak için üye işlevi **BOOL**.  
  
```  
 
BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& bValue);

BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& 
bValue  ,  
    BOOL bDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `bValue`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 `bDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya başvurduğu değişkenine yazılmış `bValue`uygun şekilde. Varsa `bDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_color"></a>  PX_Color  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya türünde bir özellik başlatmak için üye işlevi **OLE_COLOR**.  
  
```  
 
BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& 
clrValue  ,  
    OLE_COLOR 
clrDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `clrValue`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 `clrDefault`  
 Denetim geliştirici tarafından tanımlanan varsayılan bir özellik için değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya başvurduğu değişkenine yazılmış `clrValue`uygun şekilde. Varsa `clrDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_currency"></a>  PX_Currency  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya türünde bir özellik başlatmak için üye işlevi **para birimi**.  
  
```  
 
BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& cyValue);

BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& 
cyValue  ,  
    CY cyDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `cyValue`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 `cyDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya başvurduğu değişkenine yazılmış `cyValue`uygun şekilde. Varsa `cyDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_datapath"></a>  PX_DataPath  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya türünde bir veri yolu özellik başlatmak için üye işlevi [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md).  
  
```  
 
BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    LPCTSTR 
pszPropName,  
    CDataPathProperty& dataPathProperty);

BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    CDataPathProperty& dataPathProperty);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `dataPathProperty`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri yolu özellikleri zaman uyumsuz denetim özelliklerini uygulayın. Özelliğin değeri okunamıyor veya başvurduğu değişkenine yazılmış `dataPathProperty`uygun şekilde.  
  
##  <a name="px_double"></a>  PX_Double  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya türünde bir özellik başlatmak için üye işlevi **çift**.  
  
```  
 
BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& doubleValue);

BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& 
doubleValue  ,  
    double doubleDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `doubleValue`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 `doubleDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya deftere başvurduğu değişkenine `doubleValue`uygun şekilde. Varsa `doubleDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_font"></a>  PX_Font  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya bir özellik türü yazı tipinin başlatmak için üye işlevi.  
  
```  
 
BOOL  
PX_Font(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CFontHolder& 
font  ,  
    const 
FONTDESC  
FAR* 
pFontDesc  
= 
NULL,  
    LPFONTDISP 
pFontDispAmbient  
= NULL);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `font`  
 Bir başvuru bir `CFontHolder` font özelliği içeren nesne.  
  
 `pFontDesc`  
 Bir işaretçi bir **FONTDESC** durumda font özelliği varsayılan durumunu başlatılırken kullanılacak değerleri içeren yapısını nerede `pFontDispAmbient` olan **NULL**.  
  
 `pFontDispAmbient`  
 Bir işaretçi **IFontDisp** font özelliği varsayılan durumunu başlatılırken kullanılacak yazı tipinin arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okuma veya yazma `font`, `CFontHolder` başvuru, uygun olduğunda. Varsa `pFontDesc` ve `pFontDispAmbient` belirtilirse, bunlar özelliğin varsayılan değeri, gerektiğinde başlatmak için kullanılır. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değerler kullanılır. Genellikle, geçirdiğiniz **NULL** için `pFontDesc` ve tarafından döndürülen değeri, ortam `COleControl::AmbientFont` için `pFontDispAmbient`. Yazı tipi nesnesi tarafından döndürülen Not `COleControl::AmbientFont` çağrısı ile serbest bırakılması gereken **IFontDisp::Release** üye işlevi.  
  
##  <a name="px_float"></a>  PX_Float  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya türünde bir özellik başlatmak için üye işlevi **float**.  
  
```  
 
BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& floatValue);

BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& 
floatValue  ,  
    float floatDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `floatValue`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 `floatDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya deftere başvurduğu değişkenine `floatValue`uygun şekilde. Varsa `floatDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_iunknown"></a>  Px_ıunknown  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya bir nesne sağlayarak temsil edilen bir özellik başlatmak için üye işlevi bir **IUnknown**-arabirimi türetilmiş.  
  
```  
 
BOOL  
PX_IUnknown(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    LPUNKNOWN& 
pUnk  ,  
    REFIID 
iid  ,  
    LPUNKNOWN 
pUnkDefault  
= NULL);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 *pUnk*  
 Özelliğin değerini temsil eden nesne arabiriminin içeren bir değişken başvuru.  
  
 `iid`  
 Hangi arabirimi özelliği nesnesinin belirten bir arabirim kimliği denetim tarafından kullanılır.  
  
 `pUnkDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya deftere başvurduğu değişkenine *pUnk*uygun şekilde. Varsa `pUnkDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_long"></a>  PX_Long  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya türünde bir özellik başlatmak için üye işlevi **uzun**.  
  
```  
 
BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& lValue);

BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& 
lValue  ,  
    long lDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `lValue`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 `lDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya deftere başvurduğu değişkenine `lValue`uygun şekilde. Varsa `lDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_picture"></a>  PX_Picture  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya resim özelliği denetiminizin başlatmak için üye işlevi.  
  
```  
 
BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& pict);

BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& 
pict  ,  
    CPictureHolder& pictDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `pict`  
 Başvuru bir [CPictureHolder](../../mfc/reference/cpictureholder-class.md) özelliği depolandığı nesne (genellikle sınıfınızın üye değişkeni).  
  
 `pictDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya deftere başvurduğu değişkenine `pict`uygun şekilde. Varsa `pictDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_short"></a>  PX_Short  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya türünde bir özellik başlatmak için üye işlevi **kısa**.  
  
```  
 
BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& sValue);

BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& 
sValue  ,  
    short sDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `sValue`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 `sDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya deftere başvurduğu değişkenine `sValue`uygun şekilde. Varsa `sDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_ulong"></a>  PX_ULong  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya türünde bir özellik başlatmak için üye işlevi **ULONG**.  
  
```  
 
BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& ulValue);

BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& 
ulValue  ,  
    long ulDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `ulValue`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 `ulDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya deftere başvurduğu değişkenine `ulValue`uygun şekilde. Varsa `ulDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_ushort"></a>  PX_UShort  
 Bu işlev, denetimin içinde arama `DoPropExchange` serileştirmek veya türünde bir özellik başlatmak için üye işlevi `unsigned` **kısa**.  
  
```  
 
BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& usValue);

BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& 
usValue  ,  
    USHORT usDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 *usValue*  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 *usDefault*  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya deftere başvurduğu değişkenine *usValue*uygun şekilde. Varsa *usDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_string"></a>  PXstring  
 Bu işlev, denetimin içinde arama **DoPropExchange** üye işlevi serileştirmek veya bir karakter dizesi özelliği başlatılamadı.  
  
```  
 
BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& strValue);

BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& 
strValue  ,  
    CString strDefault);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `strValue`  
 Özellik depolandığı değişken başvuru (genellikle sınıfınızın üye değişkeni).  
  
 `strDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya deftere başvurduğu değişkenine `strValue`uygun şekilde. Varsa `strDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin seri hale getirme işlemi herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
##  <a name="px_vbxfontconvert"></a>  PX_VBXFontConvert  
 Bu işlev, denetimin içinde arama `DoPropExchange` üye işlevi VBX denetimin yazı tipi ilgili özellikler dönüştürerek font özelliği başlatılamadı.  
  
```  
 
BOOL  
PX_VBXFontConvert(
    CPropExchange* 
pPX  ,  
    CFontHolder& font);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pPX`  
 İşaretçi [CPropExchange](../../mfc/reference/cpropexchange-class.md) nesne (genellikle bir parametre olarak geçirilen `DoPropExchange`).  
  
 `font`  
 Font özelliği OLE denetiminin yazı tipi ilgili dönüştürülmüş VBX özellikler içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, doğrudan yerini alacak yeni bir VBX denetimi için tasarlanmış bir OLE denetimi tarafından kullanılmalıdır. Visual Basic geliştirme ortamını karşılık gelen değiştirme OLE denetimi kullanmak için bir VBX denetimi içeren bir form dönüştürdüğünde, denetimin çağıracak **IDataObject::SetData** işlevi, bir özellik bilgilerinde, Ayarla VBX denetimin özelliği veri içerir. Bu işlem, denetimin sırayla neden olan `DoPropExchange` çağrılacak işlev. `DoPropExchange` çağırabilirsiniz `PX_VBXFontConvert` VBX denetimin yazı tipi ilgili özellikler dönüştürmek için (örneğin, "FontName," "FontSize," vb.) OLE denetimin yazı tipi özelliğine karşılık gelen bileşenlere.  
  
 `PX_VBXFontConvert` Denetim gerçekte bir VBX form uygulamasından dönüştürülecek olduğunda yalnızca çağrılmalıdır. Örneğin:  
  
 [!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]  
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
