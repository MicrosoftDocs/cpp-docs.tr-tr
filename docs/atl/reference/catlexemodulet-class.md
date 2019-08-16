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
ms.openlocfilehash: d37cc8e97d29cbedfeb4ba79502d44529485399f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497836"
---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT sınıfı

Bu sınıf, bir uygulamanın modülünü temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız öğesinden `CAtlExeModuleT`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlExeModuleT:: Catlexemodüle Let](#catlexemodulet)|Oluşturucu.|
|[CAtlExeModuleT:: ~ Catlexemodüle Let](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlExeModuleT:: InitializeCom](#initializecom)|COM başlatır.|
|[CAtlExeModuleT::P arseCommandLine](#parsecommandline)|Komut satırını ayrıştırır ve gerekirse kayıt gerçekleştirir.|
|[CAtlExeModuleT::P ostMessageLoop](#postmessageloop)|Bu yöntem ileti döngüsünden çıktıktan hemen sonra çağrılır.|
|[CAtlExeModuleT::P reMessageLoop](#premessageloop)|Bu yöntem ileti döngüsüne girmeden hemen önce çağrılır.|
|[CAtlExeModuleT:: RegisterClassObjects](#registerclassobjects)|Sınıf nesnesini kaydeder.|
|[CAtlExeModuleT:: RevokeClassObjects](#revokeclassobjects)|Sınıf nesnesini iptal eder.|
|[CAtlExeModuleT:: Run](#run)|Bu yöntem, başlatmak, ileti döngüsünü çalıştırmak ve temizlemek için EXE modülünde kodu yürütür.|
|[CAtlExeModuleT:: RunMessageLoop](#runmessageloop)|Bu yöntem ileti döngüsünü yürütür.|
|[CAtlExeModuleT:: Unınitializecom](#uninitializecom)|COM başlatılır.|
|[CAtlExeModuleT:: unlock](#unlock)|Modülün kilit sayısını azaltır.|
|[CAtlExeModuleT:: WinMain](#winmain)|Bu yöntem, bir EXE çalıştırmak için gereken kodu uygular.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlExeModuleT:: m_bDelayShutdown](#m_bdelayshutdown)|Modülün kapanmasından bir gecikme olması gerektiğini belirten bir bayrak.|
|[CAtlExeModuleT:: m_dwPause](#m_dwpause)|Kapatmadan önce tüm nesnelerin serbest bırakılacağını sağlamak için kullanılan bir duraklatma değeri.|
|[CAtlExeModuleT:: m_dwTimeOut](#m_dwtimeout)|Modülün kaldırılmasını geciktirmede kullanılan bir zaman aşımı değeri.|

## <a name="remarks"></a>Açıklamalar

`CAtlExeModuleT`bir uygulamanın (EXE) modülünü temsil eder ve bir EXE oluşturmayı, komut satırını işlemeyi, sınıf nesnelerini kaydetmeyi, ileti döngüsünü çalıştırmayı ve çıkışta temizlemeyi destekleyen kodu içerir.

Bu sınıf, EXE sunucusundaki COM nesneleri sürekli olarak oluşturulduğunda ve yok edildiğinde performansı artırmak için tasarlanmıştır. Son COM nesnesi yayımlandıktan sonra, EXE, [CAtlExeModuleT:: m_dwTimeOut](#m_dwtimeout) veri üyesi tarafından belirtilen bir süre bekler. Bu süre boyunca hiçbir etkinlik yoksa (yani, COM nesnesi oluşturulmadıysa), kapatılıyor işlemi başlatılır.

[CAtlExeModuleT:: m_bDelayShutdown](#m_bdelayshutdown) veri ÜYESI, exe ' nin yukarıda tanımlanan mekanizmayı kullanıp kullanmadığını belirlemede kullanılan bir bayrak. Yanlış olarak ayarlanırsa modül hemen sonlandırılır.

ATL 'deki modüller hakkında daha fazla bilgi için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[Catlmodület](../../atl/reference/catlmodulet-class.md)

`CAtlExeModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="catlexemodulet"></a>CAtlExeModuleT:: Catlexemodüle Let

Oluşturucu.

```
CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

EXE modülü başlatılamadığından, WinMain daha fazla işleme olmadan hemen döndürülür.

##  <a name="dtor"></a>CAtlExeModuleT:: ~ Catlexemodüle Let

Yok edicisi.

```
~CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="initializecom"></a>CAtlExeModuleT:: InitializeCom

COM başlatır.

```
static HRESULT InitializeCom() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oluşturucudan çağrılır ve COM 'un varsayılan uygulamadan farklı bir şekilde başlatılması için geçersiz kılınabilir. Varsayılan uygulama, proje yapılandırmasına `CoInitializeEx(NULL, COINIT_MULTITHREADED)` göre `CoInitialize(NULL)` veya ' i çağırır.

Bu yöntemi normalde geçersiz kılmak için [CAtlExeModuleT:: Unınitializecom](#uninitializecom)geçersiz kılınması gerekir.

##  <a name="m_bdelayshutdown"></a>CAtlExeModuleT:: m_bDelayShutdown

Modülün kapanmasından bir gecikme olması gerektiğini belirten bir bayrak.

```
bool m_bDelayShutdown;
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Catlexemodüle Let 'e genel bakış](../../atl/reference/catlexemodulet-class.md) .

##  <a name="m_dwpause"></a>CAtlExeModuleT:: m_dwPause

Tüm nesnelerin kapatmadan önce kaybolduğundan emin olmak için bir duraklatma değeri kullanılır.

```
DWORD m_dwPause;
```

### <a name="remarks"></a>Açıklamalar

Sunucuyu kapatmak için duraklama değeri olarak kullanılan milisaniye sayısını ayarlamak için [Catlexemodület:: InitializeCom](#initializecom) öğesini çağırdıktan sonra bu değeri değiştirin. Varsayılan değer 1000 milisaniyedir.

##  <a name="m_dwtimeout"></a>CAtlExeModuleT:: m_dwTimeOut

Modülün kaldırılmasını geciktirmede kullanılan bir zaman aşımı değeri.

```
DWORD m_dwTimeOut;
```

### <a name="remarks"></a>Açıklamalar

Sunucuyu kapatmak için zaman aşımı değeri olarak kullanılan milisaniye sayısını tanımlamak için [Catlexemodület:: InitializeCom](#initializecom) öğesini çağırdıktan sonra bu değeri değiştirin. Varsayılan değer 5000 milisaniyedir. Daha fazla ayrıntı için bkz. [Catlexemodüle Let genel bakış](../../atl/reference/catlexemodulet-class.md) .

##  <a name="parsecommandline"></a>CAtlExeModuleT::P arseCommandLine

Komut satırını ayrıştırır ve gerekirse kayıt gerçekleştirir.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Parametreler

*lpCmdLine*<br/>
Uygulamaya geçirilen komut satırı.

*Pnekcode*<br/>
Kayda karşılık gelen HRESULT (Eğer gerçekleştiyse).

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın çalışmaya devam etmesi gerekiyorsa true, aksi takdirde false döndürün.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CAtlExeModuleT:: WinMain](#winmain) öğesinden çağrılır ve komut satırı anahtarlarını işlemek için geçersiz kılınabilir. Varsayılan uygulama, **/regserver** ve **/Unregserver** komut satırı bağımsız değişkenlerini denetler ve kayıt veya kayıt silme işlemini gerçekleştirir.

##  <a name="postmessageloop"></a>CAtlExeModuleT::P ostMessageLoop

Bu yöntem ileti döngüsünden çıktıktan hemen sonra çağrılır.

```
HRESULT PostMessageLoop() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Özel uygulama temizleme işlemini gerçekleştirmek için bu yöntemi geçersiz kılın. Varsayılan uygulama [CAtlExeModuleT:: RevokeClassObjects](#revokeclassobjects)öğesini çağırır.

##  <a name="premessageloop"></a>CAtlExeModuleT::P reMessageLoop

Bu yöntem ileti döngüsüne girmeden hemen önce çağrılır.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
WinMain 'te *nShowCmd* parametresi olarak geçirilen değer.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Uygulama için özel başlatma kodu eklemek için bu yöntemi geçersiz kılın. Varsayılan uygulama, sınıf nesnelerini kaydeder.

##  <a name="registerclassobjects"></a>CAtlExeModuleT:: RegisterClassObjects

Diğer uygulamaların bağlanabilmesi için sınıf nesnesini OLE ile kaydeder.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Parametreler

*dwClsContext*<br/>
Sınıf nesnesinin çalıştırılacağı bağlamı belirtir. Olası değerler şunlardır CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER.

*dwFlags*<br/>
Sınıf nesnesine bağlantı türlerini belirler. Olası değerler şunlardır REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı durumunda S_OK, kaydolmak için sınıf yoksa S_FALSE veya hata durumunda HRESULT hatası döndürür.

##  <a name="revokeclassobjects"></a>CAtlExeModuleT:: RevokeClassObjects

Sınıf nesnesini kaldırır.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı durumunda S_OK, kaydolmak için sınıf yoksa S_FALSE veya hata durumunda HRESULT hatası döndürür.

##  <a name="run"></a>CAtlExeModuleT:: Run

Bu yöntem, başlatmak, ileti döngüsünü çalıştırmak ve temizlemek için EXE modülünde kodu yürütür.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl gösterileceğini belirtir. Bu parametre, [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) bölümünde ele alınan değerlerden biri olabilir. Varsayılan olarak SW_HIDE.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem geçersiz kılınabilir. Bununla birlikte, uygulamada [Catlexemodület 'i geçersiz kılmak daha iyidir::P reMessageLoop](#premessageloop), [Catlexemodület:: RunMessageLoop](#runmessageloop)veya [catlexemodulet::P ostmessageloop](#postmessageloop) .

##  <a name="runmessageloop"></a>CAtlExeModuleT:: RunMessageLoop

Bu yöntem ileti döngüsünü yürütür.

```
void RunMessageLoop() throw();
```

### <a name="remarks"></a>Açıklamalar

İleti döngüsünün davranışını değiştirmek için bu yöntem geçersiz kılınabilir.

##  <a name="uninitializecom"></a>CAtlExeModuleT:: Unınitializecom

COM başlatılır.

```
static void UninitializeCom() throw();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem yalnızca [CoUnInitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize) öğesini çağırır ve yıkıcıdan çağırılır. [CAtlExeModuleT:: InitializeCom](#initializecom)öğesini geçersiz kılarsınız bu yöntemi geçersiz kılın.

##  <a name="unlock"></a>CAtlExeModuleT:: unlock

Modülün kilit sayısını azaltır.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer döndürür.

##  <a name="winmain"></a>CAtlExeModuleT:: WinMain

Bu yöntem, bir EXE çalıştırmak için gereken kodu uygular.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl gösterileceğini belirtir. Bu parametre, [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) bölümünde ele alınan değerlerden biri olabilir.

### <a name="return-value"></a>Dönüş Değeri

Yürütülebilir dosyanın dönüş değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem geçersiz kılınabilir. [CAtlExeModuleT geçersiz kılınıyorsa:P remessageloop](#premessageloop), [catlexemodület::P ostmessageloop](#postmessageloop)veya [CAtlExeModuleT:: RunMessageLoop](#runmessageloop) yeterli esneklik sağlamıyor, bunu kullanarak `WinMain` işlevi geçersiz kılmak mümkündür yöntemidir.

## <a name="see-also"></a>Ayrıca bkz.

[ATLDuck örneği](../../overview/visual-cpp-samples.md)<br/>
[CAtlModuleT Sınıfı](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlDllModuleT Sınıfı](../../atl/reference/catldllmodulet-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
