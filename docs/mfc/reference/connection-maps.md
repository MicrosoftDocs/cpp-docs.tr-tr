---
title: "Bağlantı eşlemeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.maps
dev_langs: C++
helpviewer_keywords: connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d3084bd69293b9419369f2457695965481d3dec3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="connection-maps"></a>Bağlantı Eşlemeleri
OLE denetimleri diğer uygulamalara arabirimleri kullanıma sunmak kullanabilirsiniz. Bu arabirimleri bir kapsayıcı erişimden yalnızca o denetime izin verir. Diğer OLE nesnelerin Dış arabirimler erişmek bir OLE denetimi istiyorsa, bir bağlantı noktası kurulmalıdır. Bu bağlantı noktası olay eşlemeleri veya bildirim işlevleri gibi dış gönderme eşlemeleri erişimi giden bir denetim sağlar.  
  
 Microsoft Foundation Class Kitaplığı bağlantı noktaları destekleyen bir programlama modeli sunar. Bu modelde, "bağlantı eşlemeleri" arabirimleri veya OLE denetimi için bağlantı noktalarını belirlemek için kullanılır. Bağlantı eşlemeleri her bağlantı noktası için bir makrosu içerir. Bağlantı eşlemeleri hakkında daha fazla bilgi için bkz: [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) sınıfı.  
  
 Genellikle, yalnızca iki bağlantı noktası denetim destekleyecek: olaylar, diğeri özelliği bildirimleri için. Bunlar tarafından uygulanan `COleControl` temel sınıfı ve denetim yazıcı tarafından ek bir iş gerektirir. Sınıfınızda uygulamak istediğiniz her ek bağlantı noktalarını el ile eklenmesi gerekir. Bağlantı eşlemeleri ve noktalarının desteklenmesi için aşağıdaki makroları MFC sağlar:  
  
### <a name="connection-map-declaration-and-demarcation"></a>Bağlantı harita bildirim ve düzenleme  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_PART](#begin_connection_part)|(Sınıfı bildiriminde kullanılmalıdır) bir ek bağlantı noktası uygulayan katıştırılmış bir sınıf bildirir.|  
|[END_CONNECTION_PART](#end_connection_part)|(Sınıfı bildiriminde kullanılmalıdır) bir bağlantı noktası bildirimi sona erer.|  
|[CONNECTION_IID](#connection_iid)|Denetimin bağlantı noktası arabirimi Kimliğini belirtir.|  
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Bir bağlantı eşleme (sınıfı bildiriminde kullanılmalıdır) bir sınıftaki kullanılacak bildirir.|  
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|(Sınıfı uygulamasında kullanılmalıdır) bir bağlantı harita tanımını başlar.|  
|[END_CONNECTION_MAP](#end_connection_map)|(Sınıfı uygulamasında kullanılmalıdır) bir bağlantı harita tanımını sona erer.|  
|[CONNECTION_PART](#connection_part)|Bir bağlantı noktası denetim bağlantı eşlemesinde belirtir.|  
  
 Aşağıdaki işlevleri bir havuz oluşturma ve bağlantı noktalarını kullanarak bir bağlantıyı kesmeden yardımcı:  
  
### <a name="initializationtermination-of-connection-points"></a>Başlatma/sonlandırılması, bağlantı noktaları  
  
|||  
|-|-|  
|[AfxConnectionAdvise](#afxconnectionadvise)|Bir kaynak ve bir havuz arasında bir bağlantı kurar.|  
|[AfxConnectionUnadvise](#afxconnectionunadvise)|Bir kaynak ve bir havuz arasında bir bağlantı keser.|  
  
##  <a name="begin_connection_part"></a>BEGIN_CONNECTION_PART  
 Kullanım `BEGIN_CONNECTION_PART` olay ve özellik bildirim bağlantı noktaları ötesinde ek bağlantı noktaları tanımını başlamaya makrosu.  
  
```   
BEGIN_CONNECTION_PART(theClass, localClass)   
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu, bağlantı noktası denetim sınıfın adını belirtir.  
  
 *localClass*  
 Bağlantı noktası uygulayan yerel sınıf adını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantı noktasıyla sınıfınız için üye işlevleri tanımlar bildirimi (.h) dosyasına Başlat `BEGIN_CONNECTION_PART` makrosu, ardından ekleyin `CONNECTION_IID` makrosu ve istediğiniz uygulamak ve bağlantı noktası eşlemesi tamamlamak için diğer üye işlevleri ile `END_CONNECTION_PART` makrosu.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="end_connection_part"></a>END_CONNECTION_PART  
 Bağlantı noktası bildirimi sona erer.  
  
```   
END_CONNECTION_PART(localClass)   
```  
  
### <a name="parameters"></a>Parametreler  
 *localClass*  
 Bağlantı noktası uygulayan yerel sınıf adını belirtir.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="connection_iid"></a>CONNECTION_IID  
 Arasında kullanmak `BEGIN_CONNECTION_PART` ve `END_CONNECTION_PART` OLE denetiminiz tarafından desteklenen bir bağlantı noktası için bir arabirim kimliği tanımlamak için makroları.  
  
```   
CONNECTION_IID(iid)   
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 Bağlantı noktası tarafından adlı arabirim arabirimi kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 `iid` Bağımsız değişkeni olan bağlantı noktası üzerinde bağlı kendi havuzlarını çağıracak arabirimi adını tanımlamak için kullanılan arabirim. Örneğin:  
  
 [!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]  
  
 çağıran bir bağlantı noktası belirtir `ISinkInterface` arabirimi.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="declare_connection_map"></a>DECLARE_CONNECTION_MAP  
 Her `COleControl`-programınızı türetilen sınıfta denetiminizi destekleyen ek bağlantı noktalarını belirlemek için bir bağlantı harita sağlayabilir.  
  
```   
DECLARE_CONNECTION_MAP() 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim ek noktaları destekliyorsa kullanın `DECLARE_CONNECTION_MAP` makrosu sınıf bildiriminin sonundaki. Daha sonra sınıf için üye işlevleri tanımlayan .cpp dosyasında kullanmak `BEGIN_CONNECTION_MAP` makrosu, `CONNECTION_PART` her denetimin bağlantı noktaları, makroları ve `END_CONNECTION_MAP` bağlantı harita sonuna bildirmek için makrosu.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="begin_connection_map"></a>BEGIN_CONNECTION_MAP  
 Her `COleControl`-programınızı türetilen sınıfta denetiminizi destekleyecek bağlantı noktaları belirtmek için bir bağlantı harita sağlayabilir.  
  
```   
BEGIN_CONNECTION_MAP(theClass, theBase)   
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu eşleme, bağlantı denetimi sınıfın adını belirtir.  
  
 *Temel*  
 Temel sınıfını adını belirtir `theClass`.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamasında (. CPP) dosyasında, sınıf için üye işlevleri tanımlayan başlangıç bağlantı Haritası `BEGIN_CONNECTION_MAP` makrosu, her kullanarak, bağlantı noktaları için makrosu girişleri eklemek [connectıon_part](#connection_part) makrosu. Son olarak, bağlantı Haritası tamamlamak [end_connectıon_map](#end_connection_map) makrosu.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="end_connection_map"></a>END_CONNECTION_MAP  
 Bağlantı haritanızı tanımını sona erer.  
  
```   
END_CONNECTION_MAP()  
```  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="connection_part"></a>CONNECTION_PART  
 OLE denetim için bir bağlantı noktası bir arabirimin kimliği eşlemeleri  
  
```   
CONNECTION_PART(theClass, iid, localClass)   
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu, bağlantı noktası denetim sınıfın adını belirtir.  
  
 `iid`  
 Bağlantı noktası tarafından adlı arabirim arabirimi kimliği.  
  
 *localClass*  
 Bağlantı noktası uygulayan yerel sınıf adını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]  
  
 çağıran bir bağlantı noktası ile bir bağlantı harita uygulayan `IID_ISinkInterface` arabirimi.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="afxconnectionadvise"></a>AfxConnectionAdvise  
 Tarafından belirtilen bir kaynak arasında bağlantı kurmak için bu işlevi çağırmak `pUnkSrc`ve tarafından belirtilen bir havuz `pUnkSink`.  
  
```   
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD FAR* pdwCookie);
```  
  
### <a name="parameters"></a>Parametreler  
 `pUnkSrc`  
 Arabirimini çağırır ve bu nesne için bir işaretçi.  
  
 `pUnkSink`  
 Arabirimini uygulayan nesne için bir işaretçi.  
  
 `iid`  
 Bağlantı arabirimi kimliği.  
  
 `bRefCount`  
 **DOĞRU** bağlantı oluşturma başvuru sayısı neden gösteren `pUnkSink` artırılması için. **YANLIŞ** başvuru sayısı değil artırılması gösterir.  
  
 `pdwCookie`  
 Bir işaretçi bir `DWORD` bağlantı tanımlayıcısı burada döndürülür. Bu değer olarak iletilmesi gereken `dwCookie` parametresi `AfxConnectionUnadvise` bağlantı kesilirken.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir bağlantı kuruldu, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h 

##  <a name="afxconnectionunadvise"></a>AfxConnectionUnadvise  
 Tarafından belirtilen bir kaynağı arasındaki bağlantıyı kesmek için bu işlevi çağırmak `pUnkSrc`ve tarafından belirtilen bir havuz `pUnkSink`.  
  
```   
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD dwCookie); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pUnkSrc`  
 Arabirimini çağırır ve bu nesne için bir işaretçi.  
  
 `pUnkSink`  
 Arabirimini uygulayan nesne için bir işaretçi.  
  
 `iid`  
 Bağlantı noktası arabirimi arabirim kimliği.  
  
 `bRefCount`  
 **DOĞRU** bağlantıyı kesmeden başvuru sayısı neden gösteren `pUnkSink` indirildiği olmalıdır. **YANLIŞ** başvuru sayısı indirildiği olmamalıdır gösterir.  
  
 `dwCookie`  
 Tarafından döndürülen bağlantı tanımlayıcısı `AfxConnectionAdvise`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir bağlantı kesildi durumunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h 

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
