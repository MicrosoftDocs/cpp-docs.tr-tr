---
title: "CAtlServiceModuleT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::Handler
- ATLBASE/ATL::CAtlServiceModuleT::InitializeSecurity
- ATLBASE/ATL::CAtlServiceModuleT::Install
- ATLBASE/ATL::CAtlServiceModuleT::IsInstalled
- ATLBASE/ATL::CAtlServiceModuleT::LogEvent
- ATLBASE/ATL::CAtlServiceModuleT::OnContinue
- ATLBASE/ATL::CAtlServiceModuleT::OnInterrogate
- ATLBASE/ATL::CAtlServiceModuleT::OnPause
- ATLBASE/ATL::CAtlServiceModuleT::OnShutdown
- ATLBASE/ATL::CAtlServiceModuleT::OnStop
- ATLBASE/ATL::CAtlServiceModuleT::OnUnknownRequest
- ATLBASE/ATL::CAtlServiceModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlServiceModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlServiceModuleT::RegisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::Run
- ATLBASE/ATL::CAtlServiceModuleT::ServiceMain
- ATLBASE/ATL::CAtlServiceModuleT::SetServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::Start
- ATLBASE/ATL::CAtlServiceModuleT::Uninstall
- ATLBASE/ATL::CAtlServiceModuleT::Unlock
- ATLBASE/ATL::CAtlServiceModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::WinMain
- ATLBASE/ATL::CAtlServiceModuleT::m_bService
- ATLBASE/ATL::CAtlServiceModuleT::m_dwThreadID
- ATLBASE/ATL::CAtlServiceModuleT::m_hServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::m_status
- ATLBASE/ATL::CAtlServiceModuleT::m_szServiceName
dev_langs: C++
helpviewer_keywords: CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c2d059a990b9b01cdfc959284d9fe20f3dfd12af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT sınıfı
Bu sınıf, bir hizmet uygular.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, UINT nServiceNameID>  
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınızda türetilmiş `CAtlServiceModuleT`.  
  
 *nServiceNameID*  
 Hizmet kaynak tanımlayıcısı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlServiceModuleT::Handler](#handler)|Hizmeti için işleyici yordamı.|  
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|Varsayılan hizmet için güvenlik ayarları sağlar.|  
|[CAtlServiceModuleT::Install](#install)|Yükler ve hizmet oluşturur.|  
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|Hizmeti yüklü olduğunu doğrular.|  
|[CAtlServiceModuleT::LogEvent](#logevent)|Olay günlüğüne yazar.|  
|[CAtlServiceModuleT::OnContinue](#oncontinue)|Hizmeti sürdürmek için bu yöntemi geçersiz kılın.|  
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|Sorgulama hizmeti için bu yöntemi geçersiz kılın.|  
|[CAtlServiceModuleT::OnPause](#onpause)|Hizmeti duraklatmak için bu yöntemi geçersiz kılın.|  
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|Hizmeti kapatmak için bu yöntemi geçersiz kılın|  
|[CAtlServiceModuleT::OnStop](#onstop)|Hizmeti durdurmak için bu yöntemi geçersiz kılın|  
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|Hizmet bilinmeyen isteklerini işlemek için bu yöntemi geçersiz kılın|  
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Komut satırını ayrıştırır ve gerekiyorsa, kayıt işlemini gerçekleştirir.|  
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Bu yöntem, ileti döngüsü hemen girmeden önce çağrılır.|  
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Hizmet kayıt defterinde kaydeder.|  
|[CAtlServiceModuleT::Run](#run)|Hizmet çalışır.|  
|[CAtlServiceModuleT::ServiceMain](#servicemain)|Hizmet Denetimi Yöneticisi tarafından çağrılan yöntemi.|  
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Hizmet durumunu güncelleştirir.|  
|[CAtlServiceModuleT::Start](#start)|Tarafından çağrılır `CAtlServiceModuleT::WinMain` zaman hizmetini başlatır.|  
|[CAtlServiceModuleT::Uninstall](#uninstall)|Durdurur ve hizmeti kaldırır.|  
|[CAtlServiceModuleT::Unlock](#unlock)|Azaltır hizmetin kilit sayısı.|  
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|Hizmet kayıt defterinden kaldırır.|  
|[CAtlServiceModuleT::WinMain](#winmain)|Bu yöntem hizmetini çalıştırmak için gerekli kod uygular.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlServiceModuleT::m_bService](#m_bservice)|Program hizmet olarak çalışan belirten bayrak.|  
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|İş parçacığı tanımlayıcısı depolama üye değişkeni.|  
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|Üye değişkeni için geçerli hizmet durumu bilgileri yapısı için bir tanıtıcı depolama.|  
|[CAtlServiceModuleT::m_status](#m_status)|Üye değişkeni için geçerli hizmet durumu bilgileri yapısı depolama.|  
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|Kayıtlı hizmet adı.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAtlServiceModuleT`, türetilmiş [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), ATL hizmet modül uygular. `CAtlServiceModuleT`komut satırı işleme, yükleme, kaydetme ve kaldırma için yöntemleri sağlar. Fazladan işlevsellik gerekiyorsa, bunlar ve diğer yöntemleri geçersiz kılınabilir.  
  
 Bu sınıf artık kullanılmıyor değiştirir [CComModule sınıfı](../../atl/reference/ccommodule-class.md) ATL önceki sürümlerinde kullanılan Bkz: [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="catlservicemodulet"></a>CAtlServiceModuleT::CAtlServiceModuleT  
 Oluşturucu.  
  
```
CAtlServiceModuleT() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Veri üyeleri başlatır ve ilk hizmet durumunu ayarlar.  
  
##  <a name="handler"></a>CAtlServiceModuleT::Handler  
 Hizmeti için işleyici yordamı.  
  
```
void Handler(DWORD dwOpcode) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *dwOpcode*  
 İşleyici işlemi tanımlayan bir anahtar. Açıklamalar Ayrıntılar için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu hizmet ve sorunu yönergeleri durdurma gibi durumunu almak veya duraklatmak için Hizmet Denetim Yöneticisi (SCM) çağıran koddur. SCM, için aşağıda bir işlem kodu geçirir `Handler` hizmet ne yapması gerektiğini belirtmek için.  
  
|İşlem kodu|Açıklama|  
|--------------------|-------------|  
|SERVICE_CONTROL_STOP|Hizmetini durdurur. Yöntemini geçersiz kılın [CAtlServiceModuleT::OnStop](#onstop) davranışını değiştirmek için atlbase.h içinde.|  
|SERVICE_CONTROL_PAUSE|Kullanıcı uygulanmadı. Empty yöntemi geçersiz kılma [CAtlServiceModuleT::OnPause](#onpause) Hizmeti duraklatmak için atlbase.h içinde.|  
|SERVICE_CONTROL_CONTINUE|Kullanıcı uygulanmadı. Empty yöntemi geçersiz kılma [CAtlServiceModuleT::OnContinue](#oncontinue) hizmeti sürdürmek için atlbase.h içinde.|  
|SERVICE_CONTROL_INTERROGATE|Kullanıcı uygulanmadı. Empty yöntemi geçersiz kılma [CAtlServiceModuleT::OnInterrogate](#oninterrogate) sorgulama hizmeti atlbase.h içinde.|  
|SERVICE_CONTROL_SHUTDOWN|Kullanıcı uygulanmadı. Empty yöntemi geçersiz kılma [CAtlServiceModuleT::OnShutdown](#onshutdown) kapatma hizmeti atlbase.h içinde.|  
  
 İşlem kodu tanınmıyor, yöntem [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) olarak adlandırılır.  
  
 ATL oluşturulan varsayılan hizmet durdurma yönerge yalnızca işler. SCM Dur yönerge geçerse, hizmet SCM program durmak olduğunu söyler. Hizmeti daha sonra çağırır `PostThreadMessage` kendisine çıkma iletisi göndermek için. Bu ileti döngüsü sona erer ve hizmet sonuçta kapatılacak.  
  
##  <a name="initializesecurity"></a>CAtlServiceModuleT::InitializeSecurity  
 Varsayılan hizmet için güvenlik ayarları sağlar.  
  
```
HRESULT InitializeSecurity() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Visual Studio .NET 2003'te, bu yöntem taban sınıf içinde uygulanmadı. Visual Studio Proje Sihirbazı'nı bu yöntem oluşturulan kodda içerir, ancak ATL 7.1 kullanarak Visual C++'ın önceki bir sürümde oluşturulmuş bir projeyi derlenmiş ise bir derleme hatası ortaya çıkar. Türetilen herhangi bir sınıf `CAtlServiceModuleT` türetilen sınıfta bu yöntemin uygulamalıdır.  
  
 Çağrısında PKT düzeyi kimlik doğrulama, kimliğe bürünme düzeyi RPC_C_IMP_LEVEL_IDENTIFY ve uygun null olmayan güvenlik tanımlayıcısı kullanmak **CoInitializeSecurity**.  
  
 Sihirbaz tarafından oluşturulan nonattributed hizmeti projeleri için bu içinde olacaktır  
  
 [!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]  
  
 Öznitelikli hizmeti projeleri için bu içinde olacaktır  
  
 [!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]  
  
##  <a name="install"></a>CAtlServiceModuleT::Install  
 Yükler ve hizmet oluşturur.  
  
```
BOOL Install() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Hizmeti Hizmet Denetim Yöneticisi (SCM) veritabanına yükler ve ardından hizmet nesnesi oluşturur. Hizmet oluşturulamadı, bir ileti kutusu görüntülenir ve yöntemi FALSE değerini döndürür.  
  
##  <a name="isinstalled"></a>CAtlServiceModuleT::IsInstalled  
 Hizmeti yüklü olduğunu doğrular.  
  
```
BOOL IsInstalled() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hizmeti yüklü, FALSE değilse TRUE döndürür.  
  
##  <a name="logevent"></a>CAtlServiceModuleT::LogEvent  
 Olay günlüğüne yazar.  
  
```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszFormat`  
 Olay günlüğüne yazma dize.  
  
 ...  
 Olay günlüğüne yazılması için isteğe bağlı ek dizeleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ayrıntıları bir olay işlevini kullanarak günlüğüne yazan [ReportEvent](http://msdn.microsoft.com/library/windows/desktop/aa363679). Hizmet çalışıyorsa, dize konsola gönderilir.  
  
##  <a name="m_bservice"></a>CAtlServiceModuleT::m_bService  
 Program hizmet olarak çalışan belirten bayrak.  
  
```
BOOL m_bService;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir uygulama exe dosyasını hizmet EXE ayırt etmek için kullanılır.  
  
##  <a name="m_dwthreadid"></a>CAtlServiceModuleT::m_dwThreadID  
 Üye değişkeni hizmet iş parçacığı tanıtıcısı depolama.  
  
```
DWORD m_dwThreadID;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değişkeni, geçerli iş parçacığının iş parçacığı kimliğini depolar.  
  
##  <a name="m_hservicestatus"></a>CAtlServiceModuleT::m_hServiceStatus  
 Üye değişkeni için geçerli hizmet durumu bilgileri yapısı için bir tanıtıcı depolama.  
  
```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```  
  
### <a name="remarks"></a>Açıklamalar  
 [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) yapısı bir hizmeti hakkında bilgiler içerir.  
  
##  <a name="m_status"></a>CAtlServiceModuleT::m_status  
 Üye değişkeni için geçerli hizmet durumu bilgileri yapısı depolama.  
  
```
SERVICE_STATUS m_status;
```  
  
### <a name="remarks"></a>Açıklamalar  
 [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) yapısı bir hizmeti hakkında bilgiler içerir.  
  
##  <a name="m_szservicename"></a>CAtlServiceModuleT::m_szServiceName  
 Kayıtlı hizmet adı.  
  
```
TCHAR [256] m_szServiceName;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hizmetin adını depolayan bir null ile sonlandırılmış dize.  
  
##  <a name="oncontinue"></a>CAtlServiceModuleT::OnContinue  
 Hizmeti sürdürmek için bu yöntemi geçersiz kılın.  
  
```
void OnContinue() throw();
```  
  
##  <a name="oninterrogate"></a>CAtlServiceModuleT::OnInterrogate  
 Sorgulama hizmeti için bu yöntemi geçersiz kılın.  
  
```
void OnInterrogate() throw();
```  
  
##  <a name="onpause"></a>CAtlServiceModuleT::OnPause  
 Hizmeti duraklatmak için bu yöntemi geçersiz kılın.  
  
```
void OnPause() throw();
```  
  
##  <a name="onshutdown"></a>CAtlServiceModuleT::OnShutdown  
 Hizmeti kapatmak için bu yöntemi geçersiz kılın.  
  
```
void OnShutdown() throw();
```  
  
##  <a name="onstop"></a>CAtlServiceModuleT::OnStop  
 Hizmeti durdurmak için bu yöntemi geçersiz kılın.  
  
```
void OnStop() throw();
```  
  
##  <a name="onunknownrequest"></a>CAtlServiceModuleT::OnUnknownRequest  
 Hizmet bilinmeyen isteklerini işlemek için bu yöntemi geçersiz kılın.  
  
```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 */\*dwOpcode\*/*  
 Ayrılmış.  
  
##  <a name="parsecommandline"></a>CAtlServiceModuleT::ParseCommandLine  
 Komut satırını ayrıştırır ve gerekiyorsa, kayıt işlemini gerçekleştirir.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpCmdLine`  
 Komut satırı.  
  
 `pnRetCode`  
 (Yer gerçekleştirirse) kayda karşılık gelen HRESULT.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı veya komut satırında sağlanan RGS dosyası kaydedilememiş yanlış true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Komut satırını ayrıştırır ve kaydeder veya sağlanan RGS dosya gerekirse kaydını siler. Bu yöntemi çağırır [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) denetlemek için **/regserver** ve **/Unregserver**. Bağımsız değişkeni ekleme **- / Service** hizmet kaydeder.  
  
##  <a name="premessageloop"></a>CAtlServiceModuleT::PreMessageLoop  
 Bu yöntem, ileti döngüsü hemen girmeden önce çağrılır.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nShowCmd`  
 Bu parametre için geçirilen [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hizmet için özel başlatma kodu eklemek için bu yöntemi geçersiz kılın.  
  
##  <a name="registerappid"></a>CAtlServiceModuleT::RegisterAppId  
 Hizmet kayıt defterinde kaydeder.  
  
```
inline HRESULT RegisterAppId(bool bService = false) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *bService*  
 Bir hizmet olarak kaydetmek için doğru olması gerekir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="run"></a>CAtlServiceModuleT::Run  
 Hizmet çalışır.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nShowCmd`  
 Nasıl penceresi gösterilecek belirtir. Bu parametre ele değerlerden biri olabilir [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) bölümü. SW_HIDE varsayılan değerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrılan sonra **çalıştırmak** çağrıları [CAtlServiceModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), ve [CAtlExeModuleT:: PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).  
  
##  <a name="servicemain"></a>CAtlServiceModuleT::ServiceMain  
 Bu yöntem, hizmet denetimi yöneticisi tarafından çağrılır.  
  
```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *dwArgc*  
 Argc bağımsız değişkeni.  
  
 *lpszArgv*  
 Argv bağımsız değişkeni.  
  
### <a name="remarks"></a>Açıklamalar  
 Hizmet Denetimi Yöneticisi (SCM) çağrıları `ServiceMain` Denetim Masası'ndaki Hizmetler uygulamasını açtığınızda, hizmeti seçin ve Başlat'ı tıklatın.  
  
 SCM sonra çağırır `ServiceMain`, bir hizmet SCM bir işleyici işlevi vermeniz gerekir. Bu işlev hizmetin durumunu elde edilir ve (örneğin, duraklatmak veya durduruluyor) yönelik özel yönergeler geçirmek SCM sağlar. Sonuç olarak, [CAtlServiceModuleT::Run](#run) ana iş hizmetinin gerçekleştirmek üzere çağırılır. **Çalıştırma** Hizmet durduruluncaya kadar yürütmeye devam eder.  
  
##  <a name="setservicestatus"></a>CAtlServiceModuleT::SetServiceStatus  
 Bu yöntem, hizmet durumunu güncelleştirir.  
  
```
void SetServiceStatus(DWORD dwState) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dwState`  
 Yeni durumu. Bkz: [artırılmış](http://msdn.microsoft.com/library/windows/desktop/ms686241) olası değerler için.  
  
### <a name="remarks"></a>Açıklamalar  
 Hizmeti için Hizmet Denetimi Yöneticisi'nin durum bilgilerini güncelleştirir. Çağrılır [CAtlServiceModuleT::Run](#run), [CAtlServiceModuleT::ServiceMain](#servicemain) ve diğer işleyici yöntemleri. Durum ayrıca üye değişkeninde depolanan [CAtlServiceModuleT::m_status](#m_status).  
  
##  <a name="start"></a>CAtlServiceModuleT::Start  
 Tarafından çağrılır `CAtlServiceModuleT::WinMain` zaman hizmetini başlatır.  
  
```
HRESULT Start(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nShowCmd`  
 Nasıl penceresi gösterilecek belirtir. Bu parametre ele değerlerden biri olabilir [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) bölümü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 [CAtlServiceModuleT::WinMain](#winmain) yöntemi kaydı ve yükleme işleme yanı sıra görevler kayıt defteri girdileri kaldırılıyor ve modül kaldırma dahil. Hizmet çalıştırdığınızda `WinMain` çağrıları **Başlat**.  
  
##  <a name="uninstall"></a>CAtlServiceModuleT::Uninstall  
 Durdurur ve hizmeti kaldırır.  
  
```
BOOL Uninstall() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışmasını hizmetini durdurur ve Hizmet Denetim Yöneticisi veritabanından kaldırır.  
  
##  <a name="unlock"></a>CAtlServiceModuleT::Unlock  
 Azaltır hizmetin kilit sayısı.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hata ayıklama ve tanılama için yararlı olabilir kilit sayımını döndürür.  
  
##  <a name="unregisterappid"></a>CAtlServiceModuleT::UnregisterAppId  
 Hizmet kayıt defterinden kaldırır.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="winmain"></a>CAtlServiceModuleT::WinMain  
 Bu yöntem hizmeti başlatmak için gereken kod uygular.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nShowCmd`  
 Nasıl penceresi gösterilecek belirtir. Bu parametre ele değerlerden biri olabilir [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) bölümü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hizmetin dönüş değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem komut satırı işler (ile [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)) ve ardından hizmet başlatır (kullanarak [CAtlServiceModuleT::Start](#start)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlExeModuleT sınıfı](../../atl/reference/catlexemodulet-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
