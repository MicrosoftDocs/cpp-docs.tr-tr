---
title: Colet ObjectFactory sınıfı
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
ms.openlocfilehash: 22805550d13ecb400b151495363e5eda2dfb3b76
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421543"
---
# <a name="coleobjectfactory-class"></a>Colet ObjectFactory sınıfı

Sunucular, Otomasyon nesneleri ve belgeler gibi OLE nesneleri oluşturan OLE sınıfı fabrikasını uygular.

## <a name="syntax"></a>Sözdizimi

```
class COleObjectFactory : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Colet ObjectFactory:: Copaobjectfactory](#coleobjectfactory)|`COleObjectFactory` nesnesi oluşturur.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Colet ObjectFactory:: GetClassID](#getclassid)|Bu fabrika tarafından oluşturulan nesnelerin OLE sınıf KIMLIĞINI döndürür.|
|[Colet ObjectFactory:: IsLicenseValid](#islicensevalid)|Denetimin lisansının geçerli olup olmadığını belirler.|
|[Colet ObjectFactory:: IsRegistered](#isregistered)|Nesne fabrikasının OLE sistem dll 'Lerine kaydedilip kaydedilmediğini belirtir.|
|[Colet ObjectFactory:: Register](#register)|Bu nesne fabrikasını OLE sistem dll 'Leriyle kaydeder.|
|[Colet ObjectFactory:: RegisterAll](#registerall)|Tüm uygulamanın nesne fabrikalarını OLE sistem dll 'Leriyle kaydeder.|
|[Colet ObjectFactory:: Revoke](#revoke)|Bu nesne fabrikasının kaydını OLE sistem dll 'Leriyle iptal eder.|
|[Cokerobjectfactory:: Iptal edildi](#revokeall)|OLE sistem dll 'Leriyle bir uygulamanın nesne fabrikaları kayıtlarını iptal eder.|
|[Colet ObjectFactory:: UnregisterAll](#unregisterall)|Uygulamanın nesne fabrikalarının tümünün kaydını siler.|
|[Colet ObjectFactory:: UpdateRegistry](#updateregistry)|Bu nesne fabrikasını OLE sistem kayıt defteriyle kaydeder.|
|[Colet ObjectFactory:: öğenize kaydedilecektir](#updateregistryall)|Uygulamanın tüm nesne fabrikalarını OLE sistem kayıt defteriyle kaydeder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Colet ObjectFactory:: GetLicenseKey](#getlicensekey)|Denetimin DLL 'sinden benzersiz bir anahtar ister.|
|[Colet ObjectFactory:: OnCreateObject](#oncreateobject)|Bu fabrika türünün yeni bir nesnesini oluşturmak için Framework tarafından çağırılır.|
|[Colet ObjectFactory:: VerifyLicenseKey](#verifylicensekey)|Denetimde gömülü anahtarın, kapsayıcıda gömülü anahtarla eşleştiğini doğrular.|
|[Colet ObjectFactory:: VerifyUserLicense](#verifyuserlicense)|Denetimin tasarım zamanı kullanımı için lisanslandığını doğrular.|

## <a name="remarks"></a>Açıklamalar

`COleObjectFactory` sınıfı aşağıdaki işlevleri gerçekleştirmek için üye işlevlere sahiptir:

- Nesnelerin kaydını yönetme.

- OLE sistem yazmacın yanı sıra OLE 'nin nesnelerin çalıştığını ve iletileri almaya hazırlandığını bildiren çalışma zamanı kaydını güncelleştirme.

- Denetim kullanımını, tasarım zamanında lisanslanmış geliştiriciler ve çalışma zamanında lisanslanmış uygulamalar ile sınırlayarak lisanslamayı zorunlu tutma.

- Denetim nesnesi fabrikalarını OLE sistem kayıt defteriyle kaydetme.

Nesne oluşturma hakkında daha fazla bilgi için, bkz. [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md) ve veri [nesneleri ve veri kaynakları: oluşturma ve yok etme](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Kayıt hakkında daha fazla bilgi için bkz. Makale [kaydı](../../mfc/registration.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleObjectFactory`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

##  <a name="coleobjectfactory"></a>Colet ObjectFactory:: Copaobjectfactory

`COleObjectFactory` nesnesi oluşturur, onu kayıtsız nesne fabrikası olarak başlatır ve fabrika listesine ekler.

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

*in*<br/>
Bu nesne fabrikası temsil eden OLE sınıf KIMLIĞINE başvuru.

*pRuntimeClass*<br/>
Bu fabrikaya ait oluşturabileceğiniz C++ nesnelerin çalışma zamanı sınıfına yönelik işaretçi.

*Oluşturucusuna bmultiınstance*<br/>
Uygulamanın tek bir örneğinin birden çok örneklemesini destekleyip desteklemediğini gösterir. TRUE ise, her bir nesne oluşturma isteği için uygulamanın birden çok örneği başlatılır.

*nFlags*<br/>
Aşağıdaki bayraklardan birini veya daha fazlasını içerir:

- `afxRegDefault` iş parçacığı modelini ThreadingModel = Apartment olarak ayarlar.

- `afxRegInsertable`, denetimin OLE nesneleri için **nesne Ekle** iletişim kutusunda görünmesine izin verir.

- `afxRegApartmentThreading` kayıt defterindeki iş parçacığı modelini ThreadingModel = Apartment olarak ayarlar.

- `afxRegFreeThreading` kayıt defterindeki iş parçacığı modelini ThreadingModel = ücretsiz olarak ayarlar.

   `afxRegApartmentThreading` iki bayrağı birleştirebilir ve `afxRegFreeThreading`, ThreadingModel = her Ikisi de ayarlayabilirsiniz. İş parçacığı modeli kaydı hakkında daha fazla bilgi için Windows SDK [ınprocserver32](/windows/win32/com/inprocserver32) bakın.

*lpszProgID*<br/>
"Microsoft Excel" gibi bir Vere program tanımlayıcısı içeren bir dizeye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Ancak, nesnesini kullanmak için kaydetmeniz gerekir.

Daha fazla bilgi için Windows SDK [CLSID anahtarı](/windows/win32/com/clsid-key-hklm) bölümüne bakın.

##  <a name="getclassid"></a>Colet ObjectFactory:: GetClassID

Bu fabrika 'nin gösterdiği OLE sınıf KIMLIĞINE bir başvuru döndürür.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu fabrika 'nin gösterdiği OLE sınıf KIMLIĞINE başvuru.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [CLSID anahtarı](/windows/win32/com/clsid-key-hklm) bölümüne bakın.

##  <a name="getlicensekey"></a>Colet ObjectFactory:: GetLicenseKey

Denetimin DLL 'sinden benzersiz bir lisans anahtarı ister ve bunu *Pbstrkey*tarafından Işaret edilen BSTR 'de depolar.

```
virtual BOOL GetLicenseKey(
    DWORD dwReserved,
    BSTR* pbstrKey);
```

### <a name="parameters"></a>Parametreler

*Dwayrýlmýþ*<br/>
Gelecekte kullanılmak üzere ayrılmış.

*pbstrKey*<br/>
Lisans anahtarını depolayacak bir BSTR işaretçisine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Lisans anahtarı dizesi NULL değilse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması 0 döndürür ve BSTR 'de hiçbir şey depolar. Projenizi oluşturmak için MFC ActiveX ControlWizard kullanırsanız, ControlWizard denetimin lisans anahtarını alan bir geçersiz kılma sağlar.

##  <a name="islicensevalid"></a>Colet ObjectFactory:: IsLicenseValid

Denetimin lisansının geçerli olup olmadığını belirler.

```
BOOL IsLicenseValid();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

##  <a name="isregistered"></a>Colet ObjectFactory:: IsRegistered

Fabrika, OLE sistem dll 'Leriyle kayıtlıysa sıfır dışında bir değer döndürür.

```
virtual BOOL IsRegistered() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika kayıtlıysa sıfır dışı; Aksi takdirde 0.

##  <a name="oncreateobject"></a>Colet ObjectFactory:: OnCreateObject

Yeni bir nesne oluşturmak için Framework tarafından çağırılır.

```
virtual CCmdTarget* OnCreateObject();
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturulan nesneye yönelik bir işaretçi. Başarısız olursa bir bellek özel durumu oluşturabilir.

### <a name="remarks"></a>Açıklamalar

Oluşturucuya geçirilen [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) dışında bir nesne oluşturmak için bu işlevi geçersiz kılın.

##  <a name="register"></a>Colet ObjectFactory:: Register

Bu nesne fabrikasını OLE sistem dll 'Leriyle kaydeder.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika başarıyla kaydedilmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle, uygulama başlatıldığında [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) tarafından çağırılır.

##  <a name="registerall"></a>Colet ObjectFactory:: RegisterAll

Uygulamanın tüm nesne fabrikalarını OLE sistem dll 'Leriyle kaydeder.

```
static BOOL PASCAL RegisterAll();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrikalar başarıyla kaydedilmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle, uygulama başlatıldığında [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) tarafından çağırılır.

##  <a name="revoke"></a>Colet ObjectFactory:: Revoke

Bu nesne fabrikasının kaydını OLE sistem dll 'Leriyle iptal eder.

```
void Revoke();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, uygulama sonlandırılmadan önce bu işlevi otomatik olarak çağırır. Gerekirse, bunu bir [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)geçersiz kıldığından çağırın.

##  <a name="revokeall"></a>Cokerobjectfactory:: Iptal edildi

OLE sistem dll 'Leri ile tüm uygulamanın nesne fabrikası kayıtlarını iptal eder.

```
static void PASCAL RevokeAll();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, uygulama sonlandırılmadan önce bu işlevi otomatik olarak çağırır. Gerekirse, bunu bir [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)geçersiz kıldığından çağırın.

##  <a name="unregisterall"></a>Colet ObjectFactory:: UnregisterAll

Uygulamanın nesne fabrikalarının tümünün kaydını siler.

```
static BOOL PASCAL UnregisterAll();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

##  <a name="updateregistry"></a>Colet ObjectFactory:: UpdateRegistry

Uygulamanın tüm nesne fabrikalarını OLE sistem kayıt defteriyle kaydeder.

```
void UpdateRegistry(LPCTSTR lpszProgID = NULL);
virtual BOOL UpdateRegistry(BOOL bRegister);
```

### <a name="parameters"></a>Parametreler

*lpszProgID*<br/>
"Excel. Document. 5" gibi, insan tarafından okunabilen program tanımlayıcısını içeren bir dizeye yönelik işaretçi.

*bRegister*<br/>
Denetim sınıfının nesne fabrikasının kaydedilip edilmeyeceğini belirler.

### <a name="remarks"></a>Açıklamalar

Bu işlevin iki formu için kısa tartışmalar şunları izler:

- **UpdateRegistry (** `lpszProgID` **)** Bu nesne fabrikasını OLE sistem kayıt defteriyle kaydeder. Bu işlev genellikle, uygulama başlatıldığında [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) tarafından çağırılır.

- **UpdateRegistry (** `bRegister` **)** İşlevin bu biçimi geçersiz kılınabilir. *BRegister* true ise, bu işlev denetim sınıfını sistem kayıt defteriyle kaydeder. Aksi takdirde, sınıfının kaydını siler.

   Projenizi oluşturmak için MFC ActiveX ControlWizard kullanırsanız, ControlWizard bu saf sanal işleve bir geçersiz kılma sağlar.

##  <a name="updateregistryall"></a>Colet ObjectFactory:: öğenize kaydedilecektir

Uygulamanın tüm nesne fabrikalarını OLE sistem kayıt defteriyle kaydeder.

```
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Parametreler

*bRegister*<br/>
Denetim sınıfının nesne fabrikasının kaydedilip edilmeyeceğini belirler.

### <a name="return-value"></a>Dönüş Değeri

Fabrikalar başarıyla güncelleştirilirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle, uygulama başlatıldığında [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) tarafından çağırılır.

##  <a name="verifylicensekey"></a>Colet ObjectFactory:: VerifyLicenseKey

Kapsayıcının OLE denetimini kullanmak için lisanslandığını doğrular.

```
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```

### <a name="parameters"></a>Parametreler

*bstrKey*<br/>
Kapsayıcının lisans dizesinin sürümünü depolayan bir BSTR.

### <a name="return-value"></a>Dönüş Değeri

Çalışma zamanı lisansı geçerliyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan sürüm, denetimin lisans dizesinin bir kopyasını almak için [GetLicenseKey](#getlicensekey) ' i çağırır ve bunu *bstrKey*içindeki dizeyle karşılaştırır. İki dize eşleşiyorsa, işlev sıfır dışında bir değer döndürür; Aksi takdirde 0 döndürür.

Lisansın özelleştirilmiş doğrulanmasını sağlamak için bu işlevi geçersiz kılabilirsiniz.

[VerifyUserLicense](#verifyuserlicense) işlevi tasarım zamanı lisansını doğrular.

##  <a name="verifyuserlicense"></a>Colet ObjectFactory:: VerifyUserLicense

OLE denetimi için tasarım zamanı lisansını doğrular.

```
virtual BOOL VerifyUserLicense();
```

### <a name="return-value"></a>Dönüş Değeri

Tasarım zamanı lisansı geçerliyse sıfır dışı; Aksi takdirde 0.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleTemplateServer Sınıfı](../../mfc/reference/coletemplateserver-class.md)
