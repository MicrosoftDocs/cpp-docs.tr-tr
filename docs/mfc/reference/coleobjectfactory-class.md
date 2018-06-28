---
title: COleObjectFactory sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 706cc03e3f0a074e68d0e92acdce5a747552819b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038215"
---
# <a name="coleobjectfactory-class"></a>COleObjectFactory sınıfı
Implements OLE sunucuları, Otomasyon nesneleri ve belgeler gibi OLE nesneleri oluşturur fabrika sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|Oluşturan bir `COleObjectFactory` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleObjectFactory::GetClassID](#getclassid)|Sınıfı bu üreteci oluşturur nesnelerin kimliği OLE döndürür.|  
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|Lisans denetiminin geçerli olup olmadığını belirler.|  
|[COleObjectFactory::IsRegistered](#isregistered)|Nesne üreteci OLE sistem DLL'leri ile kayıtlı olup olmadığını gösterir.|  
|[COleObjectFactory::Register](#register)|Bu nesne üreteci OLE sistem DLL'leri ile kaydeder.|  
|[COleObjectFactory::RegisterAll](#registerall)|Tüm uygulama nesne oluşturucuları OLE sistem DLL'leri ile kaydeder.|  
|[COleObjectFactory::Revoke](#revoke)|Bu nesne fabrikasının kayıt OLE sistem DLL'leri ile iptal eder.|  
|[COleObjectFactory::RevokeAll](#revokeall)|Bir uygulamanın nesne oluşturucuları kayıtlar OLE sistem DLL'leri ile iptal eder.|  
|[COleObjectFactory::UnregisterAll](#unregisterall)|Bir uygulamanın nesne oluşturucuları tümünün kaydını siler.|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|Bu nesne üreteci OLE sistem kayıt defteri ile kaydeder.|  
|[COleObjectFactory::UpdateRegistryAll](#updateregistryall)|Tüm uygulama nesne oluşturucuları OLE sistem kayıt defteri ile kaydeder.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|Benzersiz bir anahtar denetimin DLL'den ister.|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|Bu fabrikasının türünde yeni bir nesne oluşturmak için çerçevesi tarafından çağrılır.|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|Denetimde katıştırılmış anahtar kapsayıcısında katıştırılmış anahtar eşleştiğini doğrular.|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|Denetim tasarım zamanı kullanım için lisanslanmıştır doğrular.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleObjectFactory` Sınıfı aşağıdaki işlevleri gerçekleştirmek için üye işlevleri vardır:  
  
-   Nesneleri kaydını yönetme.  
  
-   OLE nesneleri çalıştırıyorsanız ve iletileri almaya hazır bildirir çalışma zamanı kayıt yanı sıra OLE sistem kaydı güncelleştiriliyor.  
  
-   Tasarım zamanında lisanslı geliştiriciler ve lisanslı uygulamalar çalışma zamanında denetim kullanımını sınırlayarak lisans zorlama.  
  
-   Denetim nesne oluşturucuları OLE sistem kayıt defteri ile kaydediliyor.  
  
 Nesne oluşturma hakkında daha fazla bilgi için makalelerine bakın [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md) ve [veri nesneleri ve veri kaynakları: oluşturma ve yok etme](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Kayıt hakkında daha fazla bilgi için bkz: [kayıt](../../mfc/registration.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
##  <a name="coleobjectfactory"></a>  COleObjectFactory::COleObjectFactory  
 Oluşturan bir `COleObjectFactory` nesnesi, bir kaydı nesne üreteci başlatır ve oluşturucuları listesine ekler.  
  
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
 *CLSID*  
 Bu nesne üreteci temsil eder OLE sınıfı Kimliğine başvuru.  
  
 *pRuntimeClass*  
 Çalışma zamanı sınıfı bu Fabrika oluşturabilirsiniz C++ nesnelerinin işaretçi.  
  
 *bMultiInstance*  
 Tek bir örnek uygulamanın birden fazla desteği olup olmadığını gösterir. Varsa **doğru**, uygulamanın birden çok örneğini bir nesne oluşturmak her istek için başlatılır.  
  
 *nFlags*  
 Bir veya daha fazla aşağıdaki bayraklar içerir:  
  
- **afxRegDefault** ThreadingModel için iş parçacığı modelini ayarlar Grup =.  
  
- **Afxregınsertable** görünmesi denetimi sağlar **Nesne Ekle** OLE nesneleri için iletişim kutusu.  
  
- **afxRegApartmentThreading** ThreadingModel için kayıt defterindeki iş parçacığı modelini ayarlar Grup =.  
  
- **afxRegFreeThreading** ThreadingModel için kayıt defterindeki iş parçacığı modelini ayarlar serbest =.  
  
     İki bayrak birleştirebilirsiniz `afxRegApartmentThreading` ve `afxRegFreeThreading` ThreadingModel ayarlamak için her ikisini de =. Bkz: [Inprocserver32](http://msdn.microsoft.com/library/windows/desktop/ms682390) modeli kaydı iş parçacığı oluşturma hakkında daha fazla bilgi için Windows SDK'sındaki.  
  
 *lpszProgID*  
 "Microsoft Excel." gibi bir sözlü program tanımlayıcısını içeren bir dize işaretçi  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne kullanmak için Bununla birlikte, onu kaydetmeniz gerekir.  
  
 Daha fazla bilgi için bkz: [CLSID anahtarı](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK'sındaki.  
  
##  <a name="getclassid"></a>  COleObjectFactory::GetClassID  
 Bu üretecini temsil eder OLE sınıf kimliği için bir başvuru döndürür.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE sınıfı kimliği bu Fabrika referansı temsil eder.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [CLSID anahtarı](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK'sındaki.  
  
##  <a name="getlicensekey"></a>  COleObjectFactory::GetLicenseKey  
 Denetimin DLL'den benzersiz lisans anahtarı ister ve depolar `BSTR` gösterdiği *pbstrKey*.  
  
```  
virtual BOOL GetLicenseKey(
    DWORD dwReserved,  
    BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwReserved*  
 Daha sonraki kullanımlar için ayrılmıştır.  
  
 *pbstrKey*  
 İşaretçi bir `BSTR` lisans anahtarı depolar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Lisans anahtarı dizesi değilse sıfır olmayan **NULL**; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması 0 döndürür ve hiçbir depolar `BSTR`. MFC ActiveX ControlWizard projenizi oluşturmak için kullanırsanız, denetimin lisans anahtarı alır bir geçersiz kılma ControlWizard sağlar.  
  
##  <a name="islicensevalid"></a>  COleObjectFactory::IsLicenseValid  
 Lisans denetiminin geçerli olup olmadığını belirler.  
  
```  
BOOL IsLicenseValid();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE ise başarılı; Aksi takdirde false.  
  
##  <a name="isregistered"></a>  COleObjectFactory::IsRegistered  
 Fabrika OLE sistem DLL'leri kaydedilmişse sıfır olmayan bir değer döndürür.  
  
```  
virtual BOOL IsRegistered() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Fabrika kaydedilmişse sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="oncreateobject"></a>  COleObjectFactory::OnCreateObject  
 Yeni bir nesne oluşturmak için çerçevesi tarafından çağrılır.  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Oluşturulan nesnesi için bir işaretçi. Başarısız olursa bir bellek özel atabilirsiniz.  
  
### <a name="remarks"></a>Açıklamalar  
 Başka bir nesne oluşturmak için bu işlevi geçersiz kılma [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) oluşturucuya geçirilen.  
  
##  <a name="register"></a>  COleObjectFactory::Register  
 Bu nesne üreteci OLE sistem DLL'leri ile kaydeder.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Fabrika başarıyla kaydedilmişse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev genellikle tarafından çağrılır [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) uygulama başlatıldığı zaman.  
  
##  <a name="registerall"></a>  COleObjectFactory::RegisterAll  
 Tüm uygulama nesne oluşturucuları OLE sistem DLL'leri ile kaydeder.  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Oluşturucuları başarıyla kaydedilmişse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev genellikle tarafından çağrılır [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) uygulama başlatıldığı zaman.  
  
##  <a name="revoke"></a>  COleObjectFactory::Revoke  
 Bu nesne fabrikasının kayıt OLE sistem DLL'leri ile iptal eder.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama kapatılmadan önce framework bu işlev otomatik olarak çağırır. Gerekirse, geçersiz kılıyorsa, çağrı [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="revokeall"></a>  COleObjectFactory::RevokeAll  
 OLE sistem DLL'leri uygulamanın nesne oluşturucuları kayıtlarla tümünün iptal eder.  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama kapatılmadan önce framework bu işlev otomatik olarak çağırır. Gerekirse, geçersiz kılıyorsa, çağrı [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="unregisterall"></a>  COleObjectFactory::UnregisterAll  
 Bir uygulamanın nesne oluşturucuları tümünün kaydını siler.  
  
```  
static BOOL PASCAL UnregisterAll();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="updateregistry"></a>  COleObjectFactory::UpdateRegistry  
 Tüm uygulama nesne oluşturucuları OLE sistem kayıt defteri ile kaydeder.  
  
```  
void UpdateRegistry(LPCTSTR lpszProgID = NULL);  
virtual BOOL UpdateRegistry(BOOL bRegister);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszProgID*  
 "Excel.Document.5." gibi okunabilir program tanımlayıcısını içeren bir dize işaretçi  
  
 *bRegister*  
 Denetim sınıfının nesne üreteci kaydedilmesi olup olmadığını belirler.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev için iki formları kısa tartışmalar izleyin:  
  
- **UpdateRegistry (** `lpszProgID` **)** OLE sistem kayıt defteri ile bu nesne üreteci kaydeder. Bu işlev genellikle tarafından çağrılır [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) uygulama başlatıldığı zaman.  
  
- **UpdateRegistry (** `bRegister` **)** bu işlevi geçersiz kılınabilir biçimidir. Varsa *bRegister* olan **doğru**, bu işlev control sınıfı sistem kayıt defteri ile kaydeder. Aksi takdirde, sınıf kaydını siler.  
  
     MFC ActiveX ControlWizard projenizi oluşturmak için kullanırsanız, bu saf sanal işlevi geçersiz kılma ControlWizard sağlar.  
  
##  <a name="updateregistryall"></a>  COleObjectFactory::UpdateRegistryAll  
 Tüm uygulama nesne oluşturucuları OLE sistem kayıt defteri ile kaydeder.  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bRegister*  
 Denetim sınıfının nesne üreteci kaydedilmesi olup olmadığını belirler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Oluşturucuları başarıyla güncelleştirilirse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev genellikle tarafından çağrılır [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) uygulama başlatıldığı zaman.  
  
##  <a name="verifylicensekey"></a>  COleObjectFactory::VerifyLicenseKey  
 Kapsayıcı OLE denetimi kullanmak için lisanslanmıştır doğrular.  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>Parametreler  
 *bstrKey*  
 A `BSTR` lisans dize kapsayıcının sürümünü depolamayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çalışma zamanı lisans geçerliyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan sürüm çağrıları [GetLicenseKey](#getlicensekey) denetimi bir kopyasını almak için lisans dize adı ve dizesinde ile karşılaştırır *bstrKey*. İki dizeyi eşleşiyorsa işlevi sıfır olmayan bir değer döndürür; Aksi halde 0 döndürür.  
  
 Lisans özelleştirilmiş doğrulama sağlamak için bu işlevi geçersiz kılabilirsiniz.  
  
 İşlev [VerifyUserLicense](#verifyuserlicense) tasarım zamanı lisans doğrular.  
  
##  <a name="verifyuserlicense"></a>  COleObjectFactory::VerifyUserLicense  
 OLE denetim tasarım zamanı lisansını doğrular.  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tasarım zamanı lisans geçerliyse sıfır olmayan; Aksi takdirde 0.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer Sınıfı](../../mfc/reference/coletemplateserver-class.md)
