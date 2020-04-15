---
title: COleObjectFactory Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleObjectFactory
- AFXDISP/COleObjectFactory
- AFXDISP/COleObjectFactory::COleObjectFactory
- AFXDISP/COleObjectFactory::GetClassID
- AFXDISP/COleObjectFactory::IsLicenseValid
- AFXDISP/COleObjectFactory::IsRegistered
- AFXDISP/COleObjectFactory::Register
- AFXDISP/COleObjectFactory::RegisterAll
- AFXDISP/COleObjectFactory::Revoke
- AFXDISP/COleObjectFactory::RevokeAll
- AFXDISP/COleObjectFactory::UnregisterAll
- AFXDISP/COleObjectFactory::UpdateRegistry
- AFXDISP/COleObjectFactory::UpdateRegistryAll
- AFXDISP/COleObjectFactory::GetLicenseKey
- AFXDISP/COleObjectFactory::OnCreateObject
- AFXDISP/COleObjectFactory::VerifyLicenseKey
- AFXDISP/COleObjectFactory::VerifyUserLicense
helpviewer_keywords:
- COleObjectFactory [MFC], COleObjectFactory
- COleObjectFactory [MFC], GetClassID
- COleObjectFactory [MFC], IsLicenseValid
- COleObjectFactory [MFC], IsRegistered
- COleObjectFactory [MFC], Register
- COleObjectFactory [MFC], RegisterAll
- COleObjectFactory [MFC], Revoke
- COleObjectFactory [MFC], RevokeAll
- COleObjectFactory [MFC], UnregisterAll
- COleObjectFactory [MFC], UpdateRegistry
- COleObjectFactory [MFC], UpdateRegistryAll
- COleObjectFactory [MFC], GetLicenseKey
- COleObjectFactory [MFC], OnCreateObject
- COleObjectFactory [MFC], VerifyLicenseKey
- COleObjectFactory [MFC], VerifyUserLicense
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
ms.openlocfilehash: 9f3d86cf735c02b6021441c66d9fd64547f6d6c2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374903"
---
# <a name="coleobjectfactory-class"></a>COleObjectFactory Sınıfı

Sunucular, otomasyon nesneleri ve belgeler gibi OLE nesneleri oluşturan OLE sınıfı fabrikayı uygular.

## <a name="syntax"></a>Sözdizimi

```
class COleObjectFactory : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|Bir `COleObjectFactory` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleObjectFactory::GetClassID](#getclassid)|Bu fabrikanın oluşturduğu nesnelerin OLE sınıfı kimliğini döndürür.|
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|Denetim lisansının geçerli olup olmadığını belirler.|
|[COleObjectFactory::Kayıtlı](#isregistered)|Nesne fabrikasının OLE sistemi DL'lerine kayıtlı olup olmadığını gösterir.|
|[COleObjectFactory::Kayıt](#register)|Bu nesne fabrikasını OLE sistemi DL'leri ile kaydeder.|
|[COleObjectFactory::RegisterAll](#registerall)|Uygulamanın tüm nesne fabrikalarını OLE sistem DL'leri ile kaydeder.|
|[COleObjectFactory::İptal](#revoke)|Bu nesne fabrikasının OLE sistemi DL'leri ile kaydını iptal eder.|
|[COleObjectFactory::RevokeAll](#revokeall)|OLE sistemi DLs ile bir uygulamanın nesne fabrikalarının kayıtlarını iptal eder.|
|[COleObjectFactory::Kayıt DışıTüm](#unregisterall)|Bir uygulamanın nesne fabrikalarının tümünün kaydını silindiri.|
|[COleObjectFactory::UpdateRegistry](#updateregistry)|Bu nesne fabrikasını OLE sistem kayıt defterine kaydeder.|
|[COleObjectFactory::UpdateRegistryAll](#updateregistryall)|Uygulamanın tüm nesne fabrikalarını OLE sistem kayıt defterine kaydeder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|Denetimin DLL'sinden benzersiz bir anahtar ister.|
|[COleObjectFactory::OnCreateObject](#oncreateobject)|Bu fabrikanın türünde yeni bir nesne oluşturmak için çerçeve tarafından çağrıldı.|
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|Denetime katışmedilen anahtarın kapsayıcıya katışta katıştılmış anahtarla eşleştiğini doğrular.|
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|Denetimin tasarım zamanı kullanımı için lisanslı olduğunu doğrular.|

## <a name="remarks"></a>Açıklamalar

Sınıfın `COleObjectFactory` aşağıdaki işlevleri gerçekleştirmek için üye işlevleri vardır:

- Nesnelerin kaydını yönetme.

- OLE sistem kaydının yanı sıra OLE'ye nesnelerin çalıştığını ve ileti almaya hazır olduğunu bildiren çalışma zamanı kaydının güncelleştirilmesi.

- Denetimin kullanımını tasarım zamanında lisanslı geliştiricilerle ve çalışma zamanında lisanslı uygulamalarla sınırlandırarak lisanslamayı zorlamak.

- Denetim nesnesi fabrikalarını OLE sistem kayıt defterine kaydetme.

Nesne oluşturma hakkında daha fazla bilgi [için, veri nesneleri ve veri kaynakları (OLE) ve](../../mfc/data-objects-and-data-sources-ole.md) [Veri Nesneleri ve Veri Kaynakları: Oluşturma ve Yok Etme](../../mfc/data-objects-and-data-sources-creation-and-destruction.md)makalelerine bakın. Kayıt hakkında daha fazla şey [için,](../../mfc/registration.md)makale Kayıt bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`COleObjectFactory`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="coleobjectfactorycoleobjectfactory"></a><a name="coleobjectfactory"></a>COleObjectFactory::COleObjectFactory

Bir `COleObjectFactory` nesne yi inşa eder, kayıtdışı nesne fabrikası olarak başharfe alerler ve fabrikalar listesine ekler.

```
COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    LPCTSTR lpszProgID);

COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    int nFlags,
    LPCTSTR lpszProgID);
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
OLE sınıfı kimliğine başvuru olarak bu nesne fabrikayı temsil eder.

*pRuntimeClass*<br/>
Bu fabrikanın oluşturabileceği C++ nesnelerinin çalışma zamanı sınıfına işaretçi.

*bMultiInstance*<br/>
Uygulamanın tek bir örneğinin birden çok anlık sözcük'ü destekleyip desteklemeyeceğini gösterir. TRUE ise, bir nesne oluşturmak için her istek için uygulamanın birden çok örneği başlatılır.

*Nflags*<br/>
Aşağıdaki bayraklardan birini veya birkaçını içerir:

- `afxRegDefault`İş parçacığı modelini ThreadingModel=Apartment olarak ayarlar.

- `afxRegInsertable`Denetimin OLE nesneleri için **Nesne Ekle** iletişim kutusunda görünmesini sağlar.

- `afxRegApartmentThreading`İş parçacığı modelini threadingModel=Apartment olarak ayarlar.

- `afxRegFreeThreading`Kayıt defterindeki iş parçacığı modelini ThreadingModel=Free olarak ayarlar.

   İki bayrağı `afxRegApartmentThreading` `afxRegFreeThreading` birleştirip ThreadingModel=Her ikisini de ayarlayabilirsiniz. İş parçacığı modeli kaydı hakkında daha fazla bilgi için Windows SDK'da [InprocServer32'ye](/windows/win32/com/inprocserver32) bakın.

*lpszProgID*<br/>
"Microsoft Excel" gibi sözel bir program tanımlayıcısı içeren bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Ancak nesneyi kullanmak için kaydettirmeniz gerekir.

Daha fazla bilgi için Windows SDK'daki [CLSID Key'e](/windows/win32/com/clsid-key-hklm) bakın.

## <a name="coleobjectfactorygetclassid"></a><a name="getclassid"></a>COleObjectFactory::GetClassID

Bu fabrikanın temsil eden OLE sınıfı kimliğine bir başvuru verir.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu fabrikanın temsil eden OLE sınıfı kimliğine başvuru.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [CLSID Key'e](/windows/win32/com/clsid-key-hklm) bakın.

## <a name="coleobjectfactorygetlicensekey"></a><a name="getlicensekey"></a>COleObjectFactory::GetLicenseKey

Denetimin DLL'sinden benzersiz bir lisans anahtarı ister ve *pbstrKey*tarafından işaret edilen BSTR'de saklar.

```
virtual BOOL GetLicenseKey(
    DWORD dwReserved,
    BSTR* pbstrKey);
```

### <a name="parameters"></a>Parametreler

*dwAyrılmış*<br/>
Daha sonraki kullanımlar için ayrılmıştır.

*pbstrKey*<br/>
Lisans anahtarını depolayacak bir BSTR işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Lisans anahtarı dizesi NULL değilse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması 0 döndürür ve BSTR'de hiçbir şey depolar. Projenizi oluşturmak için MFC ActiveX ControlWizard kullanıyorsanız, ControlWizard denetimin lisans anahtarını alan bir geçersiz kılma sağlar.

## <a name="coleobjectfactoryislicensevalid"></a><a name="islicensevalid"></a>COleObjectFactory::IsLicenseValid

Denetim lisansının geçerli olup olmadığını belirler.

```
BOOL IsLicenseValid();
```

### <a name="return-value"></a>Dönüş Değeri

DOĞRU eğer successul; aksi takdirde yanlış.

## <a name="coleobjectfactoryisregistered"></a><a name="isregistered"></a>COleObjectFactory::Kayıtlı

Fabrika OLE sistemi DLs'e kayıtlıysa sıfır olmayan bir değer verir.

```
virtual BOOL IsRegistered() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika kayıtlı ise sıfır; aksi takdirde 0.

## <a name="coleobjectfactoryoncreateobject"></a><a name="oncreateobject"></a>COleObjectFactory::OnCreateObject

Yeni bir nesne oluşturmak için çerçeve tarafından çağrılır.

```
virtual CCmdTarget* OnCreateObject();
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturulan nesneye işaretçi. Başarısız olursa bellek özel durum atabilir.

### <a name="remarks"></a>Açıklamalar

Nesneyi oluşturucuya geçirilen [CRuntimeClass'tan](../../mfc/reference/cruntimeclass-structure.md) başka bir şeyden oluşturmak için bu işlevi geçersiz kılın.

## <a name="coleobjectfactoryregister"></a><a name="register"></a>COleObjectFactory::Kayıt

Bu nesne fabrikasını OLE sistemi DL'leri ile kaydeder.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika başarıyla tescil edilirse sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle CWinApp tarafından çağrılır::Uygulama başlatıldığında [InitInstance.](../../mfc/reference/cwinapp-class.md#initinstance)

## <a name="coleobjectfactoryregisterall"></a><a name="registerall"></a>COleObjectFactory::RegisterAll

Uygulamanın tüm nesne fabrikalarını OLE sistemi DL'leri ile kaydeder.

```
static BOOL PASCAL RegisterAll();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrikalar başarıyla kaydedilirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle CWinApp tarafından çağrılır::Uygulama başlatıldığında [InitInstance.](../../mfc/reference/cwinapp-class.md#initinstance)

## <a name="coleobjectfactoryrevoke"></a><a name="revoke"></a>COleObjectFactory::İptal

Bu nesne fabrikasının OLE sistemi DL'leri ile kaydını iptal eder.

```
void Revoke();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, uygulama sona ermeden önce bu işlevi otomatik olarak çağırır. Gerekirse, CWinApp bir geçersiz kılma dan [arayın::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).

## <a name="coleobjectfactoryrevokeall"></a><a name="revokeall"></a>COleObjectFactory::RevokeAll

OLE sistemi DLs ile uygulamanın tüm nesne fabrikalarının kayıtlarını iptal eder.

```
static void PASCAL RevokeAll();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, uygulama sona ermeden önce bu işlevi otomatik olarak çağırır. Gerekirse, CWinApp bir geçersiz kılma dan [arayın::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).

## <a name="coleobjectfactoryunregisterall"></a><a name="unregisterall"></a>COleObjectFactory::Kayıt DışıTüm

Bir uygulamanın nesne fabrikalarının tümünün kaydını silindiri.

```
static BOOL PASCAL UnregisterAll();
```

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

## <a name="coleobjectfactoryupdateregistry"></a><a name="updateregistry"></a>COleObjectFactory::UpdateRegistry

Uygulamanın tüm nesne fabrikalarını OLE sistem kayıt defterine kaydeder.

```
void UpdateRegistry(LPCTSTR lpszProgID = NULL);
virtual BOOL UpdateRegistry(BOOL bRegister);
```

### <a name="parameters"></a>Parametreler

*lpszProgID*<br/>
"Excel.Document.5" gibi insan tarafından okunabilir program tanımlayıcısını içeren bir dize işaretçisi.

*bKayıt*<br/>
Denetim sınıfının nesne fabrikasının kaydedilip kaydedilmeyeceğini belirler.

### <a name="remarks"></a>Açıklamalar

Bu işlev için iki formun kısa tartışmaları aşağıdaki gibidir:

- **UpdateRegistry(** `lpszProgID` **)** Bu nesne fabrikasını OLE sistem kayıt defterine kaydeder. Bu işlev genellikle CWinApp tarafından çağrılır::Uygulama başlatıldığında [InitInstance.](../../mfc/reference/cwinapp-class.md#initinstance)

- **UpdateRegistry(** `bRegister` **)** Fonksiyonun bu formu geçersiz kılınabilir. *bRegister* TRUE ise, bu işlev denetim sınıfını sistem kayıt defterine kaydeder. Aksi takdirde, sınıfın kaydını silinir.

   Projenizi oluşturmak için MFC ActiveX ControlWizard kullanıyorsanız, ControlWizard bu saf sanal işleve geçersiz kılma sağlar.

## <a name="coleobjectfactoryupdateregistryall"></a><a name="updateregistryall"></a>COleObjectFactory::UpdateRegistryAll

Uygulamanın tüm nesne fabrikalarını OLE sistem kayıt defterine kaydeder.

```
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Parametreler

*bKayıt*<br/>
Denetim sınıfının nesne fabrikasının kaydedilip kaydedilmeyeceğini belirler.

### <a name="return-value"></a>Dönüş Değeri

Fabrikalar başarıyla güncellenirse sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle CWinApp tarafından çağrılır::Uygulama başlatıldığında [InitInstance.](../../mfc/reference/cwinapp-class.md#initinstance)

## <a name="coleobjectfactoryverifylicensekey"></a><a name="verifylicensekey"></a>COleObjectFactory::VerifyLicenseKey

Kapsayıcının OLE denetimini kullanmak için lisanslı olduğunu doğrular.

```
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```

### <a name="parameters"></a>Parametreler

*bstrKey*<br/>
Bir BSTR, konteynerin lisans dizesinin sürümünü depolamak.

### <a name="return-value"></a>Dönüş Değeri

Çalışma zamanı lisansı geçerliyse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan sürüm, denetimin lisans dizesinin bir kopyasını almak için [GetLicenseKey'i](#getlicensekey) arar ve *bstrKey'deki*dizeyle karşılaştırır. İki dize eşleşirse, işlev sıfır olmayan bir değer döndürür; aksi takdirde 0 döndürür.

Lisansın özelleştirilmiş doğrulamasını sağlamak için bu işlevi geçersiz kılabilirsiniz.

[VerifyUserLicense](#verifyuserlicense) işlevi tasarım zamanı lisansını doğrular.

## <a name="coleobjectfactoryverifyuserlicense"></a><a name="verifyuserlicense"></a>COleObjectFactory::VerifyUserLicense

OLE denetimi için tasarım zamanı lisansını doğrular.

```
virtual BOOL VerifyUserLicense();
```

### <a name="return-value"></a>Dönüş Değeri

Tasarım zamanı lisansı geçerliyse sıfırsız; aksi takdirde 0.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleTemplateServer Sınıfı](../../mfc/reference/coletemplateserver-class.md)
