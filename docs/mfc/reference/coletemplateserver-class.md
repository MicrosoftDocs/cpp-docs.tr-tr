---
title: COleTemplateServer Sınıfı
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
ms.openlocfilehash: ddd7a8ce70fe49e66e1175e413418fd59a89c917
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374849"
---
# <a name="coletemplateserver-class"></a>COleTemplateServer Sınıfı

OLE görsel düzenleme sunucuları, otomasyon sunucuları ve bağlantı kapsayıcıları (katıştırma bağlantıları destekleyen uygulamalar) için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleTemplateServer : public COleObjectFactory
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|Bir `COleTemplateServer` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Belge şablonunu alttaki `COleObjectFactory` nesneye bağlar.|
|[COleTemplateServer::Kayıt Dışı](#unregister)|İlişkili belge şablonuna kaydını açar.|
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Belge türünü OLE sistem kayıt defterine kaydeder.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)sınıfından türetilmiştir; genellikle, doğrudan `COleTemplateServer` yerine kendi sınıf türetmek kullanabilirsiniz. `COleTemplateServer`sunucu belgelerini yönetmek için bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesi kullanır. Tek `COleTemplateServer` başına bir uygulama olarak çalıştırılabilen bir sunucu, yani tam bir sunucu uygularken kullanın. Tek belge arabirimi (SDI) uygulamaları desteklenmiş olsa da, tam sunucular genellikle birden çok belge arabirimi (MDI) uygulamasıdır. Bir `COleTemplateServer` uygulamanın desteklediği her sunucu belgesi türü için bir nesne gerekir; diğer bir diğer olarak, sunucu uygulamanız hem çalışma `COleTemplateServer` sayfalarını hem de grafikleri destekliyorsa, iki nesneniz olmalıdır.

`COleTemplateServer`tarafından `COleObjectFactory`tanımlanan `OnCreateInstance` üye işlevi geçersiz kılar. Bu üye işlev, uygun türde bir C++ nesnesi oluşturmak için çerçeve tarafından çağrılır.

Sunucular hakkında daha fazla bilgi için, makale [Sunucuları bakınız: Bir Sunucu uygulama.](../../mfc/servers-implementing-a-server.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Coleobjectfactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="coletemplateservercoletemplateserver"></a><a name="coletemplateserver"></a>COleTemplateServer::COleTemplateServer

Bir `COleTemplateServer` nesne inşa eder.

```
COleTemplateServer();
```

### <a name="remarks"></a>Açıklamalar

`COleTemplateServer` Sınıfın kullanımıyla ilgili kısa bir açıklama için [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) sınıfına genel bakış bölümüne bakın.

## <a name="coletemplateserverconnecttemplate"></a><a name="connecttemplate"></a>COleTemplateServer::ConnectTemplate

*pDocTemplate* tarafından işaret edilen belge şablonunu altta yatan [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) nesnesine bağlar.

```
void ConnectTemplate(
    REFCLSID clsid,
    CDocTemplate* pDocTemplate,
    BOOL bMultiInstance);
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
Şablonun isteklerini yaptığı OLE sınıfı kimliğine başvuru.

*pDocTemplate*<br/>
Belge şablonuna işaretçi.

*bMultiInstance*<br/>
Uygulamanın tek bir örneğinin birden çok anlık sözcük'ü destekleyip desteklemeyeceğini gösterir. TRUE ise, bir nesne oluşturmak için her istek için uygulamanın birden çok örneği başlatılır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [CLSID Key'e](/windows/win32/com/clsid-key-hklm) bakın.

## <a name="coletemplateserverunregister"></a><a name="unregister"></a>COleTemplateServer::Kayıt Dışı

İlişkili belge şablonuna kaydını açar.

```
BOOL Unregister();
```

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Açıklamalara Giriş

## <a name="coletemplateserverupdateregistry"></a><a name="updateregistry"></a>COleTemplateServer::UpdateRegistry

Belge şablonu dizesinden dosya türü bilgileri yükler ve bu bilgileri OLE sistem kayıt defterine yerleştirir.

```
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Parametreler

*nAppType*<br/>
AFXDISP'de tanımlanan OLE_APPTYPE numaralandırmadeğeri. H. Aşağıdaki değerlerden herhangi birine sahip olabilir:

- OAT_INPLACE_SERVER Server tam sunucu kullanıcı arayüzüne sahiptir.

- OAT_SERVER Sunucu yalnızca katıştırma desteklemektedir.

- OAT_CONTAINER Kapsayıcı katıştak nesnelere bağlantıları destekler.

- OAT_DISPATCH_OBJECT Nesne `IDispatch`-yetenekli.

- OAT_DOC_OBJECT_SERVER Sunucu hem katıştırma hem de Belge Nesnesi bileşeni modelini destekler.

*rglpszKayıt*<br/>
Yalnızca hiçbir giriş yoksa kayıt defterine yazılmış girişlerin listesi.

*rglpszOverwrite*<br/>
Önceki girişlerin var olup olmadığına bakılmaksızın kayıt defterine yazılmış girişlerin listesi.

*bKayıt*<br/>
Sınıfın kaydedilip kaydedilmeyeceğini belirler. *bRegister* DOĞRU ise, sınıf sistem kayıt defterine kaydedilir. Aksi takdirde, sınıfın kaydını silinir.

### <a name="remarks"></a>Açıklamalar

Kayıt bilgileri [CDocTemplate::GetDocString'e](../../mfc/reference/cdoctemplate-class.md#getdocstring)yapılan bir çağrı ile yüklenir. Alınan alt `regFileTypeId`dizeleri, `regFileTypeName` `fileNewName` `GetDocString` başvuru sayfalarında açıklandığı gibi dizinler tarafından tanımlanan ve ,

Alt `regFileTypeId` dize boşsa veya `GetDocString` çağrı başka bir nedenle başarısız olursa, bu işlev başarısız olur ve dosya bilgileri kayıt defterine girilir.

Argümanlar *rglpszRegister* ve *rglpszOverwrite* bilgileri [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass)bir çağrı ile kayıt defterine yazılır. İki bağımsız değişken NULL olduğunda kaydedilmiş varsayılan bilgiler çoğu uygulama için uygundur. Bu bağımsız değişkenlerde bilginin yapısı hakkında `AfxOleRegisterServerClass`bilgi için bkz.

Daha fazla bilgi için Bkz. [IDispatch Arabirimi Uygulama.](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[COleObjectFactory Sınıfı](../../mfc/reference/coleobjectfactory-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)
