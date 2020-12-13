---
description: 'Daha fazla bilgi edinin: CAtlServiceModuleT sınıfı'
title: CAtlServiceModuleT sınıfı
ms.date: 05/06/2019
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
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
ms.openlocfilehash: 591d057437fb4386435a1f952170dfb8d6a71773
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147205"
---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT sınıfı

Bu sınıf bir hizmeti uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, UINT nServiceNameID>
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız öğesinden türetilir `CAtlServiceModuleT` .

*Nservicenameıd*<br/>
Hizmetin kaynak tanımlayıcısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlServiceModuleT:: Catlservicemodület](#catlservicemodulet)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlServiceModuleT:: Handler](#handler)|Hizmetin işleyici yordamı.|
|[CAtlServiceModuleT:: InitializeSecurity](#initializesecurity)|Hizmeti için varsayılan güvenlik ayarlarını sağlar.|
|[CAtlServiceModuleT:: Install](#install)|Hizmeti yükleyip oluşturur.|
|[CAtlServiceModuleT:: IsInstalled](#isinstalled)|Hizmetin yüklendiğini onaylar.|
|[CAtlServiceModuleT:: LogEvent](#logevent)|Olay günlüğüne yazar.|
|[CAtlServiceModuleT:: OnContinue](#oncontinue)|Hizmete devam etmek için bu yöntemi geçersiz kılın.|
|[CAtlServiceModuleT:: OnInterrogate](#oninterrogate)|Hizmeti sorgulanamıyor için bu yöntemi geçersiz kılın.|
|[CAtlServiceModuleT:: OnPause](#onpause)|Hizmeti duraklatmak için bu yöntemi geçersiz kılın.|
|[CAtlServiceModuleT:: Onkapatmalar](#onshutdown)|Hizmeti kapatmak için bu yöntemi geçersiz kılın|
|[CAtlServiceModuleT:: OnStop](#onstop)|Hizmeti durdurmak için bu yöntemi geçersiz kılın|
|[CAtlServiceModuleT:: OnUnknownRequest](#onunknownrequest)|Hizmete yönelik bilinmeyen istekleri işlemek için bu yöntemi geçersiz kılın|
|[CAtlServiceModuleT::P arseCommandLine](#parsecommandline)|Komut satırını ayrıştırır ve gerekirse kayıt gerçekleştirir.|
|[CAtlServiceModuleT::P reMessageLoop](#premessageloop)|Bu yöntem ileti döngüsüne girmeden hemen önce çağrılır.|
|[CAtlServiceModuleT:: Registerappıd](#registerappid)|Hizmeti kayıt defterine kaydeder.|
|[CAtlServiceModuleT:: Run](#run)|Hizmeti çalıştırır.|
|[CAtlServiceModuleT:: ServiceMain](#servicemain)|Hizmet denetimi yöneticisi tarafından çağrılan yöntem.|
|[CAtlServiceModuleT:: SetServiceStatus](#setservicestatus)|Hizmet durumunu güncelleştirir.|
|[CAtlServiceModuleT:: Start](#start)|`CAtlServiceModuleT::WinMain`Hizmet başladığında çağırılır.|
|[CAtlServiceModuleT:: Uninstall](#uninstall)|Hizmeti durdurup kaldırır.|
|[CAtlServiceModuleT:: unlock](#unlock)|Hizmetin kilit sayısını azaltır.|
|[CAtlServiceModuleT:: Unregisterappıd](#unregisterappid)|Hizmeti kayıt defterinden kaldırır.|
|[CAtlServiceModuleT:: WinMain](#winmain)|Bu yöntem, hizmeti çalıştırmak için gereken kodu uygular.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlServiceModuleT:: m_bService](#m_bservice)|Programın hizmet olarak çalıştığını belirten bayrak.|
|[CAtlServiceModuleT:: m_dwThreadID](#m_dwthreadid)|İş parçacığı tanımlayıcısını depolayan üye değişkeni.|
|[CAtlServiceModuleT:: m_hServiceStatus](#m_hservicestatus)|Geçerli hizmet için bir tanıtıcıyı durum bilgisi yapısına depolayan üye değişkeni.|
|[CAtlServiceModuleT:: m_status](#m_status)|Geçerli hizmet için durum bilgisi yapısını depolayan üye değişkeni.|
|[CAtlServiceModuleT:: m_szServiceName](#m_szservicename)|Kaydolmakta olan hizmetin adı.|

## <a name="remarks"></a>Açıklamalar

`CAtlServiceModuleT`[Catlexemodüle Let](../../atl/reference/catlexemodulet-class.md)'ten TÜRETILMIŞ bir ATL hizmeti modülü uygular. `CAtlServiceModuleT` komut satırı işleme, yükleme, kaydetme ve kaldırma için yöntemler sağlar. Ek işlevsellik gerekliyse, bunlar ve diğer Yöntemler geçersiz kılınabilir.

Bu sınıf, ATL 'nin önceki sürümlerinde kullanılan eski [CComModule sınıfının](../../atl/reference/ccommodule-class.md) yerini alır. Daha fazla ayrıntı için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[Catlmodület](../../atl/reference/catlmodulet-class.md)

[Catlexemodüle Let](../../atl/reference/catlexemodulet-class.md)

`CAtlServiceModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="catlservicemoduletcatlservicemodulet"></a><a name="catlservicemodulet"></a> CAtlServiceModuleT:: Catlservicemodület

Oluşturucu.

```cpp
CAtlServiceModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

Veri üyelerini başlatır ve ilk hizmet durumunu ayarlar.

## <a name="catlservicemodulethandler"></a><a name="handler"></a> CAtlServiceModuleT:: Handler

Hizmetin işleyici yordamı.

```cpp
void Handler(DWORD dwOpcode) throw();
```

### <a name="parameters"></a>Parametreler

*dwOpcode*<br/>
İşleyici işlemini tanımlayan bir anahtar. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Bu, hizmet Denetim Yöneticisi 'nin (SCM) hizmet durumunu almak ve Durdur veya Duraklat gibi yönergeler vermek için çağırdığı koddur. SCM, `Handler` hizmetin ne yapması gerektiğini göstermek için, aşağıda gösterildiği gibi bir işlem kodu geçirir.

|İşlem kodu|Anlamı|
|--------------------|-------------|
|SERVICE_CONTROL_STOP|Hizmeti sonlandırır. Davranışı değiştirmek için atlbase. h içinde [CAtlServiceModuleT:: OnStop](#onstop) yöntemini geçersiz kılın.|
|SERVICE_CONTROL_PAUSE|Kullanıcı uygulandı. Hizmeti duraklatmak için atlbase. h içinde boş olan [CAtlServiceModuleT:: OnPause](#onpause) metodunu geçersiz kılın.|
|SERVICE_CONTROL_CONTINUE|Kullanıcı uygulandı. Service 'e devam etmek için atlbase. h içinde boş olan [CAtlServiceModuleT:: OnContinue](#oncontinue) metodunu geçersiz kılın.|
|SERVICE_CONTROL_INTERROGATE|Kullanıcı uygulandı. Atlbase. h içindeki boş ' [OnInterrogate](#oninterrogate) ' metodunu hizmeti sorgulanamıyor için geçersiz kılın.|
|SERVICE_CONTROL_SHUTDOWN|Kullanıcı uygulandı. Hizmeti kapatmaya yönelik atlbase. h 'de boş olan [CAtlServiceModuleT:: Onkapatılmasını](#onshutdown) metodunu geçersiz kılın.|

İşlem kodu tanınmazsa, [CAtlServiceModuleT:: OnUnknownRequest](#onunknownrequest) yöntemi çağırılır.

Varsayılan ATL tarafından oluşturulan bir hizmet yalnızca durdurma yönergesini işler. SCM durdurma yönergesini geçerse, hizmet SCM 'ye programın durmak üzere olduğunu söyler. Hizmet daha sonra `PostThreadMessage` bir çıkış iletisi göndermek için çağırır. Bu ileti döngüsünü sonlandırır ve hizmet sonunda kapatılacak.

## <a name="catlservicemoduletinitializesecurity"></a><a name="initializesecurity"></a> CAtlServiceModuleT:: InitializeSecurity

Hizmeti için varsayılan güvenlik ayarlarını sağlar.

```cpp
HRESULT InitializeSecurity() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Öğesinden türetilen herhangi bir sınıf `CAtlServiceModuleT` türetilmiş sınıfta bu yöntemi gerçekleştirmelidir.

Çağrısı içinde, PKT düzeyi kimlik doğrulaması, RPC_C_IMP_LEVEL_IDENTIFY kimliğe bürünme düzeyi ve uygun bir null olmayan güvenlik tanımlayıcısı kullanın `CoInitializeSecurity` .

Sihirbaz tarafından oluşturulan, öznitelik atanmış olmayan hizmet projeleri için

[!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]

Öznitelikli hizmet projeleri için bu durum

[!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]

## <a name="catlservicemoduletinstall"></a><a name="install"></a> CAtlServiceModuleT:: Install

Hizmeti yükleyip oluşturur.

```cpp
BOOL Install() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Hizmeti Hizmet Denetim Yöneticisi (SCM) veritabanına yükleyip ardından hizmet nesnesini oluşturur. Hizmet oluşturulanmadıysa bir ileti kutusu görüntülenir ve Yöntem FALSE döndürür.

## <a name="catlservicemoduletisinstalled"></a><a name="isinstalled"></a> CAtlServiceModuleT:: IsInstalled

Hizmetin yüklendiğini onaylar.

```cpp
BOOL IsInstalled() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Hizmet yüklenmişse TRUE, aksi takdirde FALSE döndürür.

## <a name="catlservicemoduletlogevent"></a><a name="logevent"></a> CAtlServiceModuleT:: LogEvent

Olay günlüğüne yazar.

```cpp
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Olay günlüğüne yazılacak dize.

*...*<br/>
Olay günlüğüne yazılacak isteğe bağlı ek dizeler.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ayrıntıları [ReportEvent](/windows/win32/api/winbase/nf-winbase-reporteventw)işlevini kullanarak bir olay günlüğüne yazar. Hiçbir hizmet çalışmıyorsa, dize konsola gönderilir.

## <a name="catlservicemoduletm_bservice"></a><a name="m_bservice"></a> CAtlServiceModuleT:: m_bService

Programın hizmet olarak çalıştığını belirten bayrak.

```cpp
BOOL m_bService;
```

### <a name="remarks"></a>Açıklamalar

Bir Service EXE 'yi bir uygulama EXE 'sinden ayırt etmek için kullanılır.

## <a name="catlservicemoduletm_dwthreadid"></a><a name="m_dwthreadid"></a> CAtlServiceModuleT:: m_dwThreadID

Hizmetin iş parçacığı tanımlayıcısını depolayan üye değişkeni.

```cpp
DWORD m_dwThreadID;
```

### <a name="remarks"></a>Açıklamalar

Bu değişken, geçerli iş parçacığının iş parçacığı tanımlayıcısını depolar.

## <a name="catlservicemoduletm_hservicestatus"></a><a name="m_hservicestatus"></a> CAtlServiceModuleT:: m_hServiceStatus

Geçerli hizmet için bir tanıtıcıyı durum bilgisi yapısına depolayan üye değişkeni.

```cpp
SERVICE_STATUS_HANDLE m_hServiceStatus;
```

### <a name="remarks"></a>Açıklamalar

[SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) yapısı bir hizmet hakkındaki bilgileri içerir.

## <a name="catlservicemoduletm_status"></a><a name="m_status"></a> CAtlServiceModuleT:: m_status

Geçerli hizmet için durum bilgisi yapısını depolayan üye değişkeni.

```cpp
SERVICE_STATUS m_status;
```

### <a name="remarks"></a>Açıklamalar

[SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) yapısı bir hizmet hakkındaki bilgileri içerir.

## <a name="catlservicemoduletm_szservicename"></a><a name="m_szservicename"></a> CAtlServiceModuleT:: m_szServiceName

Kaydolmakta olan hizmetin adı.

```cpp
TCHAR [256] m_szServiceName;
```

### <a name="remarks"></a>Açıklamalar

Hizmetin adını depolayan, null ile sonlandırılmış bir dize.

## <a name="catlservicemoduletoncontinue"></a><a name="oncontinue"></a> CAtlServiceModuleT:: OnContinue

Hizmete devam etmek için bu yöntemi geçersiz kılın.

```cpp
void OnContinue() throw();
```

## <a name="catlservicemoduletoninterrogate"></a><a name="oninterrogate"></a> CAtlServiceModuleT:: OnInterrogate

Hizmeti sorgulanamıyor için bu yöntemi geçersiz kılın.

```cpp
void OnInterrogate() throw();
```

## <a name="catlservicemoduletonpause"></a><a name="onpause"></a> CAtlServiceModuleT:: OnPause

Hizmeti duraklatmak için bu yöntemi geçersiz kılın.

```cpp
void OnPause() throw();
```

## <a name="catlservicemoduletonshutdown"></a><a name="onshutdown"></a> CAtlServiceModuleT:: Onkapatmalar

Hizmeti kapatmak için bu yöntemi geçersiz kılın.

```cpp
void OnShutdown() throw();
```

## <a name="catlservicemoduletonstop"></a><a name="onstop"></a> CAtlServiceModuleT:: OnStop

Hizmeti durdurmak için bu yöntemi geçersiz kılın.

```cpp
void OnStop() throw();
```

## <a name="catlservicemoduletonunknownrequest"></a><a name="onunknownrequest"></a> CAtlServiceModuleT:: OnUnknownRequest

Hizmete yönelik bilinmeyen istekleri işlemek için bu yöntemi geçersiz kılın.

```cpp
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```

### <a name="parameters"></a>Parametreler

*dwOpcode*<br/>
Ayrılmış.

## <a name="catlservicemoduletparsecommandline"></a><a name="parsecommandline"></a> CAtlServiceModuleT::P arseCommandLine

Komut satırını ayrıştırır ve gerekirse kayıt gerçekleştirir.

```cpp
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Parametreler

*lpCmdLine*<br/>
Komut satırı.

*Pnekcode*<br/>
Kayda karşılık gelen HRESULT (Eğer gerçekleştiyse).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda true, komut satırında sağlanan RGS dosyası kaydedilüyorsa false döndürür.

### <a name="remarks"></a>Açıklamalar

Komut satırını ayrıştırır ve gerekirse sağlanan RGS dosyasını kaydeder veya kaydını siler. Bu yöntem, **/regserver** ve **/Unregserver**'ı denetlemek Için [catlexemodület::P arsecommandline](../../atl/reference/catlexemodulet-class.md#parsecommandline) öğesini çağırır. **-/Service** bağımsız değişkeninin eklenmesi hizmeti kaydeder.

## <a name="catlservicemoduletpremessageloop"></a><a name="premessageloop"></a> CAtlServiceModuleT::P reMessageLoop

Bu yöntem ileti döngüsüne girmeden hemen önce çağrılır.

```cpp
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Bu parametre [CAtlExeModuleT::P reMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop)öğesine geçirilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Hizmet için özel başlatma kodu eklemek için bu yöntemi geçersiz kılın.

## <a name="catlservicemoduletregisterappid"></a><a name="registerappid"></a> CAtlServiceModuleT:: Registerappıd

Hizmeti kayıt defterine kaydeder.

```cpp
inline HRESULT RegisterAppId(bool bService = false) throw();
```

### <a name="parameters"></a>Parametreler

*bService*<br/>
Hizmet olarak kaydolmak için true olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catlservicemoduletrun"></a><a name="run"></a> CAtlServiceModuleT:: Run

Hizmeti çalıştırır.

```cpp
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl gösterileceğini belirtir. Bu parametre, [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) bölümünde ele alınan değerlerden biri olabilir. Varsayılan değer SW_HIDE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıldıktan sonra `Run` [CAtlServiceModuleT::P remessageloop](#premessageloop), [Catlexemodület:: RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop)ve [catlexemodulet::P ostmessageloop](../../atl/reference/catlexemodulet-class.md#postmessageloop)çağrılır.

## <a name="catlservicemoduletservicemain"></a><a name="servicemain"></a> CAtlServiceModuleT:: ServiceMain

Bu yöntem, hizmet denetimi yöneticisi tarafından çağrılır.

```cpp
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```

### <a name="parameters"></a>Parametreler

*dwArgc*<br/>
Argc bağımsız değişkeni.

*lpszArgv*<br/>
Argv bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Hizmet Denetim Yöneticisi (SCM), `ServiceMain` Denetim Masası 'Nda hizmetler uygulamasını açtığınızda çağırır, hizmeti seçin ve Başlat ' a tıklayın.

SCM çağrıldıktan sonra `ServiceMain` , bir HIZMETIN SCM 'ye bir işleyici işlevi vermesi gerekir. Bu işlev, SCM 'nin hizmetin durumunu almasına ve belirli yönergeleri geçirmeye (duraklatma veya durdurma gibi) olanak tanır. Daha sonra, bir hizmetin ana işini gerçekleştirmek için [CAtlServiceModuleT:: Run](#run) çağırılır. `Run` hizmet durduruluncaya kadar yürütülmeye devam eder.

## <a name="catlservicemoduletsetservicestatus"></a><a name="setservicestatus"></a> CAtlServiceModuleT:: SetServiceStatus

Bu yöntem, hizmet durumunu güncelleştirir.

```cpp
void SetServiceStatus(DWORD dwState) throw();
```

### <a name="parameters"></a>Parametreler

*dwState*<br/>
Yeni durum. Olası değerler için bkz. [SetServiceStatus](/windows/win32/api/winsvc/nf-winsvc-setservicestatus) .

### <a name="remarks"></a>Açıklamalar

Hizmeti için hizmet denetimi yöneticisinin durum bilgilerini güncelleştirir. [CAtlServiceModuleT:: Run](#run), [Catlservicemodület:: ServiceMain](#servicemain) ve diğer işleyici yöntemleri tarafından çağrılır. Durum ayrıca [CAtlServiceModuleT:: m_status](#m_status)üye değişkeninde da depolanır.

## <a name="catlservicemoduletstart"></a><a name="start"></a> CAtlServiceModuleT:: Start

`CAtlServiceModuleT::WinMain`Hizmet başladığında çağırılır.

```cpp
HRESULT Start(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl gösterileceğini belirtir. Bu parametre, [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) bölümünde ele alınan değerlerden biri olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlServiceModuleT:: WinMain](#winmain) yöntemi hem kayıt hem de yüklemeyi ve kayıt defteri girişlerini kaldırmaya ve modülün kaldırılmasına dahil olan görevleri işler. Hizmet çalıştırıldığında, `WinMain` çağırır `Start` .

## <a name="catlservicemoduletuninstall"></a><a name="uninstall"></a> CAtlServiceModuleT:: Uninstall

Hizmeti durdurup kaldırır.

```cpp
BOOL Uninstall() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Hizmetin çalışmasını sonlandırır ve hizmet denetimi Yöneticisi veritabanından kaldırır.

## <a name="catlservicemoduletunlock"></a><a name="unlock"></a> CAtlServiceModuleT:: unlock

Hizmetin kilit sayısını azaltır.

```cpp
LONG Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve hata ayıklama için yararlı olabilecek kilit sayısını döndürür.

## <a name="catlservicemoduletunregisterappid"></a><a name="unregisterappid"></a> CAtlServiceModuleT:: Unregisterappıd

Hizmeti kayıt defterinden kaldırır.

```cpp
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catlservicemoduletwinmain"></a><a name="winmain"></a> CAtlServiceModuleT:: WinMain

Bu yöntem, hizmeti başlatmak için gereken kodu uygular.

```cpp
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl gösterileceğini belirtir. Bu parametre, [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) bölümünde ele alınan değerlerden biri olabilir.

### <a name="return-value"></a>Dönüş Değeri

Hizmetin dönüş değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut satırını işler ( [CAtlServiceModuleT::P arseCommandLine](#parsecommandline)) ve ardından hizmeti başlatır ( [CAtlServiceModuleT:: Start](#start)kullanılarak).

## <a name="see-also"></a>Ayrıca bkz.

[CAtlExeModuleT sınıfı](../../atl/reference/catlexemodulet-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
