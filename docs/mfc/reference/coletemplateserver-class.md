---
title: COleTemplateServer sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
dev_langs:
- C++
helpviewer_keywords:
- COleTemplateServer [MFC], COleTemplateServer
- COleTemplateServer [MFC], ConnectTemplate
- COleTemplateServer [MFC], Unregister
- COleTemplateServer [MFC], UpdateRegistry
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90b24d65dbd6f800dda0b25088288bee6fdcf3c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="coletemplateserver-class"></a>COleTemplateServer sınıfı
OLE görsel düzenleme sunucuları, otomasyon sunucuları ve bağlantı kapsayıcıları (eklerinin bağlantılarını destekleyen uygulamalar) için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|Oluşturan bir `COleTemplateServer` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Temel bir belge şablonu bağlayan `COleObjectFactory` nesnesi.|  
|[COleTemplateServer::Unregister](#unregister)|İlişkili belge şablonu kaydını siler.|  
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Belge türü OLE sistem kayıt defteri ile kaydeder.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf sınıfından türetilen [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); genellikle, kullanabileceğiniz `COleTemplateServer` kendi sınıf türetme yerine doğrudan. `COleTemplateServer` kullanan bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) sunucu belgeleri yönetmek için nesnesi. Kullanım `COleTemplateServer` tam bir sunucu, diğer bir deyişle, bir tek başına uygulaması olarak çalıştırmak bir sunucu uygularken. Tek belge arabirimi (SDI) uygulamaları desteklenir, ancak tam genellikle birden çok belge arabirimi (MDI) uygulamaları, sunucularıdır. Bir `COleTemplateServer` sunucu uygulamanızı çalışma sayfaları ve grafikler destekliyorsa, diğer bir deyişle, iki olmalıdır; nesne her bir uygulama destekleyen sunucu belge türü için gerekli `COleTemplateServer` nesneleri.  
  
 `COleTemplateServer` geçersiz kılmaları `OnCreateInstance` üye fonksiyonu tarafından tanımlanan `COleObjectFactory`. Bu üye işlev uygun türde bir C++ nesnesi oluşturmak için çerçevesi tarafından çağrılır.  
  
 Makaleyi sunucuları hakkında daha fazla bilgi için bkz: [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
##  <a name="coletemplateserver"></a>  COleTemplateServer::COleTemplateServer  
 Oluşturan bir `COleTemplateServer` nesnesi.  
  
```  
COleTemplateServer();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanımını kısa bir açıklaması için `COleTemplateServer` sınıfı için bkz: [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) sınıfına genel bakış.  
  
##  <a name="connecttemplate"></a>  COleTemplateServer::ConnectTemplate  
 Gösterdiği belge şablonu bağlayan `pDocTemplate` arka plandaki [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) nesnesi.  
  
```  
void ConnectTemplate(
    REFCLSID clsid,  
    CDocTemplate* pDocTemplate,  
    BOOL bMultiInstance);
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 Şablon istekleri OLE sınıf kimliği başvuru.  
  
 `pDocTemplate`  
 Belge şablonu işaretçi.  
  
 `bMultiInstance`  
 Tek bir örnek uygulamanın birden fazla desteği olup olmadığını gösterir. Varsa **doğru**, uygulamanın birden çok örneğini bir nesne oluşturmak her istek için başlatılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [CLSID anahtarı](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK'sındaki.  
  
##  <a name="unregister"></a>  COleTemplateServer::Unregister  
 İlişkili belge şablonu kaydını siler.  
  
```  
BOOL Unregister();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 EnterRemarks  
  
##  <a name="updateregistry"></a>  COleTemplateServer::UpdateRegistry  
 Belge şablonu dizeden dosya türü bilgilerini yükler ve bu bilgileri OLE sistem kayıt defterinde yerleştirir.  
  
```  
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL,  
    BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nAppType`  
 Arasında bir değer **OLE_APPTYPE** AFXDISP içinde tanımlanan numaralandırması. H. Aşağıdaki değerlerden biri olabilir:  
  
- `OAT_INPLACE_SERVER` Sunucu tam sunucu kullanıcı arabirimi sahiptir.  
  
- `OAT_SERVER` Sunucusu yalnızca katıştırma destekler.  
  
- `OAT_CONTAINER` Kapsayıcı katıştırılmış nesneler bağlantılarını destekler.  
  
- `OAT_DISPATCH_OBJECT` Nesne `IDispatch`-özelliğine sahip.  
  
- **OAT_DOC_OBJECT_SERVER** sunucu destekler katıştırma ve belge nesnesi bileşen modeli.  
  
 `rglpszRegister`  
 Yalnızca hiçbir girdi yoksa, kayıt defterine yazılır girişinin listesi.  
  
 `rglpszOverwrite`  
 Tüm önceki girdileri olup mevcut bağımsız olarak kayıt defterine yazılır girişleri listesi.  
  
 `bRegister`  
 Sınıf kayıtlı olup olmadığını belirler. Varsa `bRegister` olan **doğru**, sınıf sistem kayıt defteri ile kaydedilir. Aksi takdirde, sınıf kaydını siler.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt bilgileri yapılan bir çağrı aracılığıyla yüklenen [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Alınan alt dizeler olanlardır dizinleri tarafından tanımlanan **regFileTypeId**, **regFileTypeName**, ve **fileNewName**açıklandığı gibi `GetDocString` başvuru sayfaları.  
  
 Varsa **regFileTypeId** substring boşsa veya çağrısı `GetDocString` başka bir nedenle, bu işlev için başarısız ve dosya bilgileri kayıt defterinde girilmemiş.  
  
 Bağımsız değişkenler bilgileri `rglpszRegister` ve `rglpszOverwrite` çağrısıyla kayıt defterine yazılır [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass). İki bağımsız değişken olduğunda kayıtlı varsayılan bilgileri **NULL**, çoğu uygulamalar için uygundur. Bu bağımsız değişkenler bilgileri yapısı hakkında daha fazla bilgi için bkz: `AfxOleRegisterServerClass`.  
  
 Daha fazla bilgi için bkz: [IDispatch arabirimi uygulama](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek HIERSVR](../../visual-cpp-samples.md)   
 [COleObjectFactory sınıfı](../../mfc/reference/coleobjectfactory-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleServerDoc sınıfı](../../mfc/reference/coleserverdoc-class.md)   
 [COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)
