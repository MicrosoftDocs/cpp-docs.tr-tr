---
title: CAtlExeModuleT sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
ms.openlocfilehash: 87e526a10c9bcd6a52f4544c50344c5145cfa732
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769556"
---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT sınıfı

Bu sınıf, bir uygulama için modülü temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınıza türetilen `CAtlExeModuleT`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|Oluşturucu.|
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlExeModuleT::InitializeCom](#initializecom)|COM'u başlatan|
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Komut satırı ayrıştırır ve gerekirse kayıt gerçekleştirir.|
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|İleti döngüsünden hemen çıktıktan sonra bu yöntem çağrılır.|
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Bu yöntem, ileti döngüsü girmeden hemen önce çağrılır.|
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|Sınıf nesnesini kaydeder.|
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|Sınıf nesnesi iptal eder.|
|[CAtlExeModuleT::Run](#run)|Bu yöntem, başlatma, ileti döngüsü çalıştırmak EXE modülünde kodu yürütür ve temizleme.|
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Bu yöntem, ileti döngüsü yürütür.|
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|COM başlamasını iptal eder|
|[CAtlExeModuleT::Unlock](#unlock)|Modülün kilit sayısını azaltır.|
|[CAtlExeModuleT::WinMain](#winmain)|Bu yöntem, bir EXE çalıştırmak için gereken kodu uygular.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Modül kapatılıyor gecikme olmalıdır belirten bir bayrak.|
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Tüm nesneleri kapatma öncesinde yayımlanan sağlamak için kullanılan bir duraklatma değeri.|
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Modülün kaldırma geciktirmek için kullanılan bir zaman aşımı değeri.|

## <a name="remarks"></a>Açıklamalar

`CAtlExeModuleT` Modül için bir uygulama (EXE) temsil eder ve bir EXE oluşturmak, komut satırı işlemeyi, sınıf nesneleri kaydetme, ileti döngüsü çalıştıran ve temizleme Çıkışta destekleyen kodunu içerir.

Bu sınıf, COM nesneleri EXE Server'daki sürekli olarak oluşturulan yok ve performansı artırmak için tasarlanmıştır. Son COM nesnesi kullanıma sunulduktan sonra EXE tarafından belirtilen bir süre bekler [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) veri üyesi. Bu süre boyunca hiçbir etkinlik yoksa (diğer bir deyişle, hiçbir COM nesneleri oluşturma), kapatma işlemi başlatılır.

[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) veri üyesi olduğu EXE yukarıda tanımlanan mekanizması kullanması gerekip gerekmediğini belirlemek için kullanılan bayrak. False olarak ayarlanırsa, modül hemen sonlanacaktır.

ATL modüller hakkında daha fazla bilgi için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlExeModuleT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="catlexemodulet"></a>  CAtlExeModuleT::CAtlExeModuleT

Oluşturucu.

```
CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

EXE modülü başlatılamadı, WinMain daha fazla işleme olmadan hemen döndürür.

##  <a name="dtor"></a>  CAtlExeModuleT:: ~ CAtlExeModuleT

Yıkıcı.

```
~CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="initializecom"></a>  CAtlExeModuleT::InitializeCom

COM'u başlatan

```
static HRESULT InitializeCom() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oluşturucudan çağrılır ve COM varsayılan uygulamasından farklı bir şekilde başlatmak için geçersiz kılınabilir. Varsayılan uygulama ya da çağırır `CoInitializeEx(NULL, COINIT_MULTITHREADED)` veya `CoInitialize(NULL)` proje yapılandırmasına bağlı olarak.

Normalde bu yöntemi geçersiz kılma gerektirir geçersiz kılma [CAtlExeModuleT::UninitializeCom](#uninitializecom).

##  <a name="m_bdelayshutdown"></a>  CAtlExeModuleT::m_bDelayShutdown

Modül kapatılıyor gecikme olmalıdır belirten bir bayrak.

```
bool m_bDelayShutdown;
```

### <a name="remarks"></a>Açıklamalar

Bkz: [CAtlExeModuleT genel bakış](../../atl/reference/catlexemodulet-class.md) Ayrıntılar için.

##  <a name="m_dwpause"></a>  CAtlExeModuleT::m_dwPause

Tüm nesneleri kapatma öncesinde geçmiş sağlamak için kullanılan bir duraklatma değeri.

```
DWORD m_dwPause;
```

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu değeri değiştirmek [CAtlExeModuleT::InitializeCom](#initializecom) duraklatma değeri olarak sunucu kapatılıyor için kullanılır. milisaniye sayısını ayarlamak için. Varsayılan değer 1000 milisaniyeden kısadır.

##  <a name="m_dwtimeout"></a>  CAtlExeModuleT::m_dwTimeOut

Modülün kaldırma geciktirmek için kullanılan bir zaman aşımı değeri.

```
DWORD m_dwTimeOut;
```

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu değeri değiştirmek [CAtlExeModuleT::InitializeCom](#initializecom) Sunucu kapatılıyor için zaman aşımı değeri olarak kullanılan milisaniye sayısını tanımlamak için. Varsayılan değer 5000 milisaniyedir. Bkz: [CAtlExeModuleT genel bakış](../../atl/reference/catlexemodulet-class.md) daha fazla ayrıntı için.

##  <a name="parsecommandline"></a>  CAtlExeModuleT::ParseCommandLine

Komut satırı ayrıştırır ve gerekirse kayıt gerçekleştirir.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Parametreler

*lpCmdLine*<br/>
Komut satırı uygulamaya geçirildi.

*pnRetCode*<br/>
Kayıt için (bir yerde gerçekleştirirse) karşılık gelen HRESULT.

### <a name="return-value"></a>Dönüş Değeri

Uygulama, aksi takdirde false çalıştırmaya devam etmeli, true döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem çağrılır [CAtlExeModuleT::WinMain](#winmain) ve komut satırı anahtarları işlemek için geçersiz kılınabilir. Varsayılan uygulama denetler **/regserver** ve **/Unregserver** komut satırı bağımsız değişkenlerini ve kayıt veya silme gerçekleştirir.

##  <a name="postmessageloop"></a>  CAtlExeModuleT::PostMessageLoop

İleti döngüsünden hemen çıktıktan sonra bu yöntem çağrılır.

```
HRESULT PostMessageLoop() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Özel uygulama temizleme işlemini gerçekleştirmek için bu yöntemi yok sayın. Varsayılan Uygulama çağrıları [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects).

##  <a name="premessageloop"></a>  CAtlExeModuleT::PreMessageLoop

Bu yöntem, ileti döngüsü girmeden hemen önce çağrılır.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Olarak geçirilen değer *nShowCmd* WinMain parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Uygulama için özel başlatma kodu eklemek için bu yöntemi yok sayın. Varsayılan uygulama sınıfını nesneleri kaydeder.

##  <a name="registerclassobjects"></a>  CAtlExeModuleT::RegisterClassObjects

Diğer uygulamalar ona bağlanabilmesi için sınıf nesnesini OLE ile kaydeder.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Parametreler

*dwClsContext*<br/>
Sınıf nesnesi çalıştırılacak bağlamı belirtir. Olası değerler şunlardır: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER.

*CertOpenStore*<br/>
Bağlantı türleri sınıf nesnesi belirler. Olası değerler şunlardır: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE.

### <a name="return-value"></a>Dönüş Değeri

Başarı, kaydetmek için hiçbir sınıfın olsaydı S_FALSE veya hatasında bir hata HRESULT S_OK döndürür.

##  <a name="revokeclassobjects"></a>  CAtlExeModuleT::RevokeClassObjects

Sınıf nesnesini kaldırır.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı, kaydetmek için hiçbir sınıfın olsaydı S_FALSE veya hatasında bir hata HRESULT S_OK döndürür.

##  <a name="run"></a>  CAtlExeModuleT::Run

Bu yöntem, başlatma, ileti döngüsü çalıştırmak EXE modülünde kodu yürütür ve temizleme.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl mı belirtir. Bu parametre ele değerlerden biri olabilir [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) bölümü. Varsayılan olarak SW_HIDE.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem geçersiz kılınabilir. Ancak, uygulamada bunu geçersiz kılmak için iyidir [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), veya [CAtlExeModuleT::PostMessageLoop](#postmessageloop) Bunun yerine.

##  <a name="runmessageloop"></a>  CAtlExeModuleT::RunMessageLoop

Bu yöntem, ileti döngüsü yürütür.

```
void RunMessageLoop() throw();
```

### <a name="remarks"></a>Açıklamalar

İleti döngüsünden davranışını değiştirmek için bu yöntem geçersiz kılınabilir.

##  <a name="uninitializecom"></a>  CAtlExeModuleT::UninitializeCom

COM başlamasını iptal eder

```
static void UninitializeCom() throw();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem yalnızca çağırır [CoUninitialize](/windows/desktop/api/combaseapi/nf-combaseapi-couninitialize) ve yıkıcıdan çağrılır. Geçersiz kılmanız bu yöntemi geçersiz kılın [CAtlExeModuleT::InitializeCom](#initializecom).

##  <a name="unlock"></a>  CAtlExeModuleT::Unlock

Modülün kilit sayısını azaltır.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı veya test olabilen bir değer döndürür.

##  <a name="winmain"></a>  CAtlExeModuleT::WinMain

Bu yöntem, bir EXE çalıştırmak için gereken kodu uygular.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl mı belirtir. Bu parametre ele değerlerden biri olabilir [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) bölümü.

### <a name="return-value"></a>Dönüş Değeri

Yürütülebilir dosya'nın dönüş değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem geçersiz kılınabilir. Kılıyorsa [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::PostMessageLoop](#postmessageloop), veya [CAtlExeModuleT::RunMessageLoop](#runmessageloop) yeterli esneklik sağlamaz , geçersiz kılmak mümkündür `WinMain` bu yöntemi kullanarak işlev.

## <a name="see-also"></a>Ayrıca bkz.

[ATLDuck örnek](../../overview/visual-cpp-samples.md)<br/>
[CAtlModuleT Sınıfı](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlDllModuleT Sınıfı](../../atl/reference/catldllmodulet-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
