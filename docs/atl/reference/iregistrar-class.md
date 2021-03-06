---
description: 'Daha fazla bilgi edinin: Ikaydedicim arabirimi'
title: Ikaydedici arabirimi
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
ms.openlocfilehash: 9a138468ccbf21594c4e9d88d1ed2387a4c1052a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139171"
---
# <a name="iregistrar-interface"></a>Ikaydedici arabirimi

Bu arabirim, atlıface. h içinde tanımlanmıştır ve [UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced)gibi CAtlModule üye işlevleri tarafından dahili olarak kullanılır.

## <a name="syntax"></a>Syntax

```
typedef interface IRegistrar IRegistrar;
```

## <a name="remarks"></a>Açıklamalar

Daha fazla ayrıntı için [değiştirilebilen parametreleri (kayıt sahibinin ön işlemcisi) kullanma](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) konusuna bakın.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ikaydedici:: ResourceRegisterSz](#resourceregistersz)|Kaynağı kaydeder. |
|[Ikaydedici:: ResourceUnregisterSz](#resourceunregistersz)| Kaynağın kaydını siler.|
|[Ikaydedicikaydedicisi:: FileRegister](#fileregister)|Dosyayı kaydeder.|
|[Ikaydedici:: FileUnregister](#fileunregister)|Dosyanın kaydını siler.|
|[Ikaydedici:: StringRegister](#stringregister)|Dizeyi kaydeder.|
|[Ikaydedici:: StringUnregister](#stringunregister)|Dizenin kaydını siler|
|[Ikaydedicce:: ResourceRegister](#resourceregister)|Kaynağı kaydeder.|
|[Ikaydedici:: ResourceUnregister](#resourceunregister)|Kaynağın kaydını siler.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlifao. h

## <a name="iregistrarresourceregistersz"></a><a name="resourceregistersz"></a> Ikaydedici:: ResourceRegisterSz

Kaynağı kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregistersz"></a><a name="resourceunregistersz"></a> Ikaydedici:: ResourceUnregisterSz

Kaynağın kaydını siler.

```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarfileregister"></a><a name="fileregister"></a> Ikaydedicikaydedicisi:: FileRegister

Dosyayı kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE FileRegister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarfileunregister"></a><a name="fileunregister"></a> Ikaydedici:: FileUnregister

Dosyanın kaydını siler.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarstringregister"></a><a name="stringregister"></a> Ikaydedici:: StringRegister

Belirtilen dize verilerini kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE StringRegister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarstringunregister"></a><a name="stringunregister"></a> Ikaydedici:: StringUnregister

Belirtilen dize verilerinin kaydını siler.

```
virtualHRESULT STDMETHODCALLTYPE StringUnregister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarresourceregister"></a><a name="resourceregister"></a> Ikaydedicce:: ResourceRegister

Kaynağı kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregister"></a><a name="resourceunregister"></a> Ikaydedici:: ResourceUnregister

Kaynağın kaydını siler.

```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="see-also"></a>Ayrıca bkz.

[Değiştirilebilen parametreleri kullanma (kaydedici 'nin ön Işlemcisi)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)<br/>
[Kayıt defteri bileşeni (kaydedici)](../../atl/atl-registry-component-registrar.md)
