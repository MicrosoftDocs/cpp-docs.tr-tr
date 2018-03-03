---
title: "CAtlExeModuleT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::InitializeCom
- ATLBASE/ATL::CAtlExeModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlExeModuleT::PostMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::RegisterClassObjects
- ATLBASE/ATL::CAtlExeModuleT::RevokeClassObjects
- ATLBASE/ATL::CAtlExeModuleT::Run
- ATLBASE/ATL::CAtlExeModuleT::RunMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::UninitializeCom
- ATLBASE/ATL::CAtlExeModuleT::Unlock
- ATLBASE/ATL::CAtlExeModuleT::WinMain
- ATLBASE/ATL::CAtlExeModuleT::m_bDelayShutdown
- ATLBASE/ATL::CAtlExeModuleT::m_dwPause
- ATLBASE/ATL::CAtlExeModuleT::m_dwTimeOut
dev_langs:
- C++
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c45b1f95aba4f11e6995bf5c4c1cfff00627e4b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT sınıfı
Bu sınıf, bir uygulama için modülü temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınızda türetilmiş `CAtlExeModuleT`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|Oluşturucu.|  
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlExeModuleT::InitializeCom](#initializecom)|COM başlatır|  
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Komut satırını ayrıştırır ve gerekiyorsa, kayıt işlemini gerçekleştirir.|  
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|Bu yöntem, ileti döngüsü hemen çıktıktan sonra çağrılır.|  
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Bu yöntem, ileti döngüsü hemen girmeden önce çağrılır.|  
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|Sınıf nesnesi kaydeder.|  
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|Sınıf nesnesi iptal eder.|  
|[CAtlExeModuleT::Run](#run)|Bu yöntem başlatmak, ileti döngüsü çalıştırmak EXE modülünde kodu yürütür ve temizleme.|  
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Bu yöntem, ileti döngü yürütür.|  
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|COM uninitializes|  
|[CAtlExeModuleT::Unlock](#unlock)|Azaltır modülün kilit sayısı.|  
|[CAtlExeModuleT::WinMain](#winmain)|Bu yöntem bir EXE çalıştırmak için gerekli kod uygular.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Modülü kapatılıyor bir gecikme olmalıdır belirten bir bayrak.|  
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Tüm nesneler kapatma öncesinde yayımlanan sağlamak için kullanılan bir duraklama değer.|  
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Modül, eklentiyi gecikme için kullanılan bir zaman aşımı değeri.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAtlExeModuleT`bir uygulama (EXE) için modülü temsil eder ve bir EXE oluşturma, komut satırı işleme, sınıf nesnelerine kaydetme, ileti döngüsü çalıştıran ve temizleme Çıkışta destekleyen kodunu içerir.  
  
 Bu sınıf, COM nesneleri EXE Server'daki sürekli olarak oluşturulan ve yok olduğunda performansını artırmak için tasarlanmıştır. Son COM nesnesi yayımlandıktan sonra EXE tarafından belirtilen bir süre bekler [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) veri üyesi. Bu süre zarfında etkinlik yoksa (diğer bir deyişle, hiçbir COM nesneleri oluşturma), kapatma işlemi başlatıldı.  
  
 [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) veri üyesi olduğu EXE yukarıda tanımlanan mekanizması kullanmanızın gerekli olup olmadığını belirlemek için kullanılan bir bayrak. False olarak ayarlanırsa, modül hemen sonlandırılacak.  
  
 ATL modülleri hakkında daha fazla bilgi için bkz: [ATL modül sınıfları](../../atl/atl-module-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="catlexemodulet"></a>CAtlExeModuleT::CAtlExeModuleT  
 Oluşturucu.  
  
```
CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 EXE modülü başlatılamadı, WinMain hemen başka bir işleme olmadan döndürür.  
  
##  <a name="dtor"></a>CAtlExeModuleT:: ~ CAtlExeModuleT  
 Yok Edicisi.  
  
```
~CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="initializecom"></a>CAtlExeModuleT::InitializeCom  
 COM başlatır  
  
```
static HRESULT InitializeCom() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturucusundan çağrılır ve COM varsayılan uygulamasından farklı bir şekilde başlatmak için geçersiz kılınabilir. Varsayılan uygulama ya da çağıran **CoInitializeEx (NULL, COINIT_MULTITHREADED)** veya **CoInitialize(NULL)** proje yapılandırmasına bağlı olarak.  
  
 Normalde bu yöntemi geçersiz kılma gerektirir geçersiz kılma [CAtlExeModuleT::UninitializeCom](#uninitializecom).  
  
##  <a name="m_bdelayshutdown"></a>CAtlExeModuleT::m_bDelayShutdown  
 Modülü kapatılıyor bir gecikme olmalıdır belirten bir bayrak.  
  
```
bool m_bDelayShutdown;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CAtlExeModuleT genel bakış](../../atl/reference/catlexemodulet-class.md) Ayrıntılar için.  
  
##  <a name="m_dwpause"></a>CAtlExeModuleT::m_dwPause  
 Tüm nesneleri önce kapatılması gitti sağlamak için kullanılan bir duraklama değer.  
  
```
DWORD m_dwPause;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıldıktan sonra bu değeri değiştirmek [CAtlExeModuleT::InitializeCom](#initializecom) Sunucu kapatılıyor için Duraklat değeri olarak kullanılan milisaniye sayısını ayarlamak için. Varsayılan değer 1000 milisaniyedir.  
  
##  <a name="m_dwtimeout"></a>CAtlExeModuleT::m_dwTimeOut  
 Modül, eklentiyi gecikme için kullanılan bir zaman aşımı değeri.  
  
```
DWORD m_dwTimeOut;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıldıktan sonra bu değeri değiştirmek [CAtlExeModuleT::InitializeCom](#initializecom) Sunucu kapatılıyor için zaman aşımı değeri olarak kullanılan milisaniye sayısını tanımlamak için. Varsayılan değer 5000 milisaniyedir. Bkz: [CAtlExeModuleT genel bakış](../../atl/reference/catlexemodulet-class.md) daha fazla ayrıntı için.  
  
##  <a name="parsecommandline"></a>CAtlExeModuleT::ParseCommandLine  
 Komut satırını ayrıştırır ve gerekiyorsa, kayıt işlemini gerçekleştirir.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpCmdLine`  
 Komut satırı uygulamaya geçirildi.  
  
 `pnRetCode`  
 (Yer gerçekleştirirse) kayda karşılık gelen HRESULT.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulama, aksi takdirde false çalışmaya devam etmesi gerekiyorsa true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem çağrılır [CAtlExeModuleT::WinMain](#winmain) ve komut satırı anahtarları işlemek için geçersiz kılınabilir. Varsayılan uygulama kontrol **/regserver** ve **/Unregserver** komut satırı bağımsız değişkenleri ve kayıt veya silme gerçekleştirir.  
  
##  <a name="postmessageloop"></a>CAtlExeModuleT::PostMessageLoop  
 Bu yöntem, ileti döngüsü hemen çıktıktan sonra çağrılır.  
  
```
HRESULT PostMessageLoop() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel uygulama temizleme gerçekleştirmek için bu yöntemi geçersiz kılın. Varsayılan Uygulama çağrıları [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects).  
  
##  <a name="premessageloop"></a>CAtlExeModuleT::PreMessageLoop  
 Bu yöntem, ileti döngüsü hemen girmeden önce çağrılır.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nShowCmd`  
 Olarak geçirilen değeri `nShowCmd` WinMain parametresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama için özel başlatma kodu eklemek için bu yöntemi geçersiz kılın. Varsayılan uygulama sınıf nesneleri kaydeder.  
  
##  <a name="registerclassobjects"></a>CAtlExeModuleT::RegisterClassObjects  
 Diğer uygulamalar için bağlanabilmesi için sınıf nesnesi ile OLE kaydeder.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *dwClsContext*  
 Sınıf nesnesi çalıştırılsın mı bağlam belirtir. Olası değerler CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER olur.  
  
 `dwFlags`  
 Bağlantı türleri sınıf nesnesine belirler. Olası değerler REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, kaydetmek için hiçbir sınıfları olsaydı S_FALSE veya hatasında bir hata HRESULT S_OK döndürür.  
  
##  <a name="revokeclassobjects"></a>CAtlExeModuleT::RevokeClassObjects  
 Sınıf nesnesi kaldırır.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, kaydetmek için hiçbir sınıfları olsaydı S_FALSE veya hatasında bir hata HRESULT S_OK döndürür.  
  
##  <a name="run"></a>CAtlExeModuleT::Run  
 Bu yöntem başlatmak, ileti döngüsü çalıştırmak EXE modülünde kodu yürütür ve temizleme.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nShowCmd`  
 Nasıl penceresi gösterilecek belirtir. Bu parametre ele değerlerden biri olabilir [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) bölümü. Varsayılan olarak SW_HIDE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem geçersiz kılınabilir. Bununla birlikte, pratikte, geçersiz kılmak için iyidir [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), veya [CAtlExeModuleT::PostMessageLoop](#postmessageloop) Bunun yerine.  
  
##  <a name="runmessageloop"></a>CAtlExeModuleT::RunMessageLoop  
 Bu yöntem, ileti döngü yürütür.  
  
```
void RunMessageLoop() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İleti döngüsü davranışını değiştirmek için bu yöntem geçersiz kılınabilir.  
  
##  <a name="uninitializecom"></a>CAtlExeModuleT::UninitializeCom  
 COM uninitializes  
  
```
static void UninitializeCom() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak yalnızca bu yöntemi çağırır [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715) ve yıkıcı olarak adlandırılır. Geçersiz bu yöntemi geçersiz kılın [CAtlExeModuleT::InitializeCom](#initializecom).  
  
##  <a name="unlock"></a>CAtlExeModuleT::Unlock  
 Azaltır modülün kilit sayısı.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için yararlı veya test olabilen bir değer döndürür.  
  
##  <a name="winmain"></a>CAtlExeModuleT::WinMain  
 Bu yöntem bir EXE çalıştırmak için gerekli kod uygular.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nShowCmd`  
 Nasıl penceresi gösterilecek belirtir. Bu parametre ele değerlerden biri olabilir [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) bölümü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yürütülebilir dosya'nın dönüş değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem geçersiz kılınabilir. Kılıyorsa [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::PostMessageLoop](#postmessageloop), veya [CAtlExeModuleT::RunMessageLoop](#runmessageloop) yeterli esneklik sağlamaz , geçersiz kılmak mümkündür `WinMain` bu yöntemi kullanarak işlev.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATLDuck örnek](../../visual-cpp-samples.md)   
 [CAtlModuleT sınıfı](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT sınıfı](../../atl/reference/catldllmodulet-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
