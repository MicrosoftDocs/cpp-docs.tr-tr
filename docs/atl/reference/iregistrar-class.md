---
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
ms.openlocfilehash: e347bdba1656a53cd705123a26650dad50d3892f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417616"
---
# <a name="iregistrar-interface"></a>Ikaydedici arabirimi

Bu arabirim, atlıface. h içinde tanımlanmıştır ve [UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced)gibi CAtlModule üye işlevleri tarafından dahili olarak kullanılır.

## <a name="syntax"></a>Sözdizimi

```
typedef interface IRegistrar IRegistrar;
```

## <a name="remarks"></a>Açıklamalar

Daha fazla ayrıntı için [değiştirilebilen parametreleri (kayıt sahibinin ön işlemcisi) kullanma](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) konusuna bakın.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
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

##  <a name="resourceregistersz"></a>Ikaydedici:: ResourceRegisterSz

Kaynağı kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

##  <a name="resourceunregistersz"></a>Ikaydedici:: ResourceUnregisterSz

Kaynağın kaydını siler.

```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

##  <a name="fileregister"></a>Ikaydedicikaydedicisi:: FileRegister

Dosyayı kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE FileRegister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

##  <a name="fileunregister"></a>Ikaydedici:: FileUnregister

Dosyanın kaydını siler.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

##  <a name="stringregister"></a>Ikaydedici:: StringRegister

Belirtilen dize verilerini kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE StringRegister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

##  <a name="stringunregister"></a>Ikaydedici:: StringUnregister

Belirtilen dize verilerinin kaydını siler.

```
virtualHRESULT STDMETHODCALLTYPE StringUnregister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

##  <a name="resourceregister"></a>Ikaydedicce:: ResourceRegister

Kaynağı kaydeder.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

##  <a name="resourceunregister"></a>Ikaydedici:: ResourceUnregister

Kaynağın kaydını siler.

```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="see-also"></a>Ayrıca bkz.

[Değiştirilebilir Parametreler Kullanma (Kaydedicinin Ön İşlemcisi)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)<br/>
[Kayıt defteri bileşeni (kaydedici)](../../atl/atl-registry-component-registrar.md)
