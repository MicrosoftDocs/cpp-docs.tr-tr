---
title: CAtlExeModuleT Sınıfı
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
ms.openlocfilehash: 33edd8f2483bc21ea6cf8b68f80a2501c37d1a40
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748754"
---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT Sınıfı

Bu sınıf bir uygulama için modülü temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `CAtlExeModuleT`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|Oluşturucu.|
|[CAtlExeModuleT::~CAtlExeModuleT](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlExeModuleT::InitializeCom](#initializecom)|COM'u ilke ler.|
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Komut satırını parses ve gerekirse kayıt gerçekleştirir.|
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|Bu yöntem, ileti döngüsü çıktıktan hemen sonra çağrılır.|
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Bu yöntem, ileti döngüsüne girmeden hemen önce çağrılır.|
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|Sınıf nesnesini kaydeder.|
|[CAtlExeModuleT::İptalSınıf Nesneleri](#revokeclassobjects)|Sınıf nesnesini iptal eder.|
|[CAtlExeModuleT::Çalıştır](#run)|Bu yöntem, exe modülünde kod ları çalıştırıp, ileti döngüsünün başlatılmasını, çalıştırMasını ve temizlemesini sağlar.|
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Bu yöntem ileti döngüsü yürütür.|
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|Com'u başlatmaz.|
|[CAtlExeModuleT::Kilidini açın](#unlock)|Modülün kilit sayısını eritiyor.|
|[CAtlExeModuleT::WinMain](#winmain)|Bu yöntem, exe çalıştırmak için gerekli kodu uygular.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Modülün kapatılmasında gecikme olması gerektiğini belirten bir bayrak.|
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Tüm nesnelerin kapanmadan önce serbest bırakılmasını sağlamak için kullanılan bir duraklatma değeri.|
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Modülün boşaltılmasını geciktirmek için kullanılan bir zaman kaybı değeri.|

## <a name="remarks"></a>Açıklamalar

`CAtlExeModuleT`bir uygulama (EXE) için modülü temsil eder ve exe oluşturmayı, komut satırını işlemeyi, sınıf nesnelerini kaydetmeyi, ileti döngüsünü çalıştırmayı ve çıkışta temizlemeyi destekleyen kodlar içerir.

Bu sınıf, EXE sunucusundaki COM nesneleri sürekli olarak oluşturulduğunda ve yok edildiğinde performansı artırmak için tasarlanmıştır. Son COM nesnesi yayımlandıktan sonra, EXE [CAtlExeModuleT:m_dwTimeOut](#m_dwtimeout) veri üyesi tarafından belirtilen bir süre bekler. Bu dönemde etkinlik yoksa (diğer bir süre COM nesnesi oluşturulmazsa), kapatma işlemi başlatılır.

[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) veri üyesi EXE'nin yukarıda tanımlanan mekanizmayı kullanıp kullanmadığını belirlemek için kullanılan bir bayraktır. Yanlış olarak ayarlanırsa, modül hemen sonlanır.

ATL'deki modüller hakkında daha fazla bilgi için [ATL Modül Sınıfları'na](../../atl/atl-module-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModülü](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlExeModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="catlexemoduletcatlexemodulet"></a><a name="catlexemodulet"></a>CAtlExeModuleT::CAtlExeModuleT

Oluşturucu.

```
CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

EXE modülü başharfe atılamazsa, WinMain daha fazla işlem yapılmadan hemen geri döner.

## <a name="catlexemoduletcatlexemodulet"></a><a name="dtor"></a>CAtlExeModuleT::~CAtlExeModuleT

Yıkıcı.

```
~CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest sağlar.

## <a name="catlexemoduletinitializecom"></a><a name="initializecom"></a>CAtlExeModuleT::InitializeCom

COM'u ilke ler.

```
static HRESULT InitializeCom() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oluşturucudan çağrılır ve COM'u varsayılan uygulamadan farklı bir şekilde başlatmaya geçersiz kılınabilir. Varsayılan uygulama çağırır `CoInitializeEx(NULL, COINIT_MULTITHREADED)` `CoInitialize(NULL)` veya proje yapılandırması bağlı.

Bu yöntemi geçersiz kılmak normalde [CAtlExeModuleT::UninitializeCom'un](#uninitializecom)geçersiz kılınması gerekir.

## <a name="catlexemoduletm_bdelayshutdown"></a><a name="m_bdelayshutdown"></a>CAtlExeModuleT::m_bDelayShutdown

Modülün kapatılmasında gecikme olması gerektiğini belirten bir bayrak.

```
bool m_bDelayShutdown;
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [CAtlExeModuleT Genel Bakış'a](../../atl/reference/catlexemodulet-class.md) bakın.

## <a name="catlexemoduletm_dwpause"></a><a name="m_dwpause"></a>CAtlExeModuleT::m_dwPause

Tüm nesnelerin kapanmadan önce gittiğinden emin olmak için kullanılan bir duraklatma değeri.

```
DWORD m_dwPause;
```

### <a name="remarks"></a>Açıklamalar

[CAtlExeModuleT::InitializeCom'u](#initializecom) arayarak sunucuyu kapatmak için duraklatma değeri olarak kullanılan milisaniye sayısını ayarlamak için bu değeri değiştirin. Varsayılan değer 1000 milisaniyedir.

## <a name="catlexemoduletm_dwtimeout"></a><a name="m_dwtimeout"></a>CAtlExeModuleT::m_dwTimeOut

Modülün boşaltılmasını geciktirmek için kullanılan bir zaman kaybı değeri.

```
DWORD m_dwTimeOut;
```

### <a name="remarks"></a>Açıklamalar

[CAtlExeModuleT::InitializeCom'u](#initializecom) arayarak sunucuyu kapatmak için zaman kaybı değeri olarak kullanılan milisaniye sayısını tanımladıktan sonra bu değeri değiştirin. Varsayılan değer 5000 milisaniyedir. Daha fazla bilgi için [CAtlExeModuleT Genel Bakış'a](../../atl/reference/catlexemodulet-class.md) bakın.

## <a name="catlexemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlExeModuleT::ParseCommandLine

Komut satırını parses ve gerekirse kayıt gerçekleştirir.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Parametreler

*lpCmdLine*<br/>
Komut satırı uygulamaya geçti.

*pnRetCode*<br/>
Kayıt için karşılık gelen HRESULT (gerçekleştiyse).

### <a name="return-value"></a>Dönüş Değeri

Uygulama çalışmaya devam ederse, aksi takdirde yanlış döndürün.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CAtlExeModuleT denir::WinMain](#winmain) ve komut satırı anahtarları işlemek için geçersiz kılınabilir. Varsayılan uygulama **/RegServer** ve **/UnRegServer** komut satırı bağımsız değişkenlerini denetler ve kayıt veya kayıt dışı gerçekleştirir.

## <a name="catlexemoduletpostmessageloop"></a><a name="postmessageloop"></a>CAtlExeModuleT::PostMessageLoop

Bu yöntem, ileti döngüsü çıktıktan hemen sonra çağrılır.

```
HRESULT PostMessageLoop() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Özel uygulama temizleme gerçekleştirmek için bu yöntemi geçersiz kılın. Varsayılan uygulama [CAtlExeModuleT çağırır::RevokeClassObjects](#revokeclassobjects).

## <a name="catlexemoduletpremessageloop"></a><a name="premessageloop"></a>CAtlExeModuleT::PreMessageLoop

Bu yöntem, ileti döngüsüne girmeden hemen önce çağrılır.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Değer WinMain *nShowCmd* parametresi olarak geçti.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Uygulama için özel başlatma kodu eklemek için bu yöntemi geçersiz kılın. Varsayılan uygulama sınıf nesnelerini kaydeder.

## <a name="catlexemoduletregisterclassobjects"></a><a name="registerclassobjects"></a>CAtlExeModuleT::RegisterClassObjects

Diğer uygulamaların bağlanabilmesi için sınıf nesnesini OLE ile kaydeder.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Parametreler

*dwClsBağlam*<br/>
Sınıf nesnesinin çalıştırılacak olduğu bağlamı belirtir. Olası değerler CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER.

*Dwflags*<br/>
Sınıf nesnesine bağlantı türlerini belirler. Olası değerler REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE.

### <a name="return-value"></a>Dönüş Değeri

Kayıt olacak sınıf yoksa veya hata da HRESULT'da bir hata varsa, S_FALSE başarı S_OK döndürür.

## <a name="catlexemoduletrevokeclassobjects"></a><a name="revokeclassobjects"></a>CAtlExeModuleT::İptalSınıf Nesneleri

Sınıf nesnesini kaldırır.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt olacak sınıf yoksa veya hata da HRESULT'da bir hata varsa, S_FALSE başarı S_OK döndürür.

## <a name="catlexemoduletrun"></a><a name="run"></a>CAtlExeModuleT::Çalıştır

Bu yöntem, exe modülünde kod ları çalıştırıp, ileti döngüsünün başlatılmasını, çalıştırMasını ve temizlemesini sağlar.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl gösterilebildiğini belirtir. Bu parametre [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) bölümünde tartışılan değerlerden biri olabilir. Varsayılan olarak SW_HIDE.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem geçersiz kılınabilir. Ancak, uygulamada [catlExeModuleT geçersiz kılmak daha iyidir::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), veya [CAtlExeModuleT::PostMessageLoop](#postmessageloop) yerine.

## <a name="catlexemoduletrunmessageloop"></a><a name="runmessageloop"></a>CAtlExeModuleT::RunMessageLoop

Bu yöntem ileti döngüsü yürütür.

```cpp
void RunMessageLoop() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ileti döngüsünün davranışını değiştirmek için geçersiz kılınabilir.

## <a name="catlexemoduletuninitializecom"></a><a name="uninitializecom"></a>CAtlExeModuleT::UninitializeCom

Com'u başlatmaz.

```
static void UninitializeCom() throw();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem sadece [CoUninitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize) çağırır ve yıkıcı denir. [CAtlExeModuleT geçersiz](#initializecom)kılarsanız bu yöntemi geçersiz kılın::InitializeCom .

## <a name="catlexemoduletunlock"></a><a name="unlock"></a>CAtlExeModuleT::Kilidini açın

Modülün kilit sayısını eritiyor.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer verir.

## <a name="catlexemoduletwinmain"></a><a name="winmain"></a>CAtlExeModuleT::WinMain

Bu yöntem, exe çalıştırmak için gerekli kodu uygular.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Parametreler

*nShowCmd*<br/>
Pencerenin nasıl gösterilebildiğini belirtir. Bu parametre [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) bölümünde tartışılan değerlerden biri olabilir.

### <a name="return-value"></a>Dönüş Değeri

Çalıştırılabilenin iade değerini verir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem geçersiz kılınabilir. [CAtlExeModuleT::PreMessageLoop,](#premessageloop) [CAtlExeModuleT::PostMessageLoop](#postmessageloop)veya [CAtlExeModuleT::RunMessageLoop](#runmessageloop) yeterli esneklik sağlamıyorsa, bu yöntemi kullanarak `WinMain` işlevi geçersiz kılmak mümkündür.

## <a name="see-also"></a>Ayrıca bkz.

[ATLDuck Örnek](../../overview/visual-cpp-samples.md)<br/>
[CAtlModuleT Sınıfı](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlDllModuleT Sınıfı](../../atl/reference/catldllmodulet-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
