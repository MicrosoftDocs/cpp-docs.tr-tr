---
title: COleTemplateServer sınıfı
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
ms.openlocfilehash: 3abdf1dc2da5ef9a111371b501d5cd8ce208825d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781217"
---
# <a name="coletemplateserver-class"></a>COleTemplateServer sınıfı

OLE görsel düzenleme sunucuları, otomasyon sunucuları ve bağlantı kapsayıcıları (katıştırma için bağlantı destekleyen uygulamalar) için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleTemplateServer : public COleObjectFactory
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|Oluşturur bir `COleTemplateServer` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Temel alınan bir belge şablonu bağlayan `COleObjectFactory` nesne.|
|[COleTemplateServer::Unregister](#unregister)|İlişkili belge şablonunu kaydını siler.|
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Belge türü ile OLE sistem kayıt defterine kaydeder.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf sınıfından türetilir [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); genellikle kullanabileceğiniz `COleTemplateServer` kendi sınıf türetme yerine doğrudan. `COleTemplateServer` kullanan bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) sunucu belgeleri yönetmek için nesne. Kullanım `COleTemplateServer` tam sunucusu, diğer bir deyişle, bir tek başına uygulama olarak çalıştırılabilir bir sunucu uygularken. Tek Belgeli Arabirim (SDI) uygulamaları destekleniyor mu rağmen tam genellikle birden çok belge arabirimi (MDI) uygulamaları, sunucularıdır. Bir `COleTemplateServer` nesne, sunucu belgesi bir uygulamanın desteklediği her tür için gereklidir; sunucu uygulamanızı hem çalışma sayfaları ve grafikleri destekler, diğer bir deyişle, iki olmalıdır `COleTemplateServer` nesneleri.

`COleTemplateServer` geçersiz kılmalar `OnCreateInstance` üye işlevi tarafından tanımlanan `COleObjectFactory`. Bu üye işlevi uygun türde bir C++ nesnesi oluşturmak için framework tarafından çağırılır.

Sunucuları hakkında daha fazla bilgi için bkz [sunucuları: Sunucu uygulama](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="coletemplateserver"></a>  COleTemplateServer::COleTemplateServer

Oluşturur bir `COleTemplateServer` nesne.

```
COleTemplateServer();
```

### <a name="remarks"></a>Açıklamalar

Kullanımını kısa bir açıklaması için `COleTemplateServer` sınıfı [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) sınıfına genel bakış.

##  <a name="connecttemplate"></a>  COleTemplateServer::ConnectTemplate

İşaret ettiği belge şablonu bağlayan *pDocTemplate* arka plandaki [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) nesne.

```
void ConnectTemplate(
    REFCLSID clsid,
    CDocTemplate* pDocTemplate,
    BOOL bMultiInstance);
```

### <a name="parameters"></a>Parametreler

*CLSID*<br/>
OLE referansı sınıf şablonu isteği kimliği.

*pDocTemplate*<br/>
Belge şablonu için işaretçi.

*Bmultiınstance*<br/>
Tek bir örnek uygulamanın birden çok örneklemesini destekleyip desteklemediğini gösterir. TRUE ise bir nesne oluşturmak için her istek için uygulamanın birden fazla örneği başlatılabilir.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [CLSID anahtar](/windows/desktop/com/clsid-key-hklm) Windows SDK.

##  <a name="unregister"></a>  COleTemplateServer::Unregister

İlişkili belge şablonunu kaydını siler.

```
BOOL Unregister();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE; Aksi durumda FALSE.

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

*nAppType*<br/>
AFXDISP içinde tanımlanan OLE_APPTYPE sabit bir değer. H Bunu, aşağıdaki değerlerden biri olabilir:

- Oat_ınplace_server sunucunuzun tam sunucu kullanıcı arabirimi var.

- OAT_SERVER sunucusu yalnızca ekleme destekler.

- Oat_contaıner kapsayıcı katıştırılmış nesneler bağlantılarını destekler.

- Oat_dıspatch_object nesnedir `IDispatch`-özelliğine sahip.

- OAT_DOC_OBJECT_SERVER Server destekler hem de ekleme ve belge nesnesi bileşen modeli.

*rglpszRegister*<br/>
Hiçbir girdi yoksa kayıt defterine yazılır bir liste girdileri.

*rglpszOverwrite*<br/>
Önceki tüm girdileri olup mevcut bağımsız olarak kayıt defterine yazılır girişleri listesi.

*bRegister*<br/>
Sınıf kayıtlı olup olmadığını belirler. Varsa *bRegister* doğru ise, sınıf sistem kayıt defteri ile kaydedilir. Aksi takdirde, sınıf kaydını siler.

### <a name="remarks"></a>Açıklamalar

Kayıt bilgileri bir çağrı yoluyla yüklenen [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Alınan alt dizinleri tarafından tanımlanan olanlardır `regFileTypeId`, `regFileTypeName`, ve `fileNewName`anlatılan şekilde `GetDocString` başvuru sayfalarına.

Varsa `regFileTypeId` alt dize boşsa veya çağrı `GetDocString` başarısız başka bir nedenle, bu işlev başarısız olur ve dosya bilgileri, kayıt defterinde girilmemiş.

Bilgiler, bağımsız değişkenler *rglpszRegister* ve *rglpszOverwrite* yapılan bir çağrıyla kayıt defterine yazılır [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass). İki bağımsız değişken NULL olduğunda kaydedilir, varsayılan bilgileri, çoğu uygulama için uygundur. Bu bağımsız değişkenler bilgileri yapısı hakkında daha fazla bilgi için bkz: `AfxOleRegisterServerClass`.

Daha fazla bilgi için [IDispatch arabirimi uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[COleObjectFactory sınıfı](../../mfc/reference/coleobjectfactory-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc sınıfı](../../mfc/reference/coleserverdoc-class.md)<br/>
[Coleserverıtem sınıfı](../../mfc/reference/coleserveritem-class.md)
