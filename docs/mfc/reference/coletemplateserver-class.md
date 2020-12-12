---
description: 'Daha fazla bilgi edinin: Cotatemplateserver sınıfı'
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
ms.openlocfilehash: da4351730fe548c83e073d3f6eaa02bc0c88cd0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226629"
---
# <a name="coletemplateserver-class"></a>Cotatemplateserver sınıfı

OLE görsel düzenlemesi sunucuları, otomasyon sunucuları ve bağlantı kapsayıcıları (katıştırlara bağlantıları destekleyen uygulamalar) için kullanılır.

## <a name="syntax"></a>Syntax

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
|[Cotatemplateserver:: ConnectTemplate](#connecttemplate)|Bir belge şablonunu temel alınan nesneye bağlar `COleObjectFactory` .|
|[Cotatemplateserver:: Unregister](#unregister)|İlişkili belge şablonunun kaydını siler.|
|[Cotatemplateserver:: UpdateRegistry](#updateregistry)|Belge türünü OLE sistem kayıt defterine kaydeder.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf [Coelobjectfactory](../../mfc/reference/coleobjectfactory-class.md); sınıfından türetilir genellikle `COleTemplateServer` kendi sınıfınızı türetmekten değil doğrudan kullanabilirsiniz. `COleTemplateServer` Sunucu belgelerini yönetmek için bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesi kullanır. Bir `COleTemplateServer` tam sunucu uygularken kullanın, diğer bir deyişle, tek başına uygulama olarak çalıştırılabilen bir sunucu. Tam sunucular genellikle birden çok belge arabirimi (MDI) uygulaması olsa da, tek belge arabirimi (SDI) uygulamaları desteklenir. Bir `COleTemplateServer` uygulamanın desteklediği her bir sunucu belgesi türü için bir nesne gerekir; diğer bir deyişle, sunucu uygulamanız hem çalışma sayfalarını hem de grafikleri destekliyorsa, iki `COleTemplateServer` nesneniz olmalıdır.

`COleTemplateServer``OnCreateInstance`tarafından tanımlanan üye işlevini geçersiz kılar `COleObjectFactory` . Bu üye işlevi, uygun türde bir C++ nesnesi oluşturmak için Framework tarafından çağırılır.

Sunucular hakkında daha fazla bilgi için bkz. [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="coletemplateservercoletemplateserver"></a><a name="coletemplateserver"></a> Cotatemplateserver:: Copatemplateserver

Bir `COleTemplateServer` nesnesi oluşturur.

```
COleTemplateServer();
```

### <a name="remarks"></a>Açıklamalar

Sınıfının kullanımına ilişkin kısa bir açıklama için `COleTemplateServer` bkz. [Copalinkingdoc](../../mfc/reference/colelinkingdoc-class.md) sınıfına genel bakış.

## <a name="coletemplateserverconnecttemplate"></a><a name="connecttemplate"></a> Cotatemplateserver:: ConnectTemplate

*PDocTemplate* tarafından işaret edilen belge şablonunu temeldeki [Colet ObjectFactory](../../mfc/reference/coleobjectfactory-class.md) nesnesine bağlar.

```cpp
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

## <a name="coletemplateserverunregister"></a><a name="unregister"></a> Cotatemplateserver:: Unregister

İlişkili belge şablonunun kaydını siler.

```
BOOL Unregister();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Enternotlar

## <a name="coletemplateserverupdateregistry"></a><a name="updateregistry"></a> Cotatemplateserver:: UpdateRegistry

Belge şablonu dizesinden dosya türü bilgilerini yükler ve bu bilgileri OLE sistem kayıt defterine koyar.

```cpp
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Parametreler

*nAppType*<br/>
OLE_APPTYPE numaralandırmasından, AFXDISP. H içinde tanımlanan bir değer. Aşağıdaki değerlerden herhangi biri olabilir:

- OAT_INPLACE_SERVER sunucusu, tam sunucu Kullanıcı arabirimine sahiptir.

- OAT_SERVER sunucusu yalnızca katıştırmayı destekler.

- OAT_CONTAINER kapsayıcı katıştırılmış nesnelerin bağlantılarını destekler.

- OAT_DISPATCH_OBJECT nesne `IDispatch` özellikli.

- OAT_DOC_OBJECT_SERVER sunucusu hem katıştırma hem de belge nesnesi bileşen modelini destekler.

*rglpszRegister*<br/>
Yalnızca girdi yoksa kayıt defterine yazılan girişlerin bir listesi.

*rglpszOverwrite*<br/>
Yukarıdaki girdilerin mevcut olup olmamasına bakılmaksızın kayıt defterine yazılan girişlerin bir listesi.

*bRegister*<br/>
Sınıfın kaydedilip edilmeyeceğini belirler. *BRegister* true ise, sınıfı sistem kayıt defterine kaydedilir. Aksi takdirde, sınıfının kaydını siler.

### <a name="remarks"></a>Açıklamalar

Kayıt bilgileri [CDocTemplate:: GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)çağrısı yoluyla yüklenir. Alınan alt dizeler, `regFileTypeId` `regFileTypeName` `fileNewName` başvuru sayfalarında açıklandığı gibi, ve dizinleri tarafından tanımlanan olanlardır `GetDocString` .

Alt `regFileTypeId` dize boşsa veya çağrı `GetDocString` başka bir nedenle başarısız olursa, bu işlev başarısız olur ve dosya bilgileri kayıt defterine girilmez.

*RglpszRegister* ve *rglpszOverwrite* bağımsız değişkenlerinin bilgileri [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass)çağrısıyla kayıt defterine yazılır. İki bağımsız değişken NULL olduğunda kayıtlı olan varsayılan bilgiler, çoğu uygulama için uygundur. Bu bağımsız değişkenlerdeki bilgilerin yapısı hakkında daha fazla bilgi için bkz `AfxOleRegisterServerClass` ..

Daha fazla bilgi için bkz. [IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Colet ObjectFactory sınıfı](../../mfc/reference/coleobjectfactory-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cotaserverdoc sınıfı](../../mfc/reference/coleserverdoc-class.md)<br/>
[Cotaserverıtem sınıfı](../../mfc/reference/coleserveritem-class.md)
