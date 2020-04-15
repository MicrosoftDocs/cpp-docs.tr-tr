---
title: CAtlServiceModuleT Sınıfı
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
ms.openlocfilehash: 5d87eada997d0bbfe44cd07a819f6b012a7a3a20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321334"
---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT Sınıfı

Bu sınıf bir hizmet uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, UINT nServiceNameID>
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `CAtlServiceModuleT`türetilmiştir.

*nServiceNameID*<br/>
Hizmetin kaynak tanımlayıcısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlServiceModuleT::İşleyici](#handler)|Hizmet için işleyici yordamı.|
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|Hizmet için varsayılan güvenlik ayarlarını sağlar.|
|[CAtlServiceModuleT::Yükle](#install)|Hizmeti yükler ve oluşturur.|
|[CAtlServiceModuleT::Yüklendi](#isinstalled)|Hizmetin yüklendiğini doğrular.|
|[CAtlServiceModuleT::LogEvent](#logevent)|Olay günlüğüne yazar.|
|[CAtlServiceModuleT::OnContinue](#oncontinue)|Hizmete devam etmek için bu yöntemi geçersiz kılın.|
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|Hizmeti sorgulamak için bu yöntemi geçersiz kılın.|
|[CAtlServiceModuleT::OnPause](#onpause)|Hizmeti duraklatmak için bu yöntemi geçersiz kılın.|
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|Hizmeti kapatmak için bu yöntemi geçersiz kılma|
|[CAtlServiceModuleT::OnStop](#onstop)|Hizmeti durdurmak için bu yöntemi geçersiz kılma|
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|Hizmete bilinmeyen istekleri işlemek için bu yöntemi geçersiz kılma|
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Komut satırını parses ve gerekirse kayıt gerçekleştirir.|
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Bu yöntem, ileti döngüsüne girmeden hemen önce çağrılır.|
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Hizmeti kayıt defterine kaydeder.|
|[CAtlServiceModuleT::Çalıştır](#run)|Hizmeti yürüyor.|
|[CAtlServiceModuleT::ServiceMain](#servicemain)|Servis Denetim Yöneticisi tarafından çağrılan yöntem.|
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Hizmet durumunu güncelleştirir.|
|[CAtlServiceModuleT::Başlat](#start)|Hizmet `CAtlServiceModuleT::WinMain` başladığında çağrılır.|
|[CAtlServiceModuleT::Kaldır](#uninstall)|Hizmeti durdurur ve kaldırır.|
|[CAtlServiceModuleT::Kilidini aç](#unlock)|Hizmetin kilit sayısını verir.|
|[CAtlServiceModuleT::Kayıt DışıAppId](#unregisterappid)|Hizmeti kayıt defterinden kaldırır.|
|[CAtlServiceModuleT::WinMain](#winmain)|Bu yöntem, hizmeti çalıştırmak için gereken kodu uygular.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAtlServiceModuleT::m_bService](#m_bservice)|Programın bir hizmet olarak çalıştığını belirten bayrak.|
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|İş parçacığı tanımlayıcısını depolayan üye değişken.|
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|Üye değişkeni, geçerli hizmetin durum bilgi yapısına bir tutamacı depolar.|
|[CAtlServiceModuleT::m_status](#m_status)|Geçerli hizmetin durum bilgi yapısını depolayan üye değişkeni.|
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|Kayıtlı olan hizmetin adı.|

## <a name="remarks"></a>Açıklamalar

`CAtlServiceModuleT`, [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)türetilmiştir, bir ATL Service modülü uygular. `CAtlServiceModuleT`komut satırı işleme, yükleme, kaydetme ve kaldırma yöntemleri sağlar. İlave işlevsellik gerekiyorsa, bu ve diğer yöntemler geçersiz kılınabilir.

Bu sınıf, ATL'nin önceki sürümlerinde kullanılan eski [CComModule Sınıfının](../../atl/reference/ccommodule-class.md) yerini alır. Daha fazla bilgi için [ATL Modül Sınıfları'na](../../atl/atl-module-classes.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModülü](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[Catlexemodulet](../../atl/reference/catlexemodulet-class.md)

`CAtlServiceModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="catlservicemoduletcatlservicemodulet"></a><a name="catlservicemodulet"></a>CAtlServiceModuleT::CAtlServiceModuleT

Oluşturucu.

```
CAtlServiceModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

Veri üyelerini başolarak karşılar ve ilk hizmet durumunu ayarlar.

## <a name="catlservicemodulethandler"></a><a name="handler"></a>CAtlServiceModuleT::İşleyici

Hizmet için işleyici yordamı.

```
void Handler(DWORD dwOpcode) throw();
```

### <a name="parameters"></a>Parametreler

*dwOpcode*<br/>
İşleyici çalışmasını tanımlayan bir anahtar. Ayrıntılar için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

Bu, Hizmet Denetim Yöneticisi'nin (SCM) hizmetin durumunu almak ve durdurma veya duraklatma gibi yönergeler vermek için çağırdığı koddur. SCM, hizmetin ne yapması gerektiğini `Handler` belirtmek için aşağıda gösterilen bir işlem kodunu geçirir.

|İşlem kodu|Anlamı|
|--------------------|-------------|
|SERVICE_CONTROL_STOP|Hizmeti durdurur. Davranışı değiştirmek için [CAtlServiceModuleT::OnStop](#onstop) in atlbase.h yöntemini geçersiz kılın.|
|SERVICE_CONTROL_PAUSE|Kullanıcı uygulandı. Hizmeti duraklatmak için boş [cAtlServiceModuleT::OnPause](#onpause) in atlbase.h'yi geçersiz kılın.|
|SERVICE_CONTROL_CONTINUE|Kullanıcı uygulandı. Boş yöntem [CAtlServiceModuleT geçersiz kılın::OnHizmete](#oncontinue) devam etmek için atlbase.h'de devam edin.|
|SERVICE_CONTROL_INTERROGATE|Kullanıcı uygulandı. Hizmeti sorgulamak için boş yöntem [CAtlServiceModuleT::OnInterrogate](#oninterrogate) in atlbase.h'yi geçersiz kılın.|
|SERVICE_CONTROL_SHUTDOWN|Kullanıcı uygulandı. Hizmeti kapatmak için boş [cAtlServiceModuleT::OnShutdown](#onshutdown) in atlbase.h'de boş bir yöntem geçersiz kılın.|

İşlem kodu tanınmıyorsa, [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) adlı yöntem ekidir.

Varsayılan ATL tarafından oluşturulan bir hizmet yalnızca durdurma yönergesini işler. SCM durdurma yönergesini geçerse, hizmet SCM'ye programın durdurmak üzere olduğunu bildirir. Hizmet daha `PostThreadMessage` sonra kendisine bir çıkış iletisi göndermek için çağırır. Bu ileti döngüsü sona erer ve hizmet sonunda kapanır.

## <a name="catlservicemoduletinitializesecurity"></a><a name="initializesecurity"></a>CAtlServiceModuleT::InitializeSecurity

Hizmet için varsayılan güvenlik ayarlarını sağlar.

```
HRESULT InitializeSecurity() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Türemiş sınıftan `CAtlServiceModuleT` türeyen herhangi bir sınıf bu yöntemi uygulamalıdır.

PKT düzeyinde kimlik doğrulamasını, RPC_C_IMP_LEVEL_IDENTIFY kimliğe bürünme düzeyini ve çağrıda uygun `CoInitializeSecurity`bir null olmayan güvenlik tanımlayıcısını kullanın.

Sihirbaz tarafından oluşturulan atfedilen olmayan hizmet projeleri için, bu

[!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]

Atfedilen hizmet projeleri için, bu

[!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]

## <a name="catlservicemoduletinstall"></a><a name="install"></a>CAtlServiceModuleT::Yükle

Hizmeti yükler ve oluşturur.

```
BOOL Install() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Hizmeti Hizmet Denetim Yöneticisi (SCM) veritabanına yükler ve ardından hizmet nesnesini oluşturur. Hizmet oluşturulamadıysa, bir ileti kutusu görüntülenir ve yöntem FALSE döndürür.

## <a name="catlservicemoduletisinstalled"></a><a name="isinstalled"></a>CAtlServiceModuleT::Yüklendi

Hizmetin yüklendiğini doğrular.

```
BOOL IsInstalled() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Hizmet yüklüyse TRUE döndürür, aksi takdirde FALSE.

## <a name="catlservicemoduletlogevent"></a><a name="logevent"></a>CAtlServiceModuleT::LogEvent

Olay günlüğüne yazar.

```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Olay günlüğüne yazılması gereken dize.

*...*<br/>
Olay günlüğüne yazılması isteğe bağlı ekstra dizeleri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [ReportEvent](/windows/win32/api/winbase/nf-winbase-reporteventw)işlevini kullanarak ayrıntıları bir olay günlüğüne yazar. Hizmet yoksa, dize konsola gönderilir.

## <a name="catlservicemoduletm_bservice"></a><a name="m_bservice"></a>CAtlServiceModuleT::m_bService

Programın bir hizmet olarak çalıştığını belirten bayrak.

```
BOOL m_bService;
```

### <a name="remarks"></a>Açıklamalar

Service EXE'yi Application EXE'den ayırmak için kullanılır.

## <a name="catlservicemoduletm_dwthreadid"></a><a name="m_dwthreadid"></a>CAtlServiceModuleT::m_dwThreadID

Hizmetin iş parçacığı tanımlayıcısını depolayan üye değişken.

```
DWORD m_dwThreadID;
```

### <a name="remarks"></a>Açıklamalar

Bu değişken, geçerli iş parçacığının iş parçacığı tanımlayıcısını depolar.

## <a name="catlservicemoduletm_hservicestatus"></a><a name="m_hservicestatus"></a>CAtlServiceModuleT::m_hServiceStatus

Üye değişkeni, geçerli hizmetin durum bilgi yapısına bir tutamacı depolar.

```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```

### <a name="remarks"></a>Açıklamalar

[SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) yapısı bir hizmet hakkında bilgi içerir.

## <a name="catlservicemoduletm_status"></a><a name="m_status"></a>CAtlServiceModuleT::m_status

Geçerli hizmetin durum bilgi yapısını depolayan üye değişkeni.

```
SERVICE_STATUS m_status;
```

### <a name="remarks"></a>Açıklamalar

[SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) yapısı bir hizmet hakkında bilgi içerir.

## <a name="catlservicemoduletm_szservicename"></a><a name="m_szservicename"></a>CAtlServiceModuleT::m_szServiceName

Kayıtlı olan hizmetin adı.

```
TCHAR [256] m_szServiceName;
```

### <a name="remarks"></a>Açıklamalar

Hizmetin adını depolayan null-sonlandırılan dize.

## <a name="catlservicemoduletoncontinue"></a><a name="oncontinue"></a>CAtlServiceModuleT::OnContinue

Hizmete devam etmek için bu yöntemi geçersiz kılın.

```
void OnContinue() throw();
```

## <a name="catlservicemoduletoninterrogate"></a><a name="oninterrogate"></a>CAtlServiceModuleT::OnInterrogate

Hizmeti sorgulamak için bu yöntemi geçersiz kılın.

```
void OnInterrogate() throw();
```

## <a name="catlservicemoduletonpause"></a><a name="onpause"></a>CAtlServiceModuleT::OnPause

Hizmeti duraklatmak için bu yöntemi geçersiz kılın.

```
void OnPause() throw();
```

## <a name="catlservicemoduletonshutdown"></a><a name="onshutdown"></a>CAtlServiceModuleT::OnShutdown

Hizmeti kapatmak için bu yöntemi geçersiz kılın.

```
void OnShutdown() throw();
```

## <a name="catlservicemoduletonstop"></a><a name="onstop"></a>CAtlServiceModuleT::OnStop

Hizmeti durdurmak için bu yöntemi geçersiz kılın.

```
void OnStop() throw();
```

## <a name="catlservicemoduletonunknownrequest"></a><a name="onunknownrequest"></a>CAtlServiceModuleT::OnUnknownRequest

Hizmete bilinmeyen istekleri işlemek için bu yöntemi geçersiz kılın.

```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```

### <a name="parameters"></a>Parametreler

*dwOpcode*<br/>
Ayrılmış.

## <a name="catlservicemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlServiceModuleT::ParseCommandLine

Komut satırını parses ve gerekirse kayıt gerçekleştirir.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Parametreler

*lpCmdLine*<br/>
Komut satırı.

*pnRetCode*<br/>
Kayıt için karşılık gelen HRESULT (gerçekleştiyse).

### <a name="return-value"></a>Dönüş Değeri

Komut satırında verilen RGS dosyası kaydedilemediyse, başarı üzerinde doğru veya yanlış olarak döndürür.

### <a name="remarks"></a>Açıklamalar

Komut satırını parses ve kaydeder veya gerekirse verilen RGS dosyası unregisters. Bu yöntem [CAtlExeModuleT çağırır::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) / **RegServer** ve **/ UnregServer**kontrol etmek. Bağımsız değişken **-/Service** ekleme hizmeti kaydeder.

## <a name="catlservicemoduletpremessageloop"></a><a name="premessageloop"></a>CAtlServiceModuleT::PreMessageLoop

Bu yöntem, ileti döngüsüne girmeden hemen önce çağrılır.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Bu parametre [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop)geçirilir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Hizmet için özel başlatma kodu eklemek için bu yöntemi geçersiz kılın.

## <a name="catlservicemoduletregisterappid"></a><a name="registerappid"></a>CAtlServiceModuleT::RegisterAppId

Hizmeti kayıt defterine kaydeder.

```
inline HRESULT RegisterAppId(bool bService = false) throw();
```

### <a name="parameters"></a>Parametreler

*bService*<br/>
Bir hizmet olarak kayıt için doğru olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catlservicemoduletrun"></a><a name="run"></a>CAtlServiceModuleT::Çalıştır

Hizmeti yürüyor.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl gösterilebildiğini belirtir. Bu parametre [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) bölümünde tartışılan değerlerden biri olabilir. Varsayılan değer SW_HIDE.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

`Run` Çağrıldıktan sonra, [catlServiceModuleT::PreMessageLoop,](#premessageloop) [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop)ve [CAtlExeModuleT::PostMessageLoop.](../../atl/reference/catlexemodulet-class.md#postmessageloop)

## <a name="catlservicemoduletservicemain"></a><a name="servicemain"></a>CAtlServiceModuleT::ServiceMain

Bu yöntem Servis Denetim Yöneticisi tarafından çağrılır.

```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```

### <a name="parameters"></a>Parametreler

*dwArgc*<br/>
Argc argümanı.

*lpszArgv*<br/>
Argv argümanı.

### <a name="remarks"></a>Açıklamalar

Hizmet Denetim Yöneticisi (SCM), Denetim Masası'ndaki Hizmetler uygulamasını açtığınızda, hizmeti seçtiğinizde ve Başlat'ı tıklattığınızda çağırır. `ServiceMain`

SCM aramalarından `ServiceMain`sonra, bir hizmetin SCM işleyicisi işlevi vermesi gerekir. Bu işlev, SCM'nin hizmetin durumunu almasına ve belirli yönergeleri (duraklama veya durdurma gibi) geçirmesine olanak tanır. Daha sonra, [CAtlServiceModuleT::Run,](#run) hizmetin ana çalışmasını gerçekleştirmek için çağrılır. `Run`hizmet durdurulana kadar yürütmeye devam edilir.

## <a name="catlservicemoduletsetservicestatus"></a><a name="setservicestatus"></a>CAtlServiceModuleT::SetServiceStatus

Bu yöntem hizmet durumunu güncelleştirir.

```
void SetServiceStatus(DWORD dwState) throw();
```

### <a name="parameters"></a>Parametreler

*dwState*<br/>
Yeni durum. Olası değerler için [SetServiceStatus'e](/windows/win32/api/winsvc/nf-winsvc-setservicestatus) bakın.

### <a name="remarks"></a>Açıklamalar

Hizmet Denetim Yöneticisi'nin hizmet in durum bilgilerini güncelleştirir. [CAtlServiceModuleT::Çalıştır,](#run) [CAtlServiceModuleT::ServiceMain](#servicemain) ve diğer işleyici yöntemleri ile adlandırılır. Durum aynı zamanda üye değişken [CAtlServiceModuleT de saklanır::m_status](#m_status).

## <a name="catlservicemoduletstart"></a><a name="start"></a>CAtlServiceModuleT::Başlat

Hizmet `CAtlServiceModuleT::WinMain` başladığında çağrılır.

```
HRESULT Start(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl gösterilebildiğini belirtir. Bu parametre [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) bölümünde tartışılan değerlerden biri olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[CAtlServiceModuleT::WinMain](#winmain) yöntemi hem kayıt hem de yüklemenin yanı sıra kayıt defteri girişlerini kaldırma ve modülü kaldırma yla ilgili görevleri de işler. Hizmet çalıştırıldığında, `WinMain` çağırır. `Start`

## <a name="catlservicemoduletuninstall"></a><a name="uninstall"></a>CAtlServiceModuleT::Kaldır

Hizmeti durdurur ve kaldırır.

```
BOOL Uninstall() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Hizmetin çalışmasını durdurur ve Servis Denetim Yöneticisi veritabanından kaldırır.

## <a name="catlservicemoduletunlock"></a><a name="unlock"></a>CAtlServiceModuleT::Kilidini aç

Hizmetin kilit sayısını verir.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve hata ayıklama için yararlı olabilecek kilit sayısını verir.

## <a name="catlservicemoduletunregisterappid"></a><a name="unregisterappid"></a>CAtlServiceModuleT::Kayıt DışıAppId

Hizmeti kayıt defterinden kaldırır.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catlservicemoduletwinmain"></a><a name="winmain"></a>CAtlServiceModuleT::WinMain

Bu yöntem, hizmeti başlatmak için gereken kodu uygular.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl gösterilebildiğini belirtir. Bu parametre [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) bölümünde tartışılan değerlerden biri olabilir.

### <a name="return-value"></a>Dönüş Değeri

Hizmetin iade değerini verir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem komut satırını işler [(CAtlServiceModuleT::ParseCommandLine](#parsecommandline)ile) ve sonra hizmeti başlatır [(CAtlServiceModuleT kullanarak::Başlat).](#start)

## <a name="see-also"></a>Ayrıca bkz.

[CAtlExeModuleT Sınıfı](../../atl/reference/catlexemodulet-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
