---
title: Cotatemplateserver sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
helpviewer_keywords:
- COleTemplateServer [MFC], COleTemplateServer
- COleTemplateServer [MFC], ConnectTemplate
- COleTemplateServer [MFC], Unregister
- COleTemplateServer [MFC], UpdateRegistry
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
ms.openlocfilehash: 4a1997497f3bddb405b712b5534f76e577dabfa8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503089"
---
# <a name="coletemplateserver-class"></a>Cotatemplateserver sınıfı

OLE görsel düzenlemesi sunucuları, otomasyon sunucuları ve bağlantı kapsayıcıları (katıştırlara bağlantıları destekleyen uygulamalar) için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleTemplateServer : public COleObjectFactory
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotatemplateserver:: Copatemplateserver](#coletemplateserver)|Bir `COleTemplateServer` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotatemplateserver:: ConnectTemplate](#connecttemplate)|Bir belge şablonunu temel alınan `COleObjectFactory` nesneye bağlar.|
|[Cotatemplateserver:: Unregister](#unregister)|İlişkili belge şablonunun kaydını siler.|
|[Cotatemplateserver:: UpdateRegistry](#updateregistry)|Belge türünü OLE sistem kayıt defterine kaydeder.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf [Coelobjectfactory](../../mfc/reference/coleobjectfactory-class.md); sınıfından türetilir genellikle kendi sınıfınızı türetmekten `COleTemplateServer` değil doğrudan kullanabilirsiniz. `COleTemplateServer`Sunucu belgelerini yönetmek için bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesi kullanır. Bir `COleTemplateServer` tam sunucu uygularken kullanın, diğer bir deyişle, tek başına uygulama olarak çalıştırılabilen bir sunucu. Tam sunucular genellikle birden çok belge arabirimi (MDI) uygulaması olsa da, tek belge arabirimi (SDI) uygulamaları desteklenir. Bir `COleTemplateServer` uygulamanın desteklediği her bir sunucu belgesi türü için bir nesne gerekir; diğer bir deyişle, sunucu uygulamanız hem çalışma sayfalarını hem de grafikleri destekliyorsa, iki `COleTemplateServer` nesneniz olmalıdır.

`COleTemplateServer``OnCreateInstance` tarafından`COleObjectFactory`tanımlanan üye işlevini geçersiz kılar. Bu üye işlevi, doğru türde bir C++ nesne oluşturmak için Framework tarafından çağırılır.

Sunucular hakkında daha fazla bilgi için bkz. Makale [sunucuları: Sunucu](../../mfc/servers-implementing-a-server.md)uygulama.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

##  <a name="coletemplateserver"></a>Cotatemplateserver:: Copatemplateserver

Bir `COleTemplateServer` nesnesi oluşturur.

```
COleTemplateServer();
```

### <a name="remarks"></a>Açıklamalar

`COleTemplateServer` Sınıfının kullanımına ilişkin kısa bir açıklama için bkz. [copalinkingdoc](../../mfc/reference/colelinkingdoc-class.md) sınıfına genel bakış.

##  <a name="connecttemplate"></a>Cotatemplateserver:: ConnectTemplate

*PDocTemplate* tarafından işaret edilen belge şablonunu temeldeki [Colet ObjectFactory](../../mfc/reference/coleobjectfactory-class.md) nesnesine bağlar.

```
void ConnectTemplate(
    REFCLSID clsid,
    CDocTemplate* pDocTemplate,
    BOOL bMultiInstance);
```

### <a name="parameters"></a>Parametreler

*in*<br/>
Şablonun istediği OLE sınıf KIMLIĞINE başvuru.

*pDocTemplate*<br/>
Belge şablonuna yönelik işaretçi.

*Oluşturucusuna bmultiınstance*<br/>
Uygulamanın tek bir örneğinin birden çok örneklemesini destekleyip desteklemediğini gösterir. TRUE ise, her bir nesne oluşturma isteği için uygulamanın birden çok örneği başlatılır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [CLSID anahtarı](/windows/win32/com/clsid-key-hklm) bölümüne bakın.

##  <a name="unregister"></a>Cotatemplateserver:: Unregister

İlişkili belge şablonunun kaydını siler.

```
BOOL Unregister();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Enternotlar

##  <a name="updateregistry"></a>Cotatemplateserver:: UpdateRegistry

Belge şablonu dizesinden dosya türü bilgilerini yükler ve bu bilgileri OLE sistem kayıt defterine koyar.

```
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Parametreler

*nAppType*<br/>
OLE_APPTYPE numaralandırmasından, AFXDISP içinde tanımlanan bir değer. Olsun. Aşağıdaki değerlerden herhangi biri olabilir:

- OAT_INPLACE_SERVER sunucusu tam sunucu Kullanıcı arabirimine sahiptir.

- OAT_SERVER sunucusu yalnızca katıştırmayı destekler.

- OAT_CONTAINER kapsayıcısı gömülü nesnelerin bağlantılarını destekler.

- OAT_DISPATCH_OBJECT nesnesi `IDispatch`özellikli.

- OAT_DOC_OBJECT_SERVER sunucusu hem katıştırma hem de belge nesnesi bileşen modelini destekler.

*rglpszRegister*<br/>
Yalnızca girdi yoksa kayıt defterine yazılan girişlerin bir listesi.

*rglpszOverwrite*<br/>
Yukarıdaki girdilerin mevcut olup olmamasına bakılmaksızın kayıt defterine yazılan girişlerin bir listesi.

*bRegister*<br/>
Sınıfın kaydedilip edilmeyeceğini belirler. *BRegister* true ise, sınıfı sistem kayıt defterine kaydedilir. Aksi takdirde, sınıfının kaydını siler.

### <a name="remarks"></a>Açıklamalar

Kayıt bilgileri [CDocTemplate:: GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)çağrısı yoluyla yüklenir. Alınan alt `regFileTypeId`dizeler, `GetDocString` başvuru sayfalarında açıklandığı gibi, ve `regFileTypeName` `fileNewName`dizinleri tarafından tanımlanan olanlardır.

Alt dize boşsa veya çağrı başka bir nedenle `GetDocString` başarısız olursa, bu işlev başarısız olur ve dosya bilgileri kayıt defterine girilmez. `regFileTypeId`

*RglpszRegister* ve *rglpszOverwrite* bağımsız değişkenlerinin bilgileri [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass)çağrısıyla kayıt defterine yazılır. İki bağımsız değişken NULL olduğunda kayıtlı olan varsayılan bilgiler, çoğu uygulama için uygundur. Bu bağımsız değişkenlerdeki bilgilerin yapısı hakkında daha fazla bilgi için bkz `AfxOleRegisterServerClass`.

Daha fazla bilgi için bkz. [IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[COleObjectFactory Sınıfı](../../mfc/reference/coleobjectfactory-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)
