---
title: CAtlModule sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88c8ee576af3c50317b86b7016ac198fefdcbaa9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093447"
---
# <a name="catlmodule-class"></a>CAtlModule sınıfı

Bu sınıf, birkaç ATL modül sınıfları tarafından kullanılan yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlModule::CAtlModule](#catlmodule)|Oluşturucu.|
|[CAtlModule:: ~ CAtlModule](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|ATL kayıt defteri bileşeni (Kaydedici) değiştirme eşlemeye parametreleri eklemek için bu yöntemi yok sayın.|
|[CAtlModule::AddTermFunc](#addtermfunc)|Modül sonlandırıldığında çağrılacak yeni bir işlev ekler.|
|[CAtlModule::GetGITPtr](#getgitptr)|Genel arabirim işaretçisini döndürür.|
|[CAtlModule::GetLockCount](#getlockcount)|Kilit sayacını döndürür.|
|[CAtlModule::Lock](#lock)|Kilit sayacını artırır.|
|[CAtlModule::Term](#term)|Tüm veri üyeleri serbest bırakır.|
|[CAtlModule::Unlock](#unlock)|Kilit sayısını azaltır.|
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Belirtilen kaynak kaydetmek veya kaydını bir nesne için yer alan komut dosyasını çalıştırır.|
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Bu yöntemi çağıran `UpdateRegistryFromResourceD` kayıt defterini güncelleştirme gerçekleştirmek için.|
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Belirtilen kaynak kaydetmek veya kaydını bir nesne için yer alan komut dosyasını çalıştırır. Bu yöntem, ATL kayıt defteri bileşeni için statik olarak bağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlModule::m_libid](#m_libid)|Geçerli modül GUID içerir.|
|[CAtlModule::m_pGIT](#m_pgit)|Genel arabirim tablosu işaretçisi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından kullanılan [CAtlDllModuleT sınıfı](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT sınıfı](../../atl/reference/catlexemodulet-class.md), ve [CAtlServiceModuleT sınıfı](../../atl/reference/catlservicemodulet-class.md) uygulamaları EXE, DLL uygulamaları için destek sağlamak ve Windows, sırasıyla Hizmetleri.

ATL modüller hakkında daha fazla bilgi için bkz. [ATL modül sınıfları](../../atl/atl-module-classes.md).

Bu sınıf artık kullanılmıyor değiştirir [CComModule sınıfı](../../atl/reference/ccommodule-class.md) ATL önceki sürümlerinde kullanılan

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_MODULE](atl-typedefs.md#_atl_module)

`CAtlModule`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="addcommonrgsreplacements"></a>  CAtlModule::AddCommonRGSReplacements

ATL kayıt defteri bileşeni (Kaydedici) değiştirme eşlemeye parametreleri eklemek için bu yöntemi yok sayın.

```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```

### <a name="parameters"></a>Parametreler

*pRegistrar*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Değiştirilebilir parametreler, çalışma zamanı verileri belirtmek bir kayıt şirketinin istemci izin verin. Bunu yapmak için kayıt şirketi, betiğiniz içine değiştirilebilir parametreler ile ilişkili değerler girer değiştirme harita tutar. Kayıt şirketi, çalışma zamanında bu girişleri hale getirir.

Konusuna [değiştirilebilir parametreler kullanma (kaydedicinin ön işlemcisi)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) daha fazla ayrıntı için.

##  <a name="addtermfunc"></a>  CAtlModule::AddTermFunc

Modül sonlandırıldığında çağrılacak yeni bir işlev ekler.

```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```

### <a name="parameters"></a>Parametreler

*pFunc*<br/>
İşlev eklemek için işaretçi.

*dw*<br/>
Kullanıcı tanımlı veri, işleve geçirilen.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="catlmodule"></a>  CAtlModule::CAtlModule

Oluşturucu.

```
CAtlModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Veri üyeleri başlatır ve kritik bölüm modülün iş parçacığı etrafında başlatır.

##  <a name="dtor"></a>  CAtlModule:: ~ CAtlModule

Yıkıcı.

```
~CAtlModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyeleri serbest bırakır.

##  <a name="getgitptr"></a>  CAtlModule::GetGITPtr

Genel arabirim tablosu için bir işaretçi alır.

```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```

### <a name="parameters"></a>Parametreler

*ppGIT*<br/>
Genel arabirim tablosu işaretçisi alacak bir değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya bir hata kodu döndürür. E_poınter ise döndürülür *ppGIT* NULL değerine eşittir.

### <a name="remarks"></a>Açıklamalar

Genel arabirim tablosu nesne yok, oluşturulduktan ve adresini üye değişkeninde depolanıyorsa [CAtlModule::m_pGIT](#m_pgit).

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *ppGIT* NULL olarak eşit olan veya genel arabirim tablosu işaretçisi elde edilemiyor.

Bkz: [IGlobalInterfaceTable](/windows/desktop/api/objidl/nn-objidl-iglobalinterfacetable) genel arabirim tablosu hakkında bilgi için.

##  <a name="getlockcount"></a>  CAtlModule::GetLockCount

Kilit sayacını döndürür.

```
virtual LONG GetLockCount() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit sayacını döndürür. Bu değer, tanılama için kullanışlı ve hata ayıklama olabilir.

##  <a name="lock"></a>  CAtlModule::Lock

Kilit sayacını artırır.

```
virtual LONG Lock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit sayacını artırır ve güncelleştirilmiş değeri döndürür. Bu değer, tanılama için kullanışlı ve hata ayıklama olabilir.

##  <a name="m_libid"></a>  CAtlModule::m_libid

Geçerli modül GUID içerir.

```
static GUID m_libid;
```

##  <a name="m_pgit"></a>  CAtlModule::m_pGIT

Genel arabirim tablosu işaretçisi.

```
IGlobalInterfaceTable* m_pGIT;
```

##  <a name="term"></a>  CAtlModule::Term

Tüm veri üyeleri serbest bırakır.

```
void Term() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyeleri serbest bırakır. Bu yöntem tarafından yok Edicisi çağrılır.

##  <a name="unlock"></a>  CAtlModule::Unlock

Kilit sayısını azaltır.

```
virtual LONG Unlock() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit sayısını azaltır ve güncelleştirilmiş değeri döndürür. Bu değer, tanılama için kullanışlı ve hata ayıklama olabilir.

##  <a name="updateregistryfromresourced"></a>  CAtlModule::UpdateRegistryFromResourceD

Belirtilen kaynak kaydetmek veya kaydını bir nesne için yer alan komut dosyasını çalıştırır.

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
Bir kaynak adı.

*nResID*<br/>
Bir kaynak kimliği

*bRegister*<br/>
Nesne kayıtlı olması gerekiyorsa TRUE; FALSE Aksi takdirde.

*pMapEntries*<br/>
Betiğin değiştirilebilir parametreler ile ilişkili değerleri depolamayı değiştirme eşlemesi için bir işaretçi. ATL MODÜL % otomatik olarak kullanır. Ek değiştirilebilir parametreler kullanmak için bkz: [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Aksi takdirde, NULL varsayılan değeri kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Tarafından belirtilen kaynak yer alan komut dosyasını çalıştırır *lpszRes veya nResID*. Varsa *bRegister* doğru ise, bu yöntem nesnenin sistem kayıt defterine kaydeder; Aksi takdirde nesneyi kayıt defterinden kaldırır.

ATL kayıt defteri bileşeni (Kaydedici) statik olarak bağlamak için bkz [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).

Bu yöntemin çağırdığı [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) ve [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).

##  <a name="updateregistryfromresourcedhelper"></a>  CAtlModule::UpdateRegistryFromResourceDHelper

Bu yöntemi çağıran `UpdateRegistryFromResourceD` kayıt defterini güncelleştirme gerçekleştirmek için.

```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*lpszRes*<br/>
Bir kaynak adı.

*bRegister*<br/>
Nesne kayıtlı olup olmadığını gösterir.

*pMapEntries*<br/>
Betiğin değiştirilebilir parametreler ile ilişkili değerleri depolamayı değiştirme eşlemesi için bir işaretçi. ATL MODÜL % otomatik olarak kullanır. Ek değiştirilebilir parametreler kullanmak için bkz: [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Aksi takdirde, NULL varsayılan değeri kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem uygulamasını sağlar [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).

##  <a name="updateregistryfromresources"></a>  CAtlModule::UpdateRegistryFromResourceS

Belirtilen kaynak kaydetmek veya kaydını bir nesne için yer alan komut dosyasını çalıştırır. Bu yöntem, ATL kayıt defteri bileşeni için statik olarak bağlar.

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
Bir kaynak kimliği

*lpszRes*<br/>
Bir kaynak adı.

*bRegister*<br/>
Kaynak betiği kayıtlı olup olmadığını gösterir.

*pMapEntries*<br/>
Betiğin değiştirilebilir parametreler ile ilişkili değerleri depolamayı değiştirme eşlemesi için bir işaretçi. ATL MODÜL % otomatik olarak kullanır. Ek değiştirilebilir parametreler kullanmak için bkz: [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Aksi takdirde, NULL varsayılan değeri kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Benzer şekilde [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) dışında `CAtlModule::UpdateRegistryFromResourceS` ATL kayıt defteri bileşeni (Kaydedici) statik bir bağlantı oluşturur.

## <a name="see-also"></a>Ayrıca Bkz.

[_ATL_MODULE](atl-typedefs.md#_atl_module)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)<br/>
[Kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md)  
