---
title: IRegistrar Arabirimi
ms.date: 02/01/2017
f1_keywords:
- IRegistrar
- ATLIFASE/ATL::IRegistrar
- ATLIFASE/ATL::IRegistrar::ResourceRegisterSz
- ATLIFASE/ATL::IRegistrar::ResourceUnregisterSz
- ATLIFASE/ATL::IRegistrar::FileRegister
- ATLIFASE/ATL::IRegistrar::FileUnregister
- ATLIFASE/ATL::IRegistrar::StringRegister
- ATLIFASE/ATL::IRegistrar::StringUnregister
- ATLIFASE/ATL::IRegistrar::ResourceRegister
- ATLIFASE/ATL::IRegistrar::ResourceUnregister
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
ms.openlocfilehash: 98943fe294322715723bd91207a6f3320ca1ffb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329460"
---
# <a name="iregistrar-interface"></a>IRegistrar Arabirimi

Bu arabirim atliface.h'de tanımlanır ve [UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced)gibi CAtlModule üye işlevleri tarafından dahili olarak kullanılır.

## <a name="syntax"></a>Sözdizimi

```
typedef interface IRegistrar IRegistrar;
```

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Değiştirilebilir Parametreleri (Kayıt Şirketi Ön İşlemci) kullanarak](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) konuya bakın.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|Kaynağı kaydeder. |
|[IRegistrar::ResourceUnregisterSz](#resourceunregistersz)| Kaynağın kaydını silinir.|
|[IRegistrar::FileRegister](#fileregister)|Dosyayı kaydeder.|
|[IRegistrar::FileUnregister](#fileunregister)|Dosyayı açar.|
|[IRegistrar::StringRegister](#stringregister)|Dize yi kaydeder.|
|[IRegistrar::StringUnregister](#stringunregister)|Dizeyi unregisters|
|[IRegistrar::ResourceRegister](#resourceregister)|Kaynağı kaydeder.|
|[IRegistrar::ResourceUnRegister](#resourceunregister)|Kaynağın kaydını silinir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlifase.h

## <a name="iregistrarresourceregistersz"></a><a name="resourceregistersz"></a>IRegistrar::ResourceRegisterSz

Kaynağı kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregistersz"></a><a name="resourceunregistersz"></a>IRegistrar::ResourceUnregisterSz

Kaynağın kaydını silinir.

```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarfileregister"></a><a name="fileregister"></a>IRegistrar::FileRegister

Dosyayı kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE FileRegister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarfileunregister"></a><a name="fileunregister"></a>IRegistrar::FileUnregister

Dosyayı açar.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarstringregister"></a><a name="stringregister"></a>IRegistrar::StringRegister

Belirtilen dize verilerini kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE StringRegister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarstringunregister"></a><a name="stringunregister"></a>IRegistrar::StringUnregister

Belirtilen dize verilerini kaydeder.

```
virtualHRESULT STDMETHODCALLTYPE StringUnregister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarresourceregister"></a><a name="resourceregister"></a>IRegistrar::ResourceRegister

Kaynağı kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregister"></a><a name="resourceunregister"></a>IRegistrar::ResourceUnRegister

Kaynağın kaydını silinir.

```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="see-also"></a>Ayrıca bkz.

[Değiştirilebilir Parametreleri Kullanma (Kayıt Sahibinin Ön İşlemcisi)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Modül Sınıfları](../../atl/atl-module-classes.md)<br/>
[Kayıt Bileşeni (Registrar)](../../atl/atl-registry-component-registrar.md)
