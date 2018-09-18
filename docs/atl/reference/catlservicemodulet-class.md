---
title: CAtlServiceModuleT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74d36c7b13be3653a0c17f763e37447d5541c5a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086466"
---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT sınıfı

Bu sınıf, bir hizmet uygular.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, UINT nServiceNameID>
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınıza türetilen `CAtlServiceModuleT`.

*nServiceNameID*<br/>
Hizmet kaynak tanımlayıcısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlServiceModuleT::Handler](#handler)|İşleyici rutinini hizmeti.|
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|Varsayılan hizmet için güvenlik ayarları sağlar.|
|[CAtlServiceModuleT::Install](#install)|Yükler ve hizmeti oluşturur.|
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|Hizmetinin yüklendiğini doğrular.|
|[CAtlServiceModuleT::LogEvent](#logevent)|Olay günlüğüne yazar.|
|[CAtlServiceModuleT::OnContinue](#oncontinue)|Hizmeti sürdürmek için bu yöntemi yok sayın.|
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|Hizmet aracıyı sorgulamak için bu yöntemi yok sayın.|
|[CAtlServiceModuleT::OnPause](#onpause)|Hizmeti duraklatmak için bu yöntemi yok sayın.|
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|Hizmeti kapatmak için bu yöntemi geçersiz kılın|
|[CAtlServiceModuleT::OnStop](#onstop)|Hizmeti durdurmak için bu yöntemi geçersiz kılın|
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|Bilinmeyen hizmet isteklerini işlemek için bu yöntemi geçersiz kılın|
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Komut satırı ayrıştırır ve gerekirse kayıt gerçekleştirir.|
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Bu yöntem, ileti döngüsü girmeden hemen önce çağrılır.|
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Hizmet kayıt defterinde kaydeder.|
|[CAtlServiceModuleT::Run](#run)|Hizmet çalışır.|
|[CAtlServiceModuleT::ServiceMain](#servicemain)|Hizmet Denetimi Yöneticisi tarafından çağrılan yöntemi.|
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Hizmet durumunu güncelleştirir.|
|[CAtlServiceModuleT::Start](#start)|Çağıran `CAtlServiceModuleT::WinMain` hizmet başladığında.|
|[CAtlServiceModuleT::Uninstall](#uninstall)|Durdurur ve hizmeti kaldırır.|
|[CAtlServiceModuleT::Unlock](#unlock)|Hizmetin kilit sayısını azaltır.|
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|Hizmet kayıt defterinden kaldırır.|
|[CAtlServiceModuleT::WinMain](#winmain)|Bu yöntem, hizmeti çalıştırmak için gerekli kodu uygular.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlServiceModuleT::m_bService](#m_bservice)|Program, hizmet olarak çalışıyor belirten bayrak.|
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|Üye değişkeni iş parçacığı tanıtıcısını depolama.|
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|Üye değişkeni depolamak için geçerli hizmet durumu bilgileri yapısına bir tanıtıcı.|
|[CAtlServiceModuleT::m_status](#m_status)|Üye değişkeni depolamak için geçerli hizmet durumu bilgileri yapısı.|
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|Kayıtlı hizmet adı.|

## <a name="remarks"></a>Açıklamalar

`CAtlServiceModuleT`, öğesinden türetilen [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), ATL hizmeti modülü uygular. `CAtlServiceModuleT` komut satırı işlemeyi, yükleme, kaydetme ve kaldırma için yöntemler sağlar. Ek işlevler gerekiyorsa, bunlar ve diğer yöntemleri geçersiz kılınabilir.

Bu sınıf artık kullanılmıyor değiştirir [CComModule sınıfı](../../atl/reference/ccommodule-class.md) ATL önceki sürümlerinde kullanılan Bkz: [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)

`CAtlServiceModuleT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="catlservicemodulet"></a>  CAtlServiceModuleT::CAtlServiceModuleT

Oluşturucu.

```
CAtlServiceModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

Veri üyeleri başlatır ve ilk hizmet durumunu ayarlar.

##  <a name="handler"></a>  CAtlServiceModuleT::Handler

İşleyici rutinini hizmeti.

```
void Handler(DWORD dwOpcode) throw();
```

### <a name="parameters"></a>Parametreler

*dwOpcode*<br/>
İşleyici işlemi tanımlayan anahtar. Ayrıntılar için konusundaki yorumlara bakın.

### <a name="remarks"></a>Açıklamalar

Hizmet Denetimi Yöneticisi (SCM) çağrılarını duraklatmak veya durdurma gibi hizmet ve sorunu yönergeleri durumunu almak için kod budur. İşlem için aşağıda gösterilen kodu SCM geçirir `Handler` hizmet ne yapması gerektiğini belirtmek için.

|İşlem kodu|Açıklama|
|--------------------|-------------|
|SERVICE_CONTROL_STOP|Hizmetini durdurur. Bu yöntemi yok sayın [CAtlServiceModuleT::OnStop](#onstop) davranışını değiştirmek için atlbase.h içinde.|
|SERVICE_CONTROL_PAUSE|Kullanıcı uygulanır. Boş yöntemi yok sayın [CAtlServiceModuleT::OnPause](#onpause) hizmeti duraklatma atlbase.h içinde.|
|SERVICE_CONTROL_CONTINUE|Kullanıcı uygulanır. Boş yöntemi yok sayın [CAtlServiceModuleT::OnContinue](#oncontinue) hizmeti sürdürmek için atlbase.h içinde.|
|SERVICE_CONTROL_INTERROGATE|Kullanıcı uygulanır. Boş yöntemi yok sayın [CAtlServiceModuleT::OnInterrogate](#oninterrogate) sorgulama hizmeti için atlbase.h içinde.|
|SERVICE_CONTROL_SHUTDOWN|Kullanıcı uygulanır. Boş yöntemi yok sayın [CAtlServiceModuleT::OnShutdown](#onshutdown) atlbase.h kapatma hizmeti içinde.|

İşlem kodu tanınmıyorsa yöntemi [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) çağrılır.

ATL tarafından oluşturulan varsayılan hizmet durdurma yönergesi yalnızca işler. SCM durdurma yönerge geçerse, service, SCM program durmak için olduğunu söyler. Sonra hizmeti çağırır `PostThreadMessage` kendisine bir çıkış iletisi göndermek için. Bu ileti döngüsü sonlanır ve hizmet sonuçta kapatın.

##  <a name="initializesecurity"></a>  CAtlServiceModuleT::InitializeSecurity

Varsayılan hizmet için güvenlik ayarları sağlar.

```
HRESULT InitializeSecurity() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Visual Studio .NET 2003'te, temel sınıfta bu yöntem uygulanmadı. Visual Studio projesi Sihirbazı bu yöntem oluşturulan kodda içerir, ancak Visual C++'ın önceki bir sürümde oluşturulmuş bir projeyi ATL 7.1 kullanılarak derlenmiş bir derleme hatası meydana gelir. Öğesinden türetilen herhangi bir sınıf `CAtlServiceModuleT` bu yöntem, türetilen sınıfta uygulamalıdır.

Çağrısında PKT düzeyi kimlik doğrulama, kimliğe bürünme düzeyi rpc_c_ımp_level_ıdentıfy'nın ve uygun null olmayan güvenlik tanımlayıcısı'nı kullanmak `CoInitializeSecurity`.

Sihirbazın ürettiği nonattributed hizmet projeleri için bu içinde olacaktır

[!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]

Öznitelikli hizmet projeleri için bu içinde olacaktır

[!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]

##  <a name="install"></a>  CAtlServiceModuleT::Install

Yükler ve hizmeti oluşturur.

```
BOOL Install() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Hizmeti Hizmet Denetim Yöneticisi (SCM) veritabanına yükler ve ardından hizmet nesnesi oluşturur. Hizmet oluşturulamadı, bir ileti kutusu görüntülenir ve yöntem FALSE döndürür.

##  <a name="isinstalled"></a>  CAtlServiceModuleT::IsInstalled

Hizmetinin yüklendiğini doğrular.

```
BOOL IsInstalled() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Hizmet yoksa yüklenen, FALSE ise TRUE döndürür.

##  <a name="logevent"></a>  CAtlServiceModuleT::LogEvent

Olay günlüğüne yazar.

```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Olay günlüğüne yazmak için dize.

*...*<br/>
Olay günlüğüne yazılması için isteğe bağlı ek dizeleri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ayrıntıları bir olay işlevi kullanarak günlüğüne yazıyor [ReportEvent](/windows/desktop/api/winbase/nf-winbase-reporteventa). Dize, hiçbir hizmet çalışıyorsa, konsola gönderilir.

##  <a name="m_bservice"></a>  CAtlServiceModuleT::m_bService

Program, hizmet olarak çalışıyor belirten bayrak.

```
BOOL m_bService;
```

### <a name="remarks"></a>Açıklamalar

Bir uygulama exe dosyasını hizmet EXE ayırt etmek için kullanılır.

##  <a name="m_dwthreadid"></a>  CAtlServiceModuleT::m_dwThreadID

Üye değişkeni depolama hizmetinin iş parçacığı tanımlayıcısı.

```
DWORD m_dwThreadID;
```

### <a name="remarks"></a>Açıklamalar

Bu değişken, geçerli iş parçacığının iş parçacığı kimliğini depolar.

##  <a name="m_hservicestatus"></a>  CAtlServiceModuleT::m_hServiceStatus

Üye değişkeni depolamak için geçerli hizmet durumu bilgileri yapısına bir tanıtıcı.

```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```

### <a name="remarks"></a>Açıklamalar

[SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) yapısı bir hizmeti hakkında bilgiler içerir.

##  <a name="m_status"></a>  CAtlServiceModuleT::m_status

Üye değişkeni depolamak için geçerli hizmet durumu bilgileri yapısı.

```
SERVICE_STATUS m_status;
```

### <a name="remarks"></a>Açıklamalar

[SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) yapısı bir hizmeti hakkında bilgiler içerir.

##  <a name="m_szservicename"></a>  CAtlServiceModuleT::m_szServiceName

Kayıtlı hizmet adı.

```
TCHAR [256] m_szServiceName;
```

### <a name="remarks"></a>Açıklamalar

Hizmetin adını depolayan bir null ile sonlandırılmış dize.

##  <a name="oncontinue"></a>  CAtlServiceModuleT::OnContinue

Hizmeti sürdürmek için bu yöntemi yok sayın.

```
void OnContinue() throw();
```

##  <a name="oninterrogate"></a>  CAtlServiceModuleT::OnInterrogate

Hizmet aracıyı sorgulamak için bu yöntemi yok sayın.

```
void OnInterrogate() throw();
```

##  <a name="onpause"></a>  CAtlServiceModuleT::OnPause

Hizmeti duraklatmak için bu yöntemi yok sayın.

```
void OnPause() throw();
```

##  <a name="onshutdown"></a>  CAtlServiceModuleT::OnShutdown

Hizmeti kapatmak için bu yöntemi yok sayın.

```
void OnShutdown() throw();
```

##  <a name="onstop"></a>  CAtlServiceModuleT::OnStop

Hizmeti durdurmak için bu yöntemi yok sayın.

```
void OnStop() throw();
```

##  <a name="onunknownrequest"></a>  CAtlServiceModuleT::OnUnknownRequest

Bilinmeyen hizmet isteklerini işlemek için bu yöntemi yok sayın.

```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```

### <a name="parameters"></a>Parametreler

*dwOpcode*<br/>
Ayrılmış.

##  <a name="parsecommandline"></a>  CAtlServiceModuleT::ParseCommandLine

Komut satırı ayrıştırır ve gerekirse kayıt gerçekleştirir.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Parametreler

*lpCmdLine*<br/>
Komut satırı.

*pnRetCode*<br/>
Kayıt için (bir yerde gerçekleştirirse) karşılık gelen HRESULT.

### <a name="return-value"></a>Dönüş Değeri

Başarı veya yanlış komut satırında sağlanan RGS dosyası kaydedilemedi true döndürür.

### <a name="remarks"></a>Açıklamalar

Komut satırı ayrıştırır ve kaydeder veya sağlanan RGS dosyası gerekirse kaydını siler. Bu yöntemin çağırdığı [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) denetlemek için **/regserver** ve **/Unregserver**. Bağımsız değişken ekleyerek **- / Service** hizmet kaydeder.

##  <a name="premessageloop"></a>  CAtlServiceModuleT::PreMessageLoop

Bu yöntem, ileti döngüsü girmeden hemen önce çağrılır.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Bu parametre için geçirilen [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Hizmet için özel başlatma kodu eklemek için bu yöntemi yok sayın.

##  <a name="registerappid"></a>  CAtlServiceModuleT::RegisterAppId

Hizmet kayıt defterinde kaydeder.

```
inline HRESULT RegisterAppId(bool bService = false) throw();
```

### <a name="parameters"></a>Parametreler

*bService*<br/>
Hizmet olarak kaydetmek için doğru olması gerekir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="run"></a>  CAtlServiceModuleT::Run

Hizmet çalışır.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl mı belirtir. Bu parametre ele değerlerden biri olabilir [WinMain](https://msdn.microsoft.com/library/windows/desktop/ms633559) bölümü. SW_HIDE varsayılan değerdir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrılan sonra `Run` çağrıları [CAtlServiceModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), ve [CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).

##  <a name="servicemain"></a>  CAtlServiceModuleT::ServiceMain

Bu yöntem, hizmet denetimi yöneticisi tarafından çağrılır.

```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```

### <a name="parameters"></a>Parametreler

*dwArgc*<br/>
Argc bağımsız değişkeni.

*lpszArgv*<br/>
Argv bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Hizmet Denetimi Yöneticisi (SCM) çağrıları `ServiceMain` Denetim Masası'ndaki Hizmetler uygulamasını açtığınızda, hizmeti seçin ve Başlat'a tıklayın.

SCM sonra çağıran `ServiceMain`, hizmet bir işleyici işlevi SCM vermeniz gerekir. Bu işlev, hizmetin durum elde edilir ve özel yönergeler (örneğin, duraklatmak veya durdurma) geçirmeniz SCM sağlar. Sonuç olarak, [CAtlServiceModuleT::Run](#run) hizmet ana iş gerçekleştirmek üzere çağırılır. `Run` Hizmet durduruluncaya kadar yürütmeye devam eder.

##  <a name="setservicestatus"></a>  CAtlServiceModuleT::SetServiceStatus

Bu yöntem, hizmet durumunu güncelleştirir.

```
void SetServiceStatus(DWORD dwState) throw();
```

### <a name="parameters"></a>Parametreler

*dwState*<br/>
Yeni durum. Bkz: [artırılmış](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) için olası değerler.

### <a name="remarks"></a>Açıklamalar

Hizmeti için Hizmet Denetimi Yöneticisi'nin durum bilgilerini güncelleştirir. Tarafından çağrılır [CAtlServiceModuleT::Run](#run), [CAtlServiceModuleT::ServiceMain](#servicemain) ve diğer işleyici yöntemleri. Durum da üye değişkeni depolanan [CAtlServiceModuleT::m_status](#m_status).

##  <a name="start"></a>  CAtlServiceModuleT::Start

Çağıran `CAtlServiceModuleT::WinMain` hizmet başladığında.

```
HRESULT Start(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl mı belirtir. Bu parametre ele değerlerden biri olabilir [WinMain](https://msdn.microsoft.com/library/windows/desktop/ms633559) bölümü.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlServiceModuleT::WinMain](#winmain) yöntemi kayıt hem yükleme işler yanı sıra görevler kayıt defteri girdileri kaldırılıyor ve modül kaldırma dahil. Hizmet çalıştırıldığında `WinMain` çağrıları `Start`.

##  <a name="uninstall"></a>  CAtlServiceModuleT::Uninstall

Durdurur ve hizmeti kaldırır.

```
BOOL Uninstall() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Çalışmasını hizmetini durdurur ve Hizmet Denetim Yöneticisi veritabanından kaldırır.

##  <a name="unlock"></a>  CAtlServiceModuleT::Unlock

Hizmetin kilit sayısını azaltır.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı ve hata ayıklama olabilir kilit sayacını döndürür.

##  <a name="unregisterappid"></a>  CAtlServiceModuleT::UnregisterAppId

Hizmet kayıt defterinden kaldırır.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="winmain"></a>  CAtlServiceModuleT::WinMain

Hizmeti başlatmak için gerekli kodu bu yöntemi uygular.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl mı belirtir. Bu parametre ele değerlerden biri olabilir [WinMain](https://msdn.microsoft.com/library/windows/desktop/ms633559) bölümü.

### <a name="return-value"></a>Dönüş Değeri

Hizmetin dönüş değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut satırında işler (ile [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)) ve ardından hizmeti başlatır (kullanarak [CAtlServiceModuleT::Start](#start)).

## <a name="see-also"></a>Ayrıca Bkz.

[CAtlExeModuleT Sınıfı](../../atl/reference/catlexemodulet-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
