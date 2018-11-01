---
title: COleObjectFactory sınıfı
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
ms.openlocfilehash: 4aa6d688de59884c7279b441d12dda9dcdf2ff6c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476017"
---
# <a name="coleobjectfactory-class"></a>COleObjectFactory sınıfı

Sınıf sunucuları, Otomasyon nesneleri ve belgeler gibi OLE nesnelerini oluşturan üretecini uygular.

## <a name="syntax"></a>Sözdizimi

```
class COleObjectFactory : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|Oluşturur bir `COleObjectFactory` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleObjectFactory::GetClassID](#getclassid)|OLE döndürür sınıfı oluşturur bu üretecin nesne kimliği.|
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|Denetimin Lisans geçerli olup olmadığını belirler.|
|[COleObjectFactory::IsRegistered](#isregistered)|Nesne üreteci OLE sistem DLL'lerini kayıtlı olup olmadığını gösterir.|
|[COleObjectFactory::Register](#register)|Bu nesne üreteci OLE sistem DLL'lerini kaydeder.|
|[COleObjectFactory::RegisterAll](#registerall)|Uygulamanın nesne fabrikaları tüm OLE sistem DLL'lerini kaydeder.|
|[COleObjectFactory::Revoke](#revoke)|OLE sistem DLL'lerini ile bu nesne fabrikasının kaydı iptal eder.|
|[COleObjectFactory::RevokeAll](#revokeall)|OLE sistem DLL'lerini uygulamanın nesne fabrikaları kayıtlarla iptal eder.|
|[COleObjectFactory::UnregisterAll](#unregisterall)|Tüm uygulama nesnesi fabrikaları kaydını siler.|
|[COleObjectFactory::UpdateRegistry](#updateregistry)|Bu nesne üreteci OLE sistem kayıt defteri ile kaydeder.|
|[COleObjectFactory::UpdateRegistryAll](#updateregistryall)|Uygulamanın nesne fabrikaları tüm OLE sistem kayıt defteri ile kaydeder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|Benzersiz bir anahtar denetimin DLL'den ister.|
|[COleObjectFactory::OnCreateObject](#oncreateobject)|Bu fabrikasının türünde yeni bir nesne oluşturmak için framework tarafından çağırılır.|
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|Katıştırılmış denetime anahtar kapsayıcısında katıştırılmış anahtar eşleştiğini doğrular.|
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|Denetim tasarım zamanı kullanım için lisanslanmıştır doğrular.|

## <a name="remarks"></a>Açıklamalar

`COleObjectFactory` Sınıfın üye işlevleri, aşağıdaki işlevleri gerçekleştirmek için vardır:

- Nesneleri kaydını yönetme.

- OLE nesneleri çalıştırıyorsanız ve iletileri almaya hazır bildirir çalışma zamanı kayıt yanı sıra OLE sistemin yazmaç güncelleştiriliyor.

- Tasarım zamanında lisanslı geliştiriciler ve lisanslı uygulamalar çalışma zamanında denetim kullanımını sınırlayarak lisans zorlama.

- Denetim nesnesi fabrikaları OLE sistem kayıt defteri ile kaydediliyor.

Nesne oluşturma hakkında daha fazla bilgi için makalelere göz atın [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md) ve [veri nesneleri ve veri kaynakları: oluşturma ve yok etme](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Kayıt hakkında daha fazla bilgi için bkz [kayıt](../../mfc/registration.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleObjectFactory`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="coleobjectfactory"></a>  COleObjectFactory::COleObjectFactory

Oluşturur bir `COleObjectFactory` nesnesi, bir kaydı nesne üreteci başlatır ve fabrikaları listesine ekler.

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

*CLSID*<br/>
OLE sınıf kimliği bu nesne üreteci başvuruyu temsil eder.

*pRuntimeClass*<br/>
Bu fabrika oluşturabilirsiniz C++ nesnelerin çalışma zamanı sınıf işaretçisi.

*Bmultiınstance*<br/>
Tek bir örnek uygulamanın birden çok örneklemesini destekleyip desteklemediğini gösterir. TRUE ise bir nesne oluşturmak için her istek için uygulamanın birden fazla örneği başlatılabilir.

*nFlags*<br/>
Bir veya daha fazla aşağıdaki bayraklar içerir:

- `afxRegDefault` ThreadingModel için iş parçacığı modeli ayarlar Grup =.

- `afxRegInsertable` Denetimin görünür izin **Nesne Ekle** OLE nesneleri için iletişim kutusu.

- `afxRegApartmentThreading` İş parçacığı modeli ThreadingModel kayıt defterindeki ayarlar Grup =.

- `afxRegFreeThreading` İş parçacığı modeli ThreadingModel kayıt defterindeki ayarlar ücretsiz =.

   İki bayrak birleştirebilirsiniz `afxRegApartmentThreading` ve `afxRegFreeThreading` ThreadingModel ayarlamak için her ikisi =. Bkz: [Inprocserver32](/windows/desktop/com/inprocserver32) model kaydı iş parçacığı oluşturma hakkında daha fazla bilgi için Windows SDK.

*lpszProgID*<br/>
"Microsoft Excel" gibi bir sözlü program tanımlayıcı içeren bir dize işaretçisi

### <a name="remarks"></a>Açıklamalar

Nesne kullanmak için ancak kaydetmelisiniz.

Daha fazla bilgi için [CLSID anahtar](/windows/desktop/com/clsid-key-hklm) Windows SDK.

##  <a name="getclassid"></a>  COleObjectFactory::GetClassID

Bu üretecini temsil eder OLE sınıf kimliği için bir başvuru döndürür.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Dönüş Değeri

OLE sınıf kimliği bu Fabrika başvuruyu temsil eder.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [CLSID anahtar](/windows/desktop/com/clsid-key-hklm) Windows SDK.

##  <a name="getlicensekey"></a>  COleObjectFactory::GetLicenseKey

Denetimin DLL'den benzersiz lisans anahtarı ister ve onu işaret ettiği BSTR depolar *pbstrKey*.

```
virtual BOOL GetLicenseKey(
    DWORD dwReserved,
    BSTR* pbstrKey);
```

### <a name="parameters"></a>Parametreler

*dwReserved*<br/>
Daha sonraki kullanımlar için ayrılmıştır.

*pbstrKey*<br/>
Lisans anahtarı depolayacak BSTR işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Lisans anahtarı dizesi boş değilse sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını 0 döndürür ve hiçbir şey BSTR içinde depolar. MFC ActiveX ControlWizard projenizi oluşturmak için kullanıyorsanız, denetimin lisans anahtarı alır. bir geçersiz kılma ControlWizard sağlar.

##  <a name="islicensevalid"></a>  COleObjectFactory::IsLicenseValid

Denetimin Lisans geçerli olup olmadığını belirler.

```
BOOL IsLicenseValid();
```

### <a name="return-value"></a>Dönüş Değeri

TRUE ise başarılı; Aksi durumda false.

##  <a name="isregistered"></a>  COleObjectFactory::IsRegistered

OLE sistem DLL'lerini Fabrika kayıtlıysa, sıfır olmayan bir değer döndürür.

```
virtual BOOL IsRegistered() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika kayıtlı olursa sıfır dışı; Aksi durumda 0.

##  <a name="oncreateobject"></a>  COleObjectFactory::OnCreateObject

Yeni bir nesne oluşturmak için framework tarafından çağırılır.

```
virtual CCmdTarget* OnCreateObject();
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturulan nesneye bir işaretçi. Başarısız olursa, yetersiz bellek özel durum.

### <a name="remarks"></a>Açıklamalar

Başka bir nesne oluşturmak için bu işlevi geçersiz kılma [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) oluşturucuya geçirilen.

##  <a name="register"></a>  COleObjectFactory::Register

Bu nesne üreteci OLE sistem DLL'lerini kaydeder.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika başarıyla kaydettirildi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin genellikle çağıran [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) uygulamanın ne zaman başlatılır.

##  <a name="registerall"></a>  COleObjectFactory::RegisterAll

Uygulamanın nesne fabrikaları tüm OLE sistem DLL'lerini kaydeder.

```
static BOOL PASCAL RegisterAll();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrikalar başarıyla kaydoldunuz olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin genellikle çağıran [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) uygulamanın ne zaman başlatılır.

##  <a name="revoke"></a>  COleObjectFactory::Revoke

OLE sistem DLL'lerini ile bu nesne fabrikasının kaydı iptal eder.

```
void Revoke();
```

### <a name="remarks"></a>Açıklamalar

Uygulama sonlandırılmadan önce framework otomatik olarak bu işlevi çağırır. Gerekirse, geçersiz kılma çağrısından [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).

##  <a name="revokeall"></a>  COleObjectFactory::RevokeAll

Tüm OLE sistem DLL'lerini uygulamanın nesne fabrikaları kayıtlarla iptal eder.

```
static void PASCAL RevokeAll();
```

### <a name="remarks"></a>Açıklamalar

Uygulama sonlandırılmadan önce framework otomatik olarak bu işlevi çağırır. Gerekirse, geçersiz kılma çağrısından [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).

##  <a name="unregisterall"></a>  COleObjectFactory::UnregisterAll

Tüm uygulama nesnesi fabrikaları kaydını siler.

```
static BOOL PASCAL UnregisterAll();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE; Aksi durumda FALSE.

##  <a name="updateregistry"></a>  COleObjectFactory::UpdateRegistry

Uygulamanın nesne fabrikaları tüm OLE sistem kayıt defteri ile kaydeder.

```
void UpdateRegistry(LPCTSTR lpszProgID = NULL);
virtual BOOL UpdateRegistry(BOOL bRegister);
```

### <a name="parameters"></a>Parametreler

*lpszProgID*<br/>
"Excel.Document.5." gibi bir kullanıcı tarafından okunabilen program tanımlayıcısını içeren bir dize işaretçisi

*bRegister*<br/>
Denetim sınıfın nesne üreteci kaydedilecek olup olmadığını belirler.

### <a name="remarks"></a>Açıklamalar

Bu işlev için iki biçim kısa tartışmalar izleyin:

- **UpdateRegistry (** `lpszProgID` **)** OLE sistem kayıt defteri ile bu nesne üreteci kaydeder. Bu işlevin genellikle çağıran [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) uygulamanın ne zaman başlatılır.

- **UpdateRegistry (** `bRegister` **)** bu işlev geçersiz kılınabilir şeklidir. Varsa *bRegister* true, denetim sınıf sistem kayıt defteri ile bu işlevi kaydeder. Aksi takdirde, sınıf kaydını siler.

   MFC ActiveX ControlWizard projenizi oluşturmak için kullanıyorsanız, bu saf sanal işlevi geçersiz kılma ControlWizard sağlar.

##  <a name="updateregistryall"></a>  COleObjectFactory::UpdateRegistryAll

Uygulamanın nesne fabrikaları tüm OLE sistem kayıt defteri ile kaydeder.

```
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Parametreler

*bRegister*<br/>
Denetim sınıfın nesne üreteci kaydedilecek olup olmadığını belirler.

### <a name="return-value"></a>Dönüş Değeri

Fabrikalar başarıyla güncellendi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin genellikle çağıran [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) uygulamanın ne zaman başlatılır.

##  <a name="verifylicensekey"></a>  COleObjectFactory::VerifyLicenseKey

OLE denetim kullanmak için kapsayıcı lisanslanır doğrular.

```
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```

### <a name="parameters"></a>Parametreler

*bstrKey*<br/>
Lisans dize kapsayıcının sürümünü depolamak BSTR.

### <a name="return-value"></a>Dönüş Değeri

Çalışma zamanı lisansı geçerli ise sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan sürüm çağrıları [GetLicenseKey](#getlicensekey) denetimin bir kopyasını almak için kullanıcının lisans dize ve dize ile karşılaştırır *bstrKey*. İki dizenin eşleşirse, işlev sıfır olmayan bir değer döndürür; Aksi takdirde 0 değerini döndürür.

Özelleştirilmiş lisans sağlamak için bu işlevi geçersiz kılabilirsiniz.

İşlev [VerifyUserLicense](#verifyuserlicense) tasarım zamanı lisansı doğrular.

##  <a name="verifyuserlicense"></a>  COleObjectFactory::VerifyUserLicense

OLE denetimi tasarım zamanı lisansı doğrular.

```
virtual BOOL VerifyUserLicense();
```

### <a name="return-value"></a>Dönüş Değeri

Tasarım zamanı lisansı geçerli ise sıfır olmayan; Aksi durumda 0.

## <a name="see-also"></a>Ayrıca Bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleTemplateServer Sınıfı](../../mfc/reference/coletemplateserver-class.md)
