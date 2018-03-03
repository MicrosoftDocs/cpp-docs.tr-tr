---
title: "CPropExchange sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
dev_langs:
- C++
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5deea89ccc9c340537b1b33563455ea91b46fe8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cpropexchange-class"></a>CPropExchange sınıfı
OLE denetimleri için Kalıcılık uyarlamasını destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|İkili büyük nesne (BLOB) özelliği değiş tokuş eder.|  
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Font özelliği değiş tokuş eder.|  
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|Bir özelliği bir denetim ve bir dosya arasında değiş tokuş eder.|  
|[CPropExchange::ExchangeProp](#exchangeprop)|Yerleşik türler özelliklerini değiş tokuş eder.|  
|[CPropExchange::ExchangeVersion](#exchangeversion)|OLE denetimi sürüm numarasını değiş tokuş eder.|  
|[CPropExchange::GetVersion](#getversion)|OLE denetimi sürüm numarasını alır.|  
|[CPropExchange::IsAsynchronous](#isasynchronous)|Özellik alışverişleri zaman uyumsuz olarak Bitti durumunda belirler.|  
|[CPropExchange::IsLoading](#isloading)|Özellikler yükleniyor olup olmadığını gösterir denetimine atanan veya ondan kaydedildi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CPropExchange`bir taban sınıfı yok.  
  
 İçeriği ve özellik exchange yönünü belirler.  
  
 Genellikle Denetim ve bir orta arasında özelliklerini tarafından temsil edilen denetim durumu bilgileri exchange Kalıcılık olur.  
  
 Framework türetilmiş bir nesne oluşturur `CPropExchange` bir OLE denetimin özelliklerini gelen yüklenecek olan ne zaman bildirim ya da kalıcı için saklı depolama.  
  
 Çerçeve işaretçisi için geçirir `CPropExchange` denetiminizin nesnesine `DoPropExchange` işlevi. Denetim için Denetim starter dosyaları oluşturmak için sihirbaz kullandıysanız `DoPropExchange` işlev çağrıları `COleControl::DoPropExchange`. Taban sınıfı sürüm denetim stok özelliklerini kullanmaz; türetilen sınıfın sürüme denetiminize eklediğiniz exchange özellikleri değiştirin.  
  
 `CPropExchange`bir denetimin özelliklerini serileştirmek veya bir denetimin özellikleri yükleme ya da bir denetimin oluşturulmasını etkileyen başlatmak için kullanılabilir. `ExchangeProp` Ve `ExchangeFontProp` üye işlevlerini `CPropExchange` özelliklerini depolamak ve bunları farklı medyadan yükleme imkanınız olur.  
  
 Kullanma hakkında daha fazla bilgi için `CPropExchange`, makaleye bakın [MFC ActiveX denetimleri: özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CPropExchange`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h  
  
##  <a name="exchangeblobprop"></a>CPropExchange::ExchangeBlobProp  
 İkili büyük nesne (BLOB) verilerini depolayan bir özellik serileştirir.  
  
```  
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,  
    HGLOBAL* phBlob,  
    HGLOBAL hBlobDefault = NULL) = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `phBlob`  
 Özellik depolandığı işaret eden bir değişken işaretçisine (değişkenidir genellikle sınıfınız üyesi).  
  
 `hBlobDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliğin değeri okunamıyor veya deftere için uygun şekilde tarafından başvurulan değişken `phBlob`. Varsa `hBlobDefault` belirtilirse, bu kullanılacak özelliğin varsayılan değeri olarak. Denetimin serileştirme herhangi bir nedenle başarısız olursa, bu değer kullanılır.  
  
 İşlevler **CArchivePropExchange::ExchangeBlobProp**, **CResetPropExchange::ExchangeBlobProp**, ve **CPropsetPropExchange::ExchangeBlobProp** geçersiz kıl Bu saf sanal işlev.  
  
##  <a name="exchangefontprop"></a>CPropExchange::ExchangeFontProp  
 Font özelliği bir depolama ortamına ve denetim arasında değiş tokuş eder.  
  
```  
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,  
    CFontHolder& font,  
    const FONTDESC* pFontDesc,  
    LPFONTDISP pFontDispAmbient) = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `font`  
 Bir başvuru bir [CFontHolder](../../mfc/reference/cfontholder-class.md) font özelliği içeren nesne.  
  
 `pFontDesc`  
 Bir işaretçi bir [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782) font özelliği varsayılan durumunu başlatma için değerleri içeren yapısını zaman `pFontDispAmbient` olan **NULL**.  
  
 `pFontDispAmbient`  
 Bir işaretçi **IFontDisp** font özelliği varsayılan durumunu başlatmak için kullanılacak yazı tipinin arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetime font özelliği ortamından yüklenirken, yazı tipinin özellikleri ortamından alınır ve `CFontHolder` tarafından başvurulan nesne `font` bunlarla başlatılır. Font özelliği depolanıyorsa, yazı tipi nesnesindeki özellikleri Orta yazılır.  
  
 İşlevler **CArchivePropExchange::ExchangeFontProp**, **CResetPropExchange::ExchangeFontProp**, ve **CPropsetPropExchange::ExchangeFontProp** geçersiz kıl Bu saf sanal işlev.  
  
##  <a name="exchangepersistentprop"></a>CPropExchange::ExchangePersistentProp  
 Bir özellik denetimi ve dosya arasında değiş tokuş eder.  
  
```  
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,  
    LPUNKNOWN* ppUnk,  
    REFIID iid,  
    LPUNKNOWN pUnkDefault) = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `ppUnk`  
 Özelliğin gösteren bir işaretçi içeren bir değişken için bir işaretçi **IUnknown** (Bu değişken genellikle üyesi olduğu sınıfınız) arabirimi.  
  
 `iid`  
 Arabirim denetimi kullanacağı özelliği üzerinde arabirimi kimliği.  
  
 `pUnkDefault`  
 Özelliği için varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Dosyadan denetime özellik yükleniyor, özellik oluşturulur ve dosyadan başlatıldı. Özellik depolanıyorsa, değerini dosyasına yazılır.  
  
 İşlevler **CArchivePropExchange::ExchangePersistentProp**, **CResetPropExchange::ExchangePersistentProp**, ve **CPropsetPropExchange::ExchangePersistentProp** bu saf sanal işlevi geçersiz.  
  
##  <a name="exchangeprop"></a>CPropExchange::ExchangeProp  
 Bir özelliği bir depolama ortamına ve denetim arasında değiş tokuş eder.  
  
```  
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,  
    VARTYPE vtProp,  
    void* pvProp,  
    const void* pvDefault = NULL) = 0 ;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pszPropName`  
 Değiştirilen özelliğinin adı.  
  
 `vtProp`  
 Değiştirilen özelliğin türünü belirten bir simge. Olası değerler şunlardır:  
  
|Simgesi|Özellik türü|  
|------------|-------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_BOOL`|**BOOL**|  
|`VT_BSTR`|`CString`|  
|`VT_CY`|**CY**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
  
 `pvProp`  
 Özelliğin değerini gösteren bir işaretçi.  
  
 *pvDefault*  
 Özelliği için bir varsayılan değer işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Exchange başarılı olduğunda sıfır olmayan; işlem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetime özellik ortamından yüklenirken, özelliğin değerini ortamından alınır ve gösterdiği nesnesinde depolanan `pvProp`. Özellik Orta depolanıyorsa, nesnenin değerini işaret için tarafından `pvProp` Orta yazılır.  
  
 İşlevler **CArchivePropExchange::ExchangeProp**, **CResetPropExchange::ExchangeProp**, ve **CPropsetPropExchange::ExchangeProp** bu saf geçersiz kılma sanal işlev.  
  
##  <a name="exchangeversion"></a>CPropExchange::ExchangeVersion  
 Bir sürüm numarası kalıcılığı işlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,  
    DWORD dwVersionDefault,  
    BOOL bConvert);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwVersionLoaded*  
 Yüklenmekte olan kalıcı veri sürüm numarasını depolanacağı bir değişken başvuru.  
  
 `dwVersionDefault`  
 Denetimi geçerli sürüm numarası.  
  
 `bConvert`  
 Kalıcı veri geçerli sürüme dönüştürme ya da yüklenen aynı sürümünde koruma gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="getversion"></a>CPropExchange::GetVersion  
 Denetim sürüm numarasını almak için bu işlevini çağırın.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin sürüm numarası.  
  
##  <a name="isasynchronous"></a>CPropExchange::IsAsynchronous  
 Özellik alışverişleri zaman uyumsuz olarak Bitti durumunda belirler.  
  
```  
BOOL IsAsynchronous();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellikleri varsa TRUE değerini döndürür, aksi takdirde FALSE zaman uyumsuz olarak akar.  
  
##  <a name="isloading"></a>CPropExchange::IsLoading  
 Özellikler yükleniyor olup olmadığını belirlemek için bu işlevi çağırmak denetime yüklenen veya ondan kaydedildi.  
  
```  
BOOL IsLoading();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellikler yüklenirse sıfır olmayan; Aksi takdirde 0.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)



