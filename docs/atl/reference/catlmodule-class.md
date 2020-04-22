---
title: CAtlModule Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
ms.openlocfilehash: cfc11a95a8d5d9354279f4c71698a6bc35c7aca7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748624"
---
# <a name="catlmodule-class"></a>CAtlModule Sınıfı

Bu sınıf, çeşitli ATL modül sınıfları tarafından kullanılan yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlModülü::CAtlModule](#catlmodule)|Oluşturucu.|
|[CAtlModülü::~CAtlModülü](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|ATL Kayıt Defteri Bileşeni (Registrar) değiştirme haritasına parametreler eklemek için bu yöntemi geçersiz kılın.|
|[CAtlModülü::AddTermFunc](#addtermfunc)|Modül sona erdiğinde çağrılacak yeni bir işlev ekler.|
|[CAtlModülü::GetGITPtr](#getgitptr)|Genel Arabirim İşaretçisini döndürür.|
|[CAtlModule::GetLockCount](#getlockcount)|Kilit sayısını döndürür.|
|[CAtlModule::Kilit](#lock)|Kilit sayısını nitreeder.|
|[CAtlModule::Dönem](#term)|Tüm veri üyelerini serbest bırakır.|
|[CAtlModule::Kilidini aç](#unlock)|Kilit sayısını erteler.|
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Bir nesneyi kaydetmek veya kaydetmek için belirtilen kaynakta bulunan komut dosyasını çalıştırın.|
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Bu yöntem, `UpdateRegistryFromResourceD` kayıt defteri güncelleştirmesi gerçekleştirmek için çağrılır.|
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Bir nesneyi kaydetmek veya kaydetmek için belirtilen kaynakta bulunan komut dosyasını çalıştırın. Bu yöntem statik olarak ATL Kayıt Defteri Bileşenine bağlanır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAtlModülü::m_libid](#m_libid)|Geçerli modülün GUID'ini içerir.|
|[CAtlModülü::m_pGIT](#m_pgit)|Genel Arabirim Tablosuna işaretçi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, Sırasıyla DLL uygulamaları, EXE uygulamaları ve Windows hizmetleri için destek sağlamak için [CAtlDllModuleT Class](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT Class](../../atl/reference/catlexemodulet-class.md)ve [CAtlServiceModuleT Class](../../atl/reference/catlservicemodulet-class.md) tarafından kullanılır.

ATL'deki modüller hakkında daha fazla bilgi için [ATL Modül Sınıfları'na](../../atl/atl-module-classes.md)bakın.

Bu sınıf, ATL'nin önceki sürümlerinde kullanılan eski [CComModule Sınıfının](../../atl/reference/ccommodule-class.md) yerini alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

`CAtlModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="catlmoduleaddcommonrgsreplacements"></a><a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSReplacements

ATL Kayıt Defteri Bileşeni (Registrar) değiştirme haritasına parametreler eklemek için bu yöntemi geçersiz kılın.

```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```

### <a name="parameters"></a>Parametreler

*pRegistrar*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Değiştirilebilir parametreler, kayıt şirketinin istemcisinin çalışma zamanı verilerini belirtmesine olanak sağlar. Bunu yapmak için, Kayıt Şirketi komut dosyanızdaki değiştirilebilir parametrelerle ilişkili değerleri girdiği yedek bir eşeği tutar. Kayıt Şirketi bu girişleri çalışma zamanında yapar.

Daha fazla bilgi için [Değiştirilebilir Parametreleri (Kayıt Şirketi Ön İşlemci) kullanarak](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) konuya bakın.

## <a name="catlmoduleaddtermfunc"></a><a name="addtermfunc"></a>CAtlModülü::AddTermFunc

Modül sona erdiğinde çağrılacak yeni bir işlev ekler.

```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```

### <a name="parameters"></a>Parametreler

*pFunc*<br/>
Eklenecek işleviçin işaretçi.

*Dw*<br/>
Kullanıcı tanımlı veriler, işleve aktarılır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catlmodulecatlmodule"></a><a name="catlmodule"></a>CAtlModülü::CAtlModule

Oluşturucu.

```
CAtlModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Veri üyelerini başlatır ve modülün iş parçacığı etrafında kritik bir bölüm başlatır.

## <a name="catlmodulecatlmodule"></a><a name="dtor"></a>CAtlModülü::~CAtlModülü

Yıkıcı.

```
~CAtlModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini serbest bırakır.

## <a name="catlmodulegetgitptr"></a><a name="getgitptr"></a>CAtlModülü::GetGITPtr

Global Arabirim Tablosu için bir işaretçi alır.

```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```

### <a name="parameters"></a>Parametreler

*ppGIT*<br/>
İşaretçiyi Global Arabirim Tablosu'na alacak değişkeni işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hata yla ilgili bir hata kodunu verir. *E_POINTER, ppGIT* NULL'a eşitse döndürülür.

### <a name="remarks"></a>Açıklamalar

Global Arabirim Tablosu nesnesi yoksa oluşturulur ve adresi üye değişken [CAtlModule::m_pGIT.](#m_pgit)

Hata ayıklama oluştururda, *ppGIT* NULL'a eşitse veya Global Arabirim Tablosu işaretçisi elde edilemiyorsa bir tasnif hatası oluşur.

Global Arayüz Tablosu hakkında bilgi için [IGlobalInterfaceTable'a](/windows/win32/api/objidl/nn-objidl-iglobalinterfacetable) bakın.

## <a name="catlmodulegetlockcount"></a><a name="getlockcount"></a>CAtlModule::GetLockCount

Kilit sayısını döndürür.

```
virtual LONG GetLockCount() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit sayısını döndürür. Bu değer tanılama ve hata ayıklama için yararlı olabilir.

## <a name="catlmodulelock"></a><a name="lock"></a>CAtlModule::Kilit

Kilit sayısını nitreeder.

```
virtual LONG Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit sayısını artımlar ve güncelleştirilmiş değeri döndürür. Bu değer tanılama ve hata ayıklama için yararlı olabilir.

## <a name="catlmodulem_libid"></a><a name="m_libid"></a>CAtlModülü::m_libid

Geçerli modülün GUID'ini içerir.

```
static GUID m_libid;
```

## <a name="catlmodulem_pgit"></a><a name="m_pgit"></a>CAtlModülü::m_pGIT

Genel Arabirim Tablosuna işaretçi.

```
IGlobalInterfaceTable* m_pGIT;
```

## <a name="catlmoduleterm"></a><a name="term"></a>CAtlModule::Dönem

Tüm veri üyelerini serbest bırakır.

```cpp
void Term() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini serbest bırakır. Bu yöntem yıkıcı tarafından çağrılır.

## <a name="catlmoduleunlock"></a><a name="unlock"></a>CAtlModule::Kilidini aç

Kilit sayısını erteler.

```
virtual LONG Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit sayısını verir ve güncelleştirilen değeri döndürür. Bu değer tanılama ve hata ayıklama için yararlı olabilir.

## <a name="catlmoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CAtlModule::UpdateRegistryFromResourceD

Bir nesneyi kaydetmek veya kaydetmek için belirtilen kaynakta bulunan komut dosyasını çalıştırın.

```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*lpszRes*<br/>
Kaynak adı.

*nResID*<br/>
Kaynak kimliği.

*bKayıt*<br/>
Nesne nin kaydedilmesi gerekiyorsa DOĞRU; YANLIŞ aksi takdirde.

*pMapEntries*<br/>
Komut dosyasının değiştirilebilir parametreleri ile ilişkili değerleri depolama değiştirme eşlemi için bir işaretçi. ATL otomatik olarak %MODÜL% kullanır. Ek değiştirilebilir parametreleri kullanmak için [Bkz. CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Aksi takdirde, NULL varsayılan değerini kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

*lpszRes veya nResID*tarafından belirtilen kaynakta bulunan komut dosyasını çalıştırın. *bRegister* TRUE ise, bu yöntem nesneyi sistem kayıt defterine kaydeder; aksi takdirde nesneyi kayıt defterinden kaldırır.

ATL Kayıt Defteri Bileşenine (Registrar) statik olarak bağlanmak için [Bkz. CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).

Bu yöntem [catlModule çağırır::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) ve [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).

## <a name="catlmoduleupdateregistryfromresourcedhelper"></a><a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper

Bu yöntem, `UpdateRegistryFromResourceD` kayıt defteri güncelleştirmesi gerçekleştirmek için çağrılır.

```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*lpszRes*<br/>
Kaynak adı.

*bKayıt*<br/>
Nesnenin kaydedilip kaydedilmemesi gerektiğini gösterir.

*pMapEntries*<br/>
Komut dosyasının değiştirilebilir parametreleri ile ilişkili değerleri depolama değiştirme eşlemi için bir işaretçi. ATL otomatik olarak %MODÜL% kullanır. Ek değiştirilebilir parametreleri kullanmak için [Bkz. CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Aksi takdirde, NULL varsayılan değerini kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CAtlModule uygulamasını sağlar::UpdateRegistryFromResourceD](#updateregistryfromresourced).

## <a name="catlmoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CAtlModule::UpdateRegistryFromResourceS

Bir nesneyi kaydetmek veya kaydetmek için belirtilen kaynakta bulunan komut dosyasını çalıştırın. Bu yöntem statik olarak ATL Kayıt Defteri Bileşenine bağlanır.

```
HRESULT WINAPI UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*nResID*<br/>
Kaynak kimliği.

*lpszRes*<br/>
Kaynak adı.

*bKayıt*<br/>
Kaynak komut dosyasının kaydedilip kaydedilmemesi gerektiğini gösterir.

*pMapEntries*<br/>
Komut dosyasının değiştirilebilir parametreleri ile ilişkili değerleri depolama değiştirme eşlemi için bir işaretçi. ATL otomatik olarak %MODÜL% kullanır. Ek değiştirilebilir parametreleri kullanmak için [Bkz. CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Aksi takdirde, NULL varsayılan değerini kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[CAtlModule benzer::UpdateRegistryFromResourceD](#updateregistryfromresourced) `CAtlModule::UpdateRegistryFromResourceS` dışında ATL Kayıt Bileşeni (Registrar) statik bir bağlantı oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_MODULE](atl-typedefs.md#_atl_module)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Modül Sınıfları](../../atl/atl-module-classes.md)<br/>
[Kayıt Bileşeni (Registrar)](../../atl/atl-registry-component-registrar.md)
