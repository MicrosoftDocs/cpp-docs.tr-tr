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
ms.openlocfilehash: 10658b118c97afe99144c3a4d25e0297aba3727f
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168021"
---
# <a name="catlmodule-class"></a>CAtlModule Sınıfı

Bu sınıf, birkaç ATL modül sınıfı tarafından kullanılan yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlModule:: CAtlModule](#catlmodule)|Oluşturucu.|
|[CAtlModule:: ~ CAtlModule](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlModule:: Addcommonrgsdeğiştirmeler](#addcommonrgsreplacements)|ATL kayıt defteri bileşeni (kaydedici) değiştirme eşlemesine parametreler eklemek için bu yöntemi geçersiz kılın.|
|[CAtlModule:: AddTermFunc](#addtermfunc)|Modül sonlandırıldığında çağrılacak yeni bir işlev ekler.|
|[CAtlModule:: GetGITPtr](#getgitptr)|Genel arabirim Işaretçisini döndürür.|
|[CAtlModule:: GetLockCount](#getlockcount)|Kilit sayısını döndürür.|
|[CAtlModule:: Lock](#lock)|Kilit sayısını artırır.|
|[CAtlModule:: Term](#term)|Tüm veri üyelerini yayınlar.|
|[CAtlModule:: unlock](#unlock)|Kilit sayısını azaltır.|
|[CAtlModule:: UpdateRegistryFromResourceD](#updateregistryfromresourced)|Bir nesneyi kaydetmek veya kaydını silmek için belirtilen bir kaynakta bulunan betiği çalıştırır.|
|[CAtlModule:: UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Bu yöntem, kayıt defteri `UpdateRegistryFromResourceD` güncelleştirmesini gerçekleştirmek için tarafından çağırılır.|
|[CAtlModule:: UpdateRegistryFromResourceS](#updateregistryfromresources)|Bir nesneyi kaydetmek veya kaydını silmek için belirtilen bir kaynakta bulunan betiği çalıştırır. Bu yöntem, ATL kayıt defteri bileşenine statik olarak bağlantı sağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAtlModule:: m_libid](#m_libid)|Geçerli modülün GUID 'sini içerir.|
|[CAtlModule:: m_pGIT](#m_pgit)|Genel arabirim tablosuna yönelik işaretçi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, sırasıyla DLL uygulamaları, EXE uygulamaları ve Windows Hizmetleri için destek sağlamak üzere [Catldllmodület sınıfı](../../atl/reference/catldllmodulet-class.md), [catlexemodület sınıfı](../../atl/reference/catlexemodulet-class.md)ve [CAtlServiceModuleT sınıfı](../../atl/reference/catlservicemodulet-class.md) tarafından kullanılır.

ATL 'deki modüller hakkında daha fazla bilgi için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md).

Bu sınıf, ATL 'nin önceki sürümlerinde kullanılan eski [CComModule sınıfının](../../atl/reference/ccommodule-class.md) yerini alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

`CAtlModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="catlmoduleaddcommonrgsreplacements"></a><a name="addcommonrgsreplacements"></a>CAtlModule:: Addcommonrgsdeğiştirmeler

ATL kayıt defteri bileşeni (kaydedici) değiştirme eşlemesine parametreler eklemek için bu yöntemi geçersiz kılın.

```cpp
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```

### <a name="parameters"></a>Parametreler

*pRegistrar*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Değiştirilebilen parametreler, bir kaydedici istemcisinin çalışma zamanı verilerini belirtmesini sağlar. Bunu yapmak için, kaydedici, betiğinizdeki değiştirilebilen parametrelerle ilişkili değerleri girdiği bir değiştirme haritası sağlar. Kaydedici bu girişleri çalışma zamanında yapar.

Daha fazla ayrıntı için [değiştirilebilen parametreleri (kayıt sahibinin ön işlemcisi) kullanma](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) konusuna bakın.

## <a name="catlmoduleaddtermfunc"></a><a name="addtermfunc"></a>CAtlModule:: AddTermFunc

Modül sonlandırıldığında çağrılacak yeni bir işlev ekler.

```cpp
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```

### <a name="parameters"></a>Parametreler

*pFunc*<br/>
Eklenecek işlevin işaretçisi.

*DW*<br/>
İşleve geçirilen kullanıcı tanımlı veriler.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catlmodulecatlmodule"></a><a name="catlmodule"></a>CAtlModule:: CAtlModule

Oluşturucu.

```cpp
CAtlModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Veri üyelerini başlatır ve modülün iş parçacığı etrafında kritik bir bölüm başlatır.

## <a name="catlmodulecatlmodule"></a><a name="dtor"></a>CAtlModule:: ~ CAtlModule

Yok edicisi.

```cpp
~CAtlModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini yayınlar.

## <a name="catlmodulegetgitptr"></a><a name="getgitptr"></a>CAtlModule:: GetGITPtr

Genel arabirim tablosuna bir işaretçi alır.

```cpp
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```

### <a name="parameters"></a>Parametreler

*ppGIT*<br/>
Genel arabirim tablosuna yönelik işaretçiyi alacak değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hatada hata kodu döndürür. *Ppgit* , null değerine eşitse E_POINTER döndürülür.

### <a name="remarks"></a>Açıklamalar

Genel arabirim tablosu nesnesi yoksa, oluşturulur ve adresi [CAtlModule:: m_pGIT](#m_pgit)üye değişkeninde depolanır.

Hata ayıklama yapılarında, *PPGIT* null değerine eşitse ya da genel arabirim tablosu işaretçisi alınamıyorsa bir onaylama hatası meydana gelir.

Genel arabirim tablosu hakkında bilgi için bkz. [IGlobalInterfaceTable](/windows/win32/api/objidl/nn-objidl-iglobalinterfacetable) .

## <a name="catlmodulegetlockcount"></a><a name="getlockcount"></a>CAtlModule:: GetLockCount

Kilit sayısını döndürür.

```cpp
virtual LONG GetLockCount() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit sayısını döndürür. Bu değer tanılama ve hata ayıklama için yararlı olabilir.

## <a name="catlmodulelock"></a><a name="lock"></a>CAtlModule:: Lock

Kilit sayısını artırır.

```cpp
virtual LONG Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit sayısını artırır ve güncelleştirilmiş değeri döndürür. Bu değer tanılama ve hata ayıklama için yararlı olabilir.

## <a name="catlmodulem_libid"></a><a name="m_libid"></a>CAtlModule:: m_libid

Geçerli modülün GUID 'sini içerir.

```cpp
static GUID m_libid;
```

## <a name="catlmodulem_pgit"></a><a name="m_pgit"></a>CAtlModule:: m_pGIT

Genel arabirim tablosuna yönelik işaretçi.

```cpp
IGlobalInterfaceTable* m_pGIT;
```

## <a name="catlmoduleterm"></a><a name="term"></a>CAtlModule:: Term

Tüm veri üyelerini yayınlar.

```cpp
void Term() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini yayınlar. Bu yöntem yıkıcı tarafından çağırılır.

## <a name="catlmoduleunlock"></a><a name="unlock"></a>CAtlModule:: unlock

Kilit sayısını azaltır.

```cpp
virtual LONG Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit sayısını azaltır ve güncelleştirilmiş değeri döndürür. Bu değer tanılama ve hata ayıklama için yararlı olabilir.

## <a name="catlmoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CAtlModule:: UpdateRegistryFromResourceD

Bir nesneyi kaydetmek veya kaydını silmek için belirtilen bir kaynakta bulunan betiği çalıştırır.

```cpp
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
Bir kaynak adı.

*Nresd*<br/>
Kaynak KIMLIĞI.

*bRegister*<br/>
Nesnenin kaydedilmesi gerekiyorsa doğru; Aksi takdirde FALSE.

*pMapEntries*<br/>
Değiştirme eşlemesi için, betikle değiştirilebilen parametrelerle ilişkili değerleri depolayan bir işaretçi. ATL otomatik olarak% MODULE% kullanır. Ek değiştirilebilen parametreleri kullanmak için bkz. [CAtlModule:: Addcommonrgsdeğiştirmeleri](#addcommonrgsreplacements). Aksi takdirde, NULL varsayılan değerini kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

*LpszRes veya Nresd*tarafından belirtilen kaynakta bulunan betiği çalıştırır. *BRegister* true ise, bu yöntem nesneyi sistem kayıt defterine kaydeder; Aksi takdirde, nesneyi kayıt defterinden kaldırır.

ATL kayıt defteri bileşeni (kaydedici) statik olarak bağlamak için bkz. [CAtlModule:: UpdateRegistryFromResourceS](#updateregistryfromresources).

Bu yöntem, [CAtlModule:: UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) ve [ıkaydedic:: ResourceUnregister](iregistrar-class.md#resourceunregister)öğesini çağırır.

## <a name="catlmoduleupdateregistryfromresourcedhelper"></a><a name="updateregistryfromresourcedhelper"></a>CAtlModule:: UpdateRegistryFromResourceDHelper

Bu yöntem, kayıt defteri `UpdateRegistryFromResourceD` güncelleştirmesini gerçekleştirmek için tarafından çağırılır.

```cpp
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*lpszRes*<br/>
Bir kaynak adı.

*bRegister*<br/>
Nesnenin kaydedilip edilmeyeceğini belirtir.

*pMapEntries*<br/>
Değiştirme eşlemesi için, betikle değiştirilebilen parametrelerle ilişkili değerleri depolayan bir işaretçi. ATL otomatik olarak% MODULE% kullanır. Ek değiştirilebilen parametreleri kullanmak için bkz. [CAtlModule:: Addcommonrgsdeğiştirmeleri](#addcommonrgsreplacements). Aksi takdirde, NULL varsayılan değerini kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CAtlModule:: UpdateRegistryFromResourceD](#updateregistryfromresourced)uygulamasını sağlar.

## <a name="catlmoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CAtlModule:: UpdateRegistryFromResourceS

Bir nesneyi kaydetmek veya kaydını silmek için belirtilen bir kaynakta bulunan betiği çalıştırır. Bu yöntem, ATL kayıt defteri bileşenine statik olarak bağlantı sağlar.

```cpp
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

*Nresd*<br/>
Kaynak KIMLIĞI.

*lpszRes*<br/>
Bir kaynak adı.

*bRegister*<br/>
Kaynak betiğin kaydedilip edilmeyeceğini belirtir.

*pMapEntries*<br/>
Değiştirme eşlemesi için, betikle değiştirilebilen parametrelerle ilişkili değerleri depolayan bir işaretçi. ATL otomatik olarak% MODULE% kullanır. Ek değiştirilebilen parametreleri kullanmak için bkz. [CAtlModule:: Addcommonrgsdeğiştirmeleri](#addcommonrgsreplacements). Aksi takdirde, NULL varsayılan değerini kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlModule:: UpdateRegistryFromResourceD](#updateregistryfromresourced) ' ye benzer `CAtlModule::UpdateRegistryFromResourceS` şekilde, atl kayıt defteri bileşeni (kaydedici) için statik bir bağlantı oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_MODULE](atl-typedefs.md#_atl_module)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)<br/>
[Kayıt defteri bileşeni (kaydedici)](../../atl/atl-registry-component-registrar.md)
