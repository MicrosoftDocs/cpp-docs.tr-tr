---
title: CComObjectGlobal Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
ms.openlocfilehash: 9a784584179186cdf1e63c1ec43cad4d59391ec3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327632"
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal Sınıfı

Bu sınıf, nesnenizi `Base` içeren modülde bir başvuru sayısını yönetir.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComObjectGlobal : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
CComObjectRoot veya [CComObjectRootEx'ten](../../atl/reference/ccomobjectrootex-class.md)türetilen sınıfınızın yanı sıra nesne üzerinde desteklemek istediğiniz diğer arabirimlerden de. [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Ccomobjectglobal::ccomobjectglobal](#ccomobjectglobal)|Oluşturucu.|
|[Ccomobjectglobal::~ccomobjectglobal](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Ccomobjectglobal::Addref](#addref)|Genel `AddRef`bir uygular.|
|[CcomObjectGlobal::QueryInterface](#queryinterface)|Genel `QueryInterface`bir uygular.|
|[CcomObjectGlobal::Sürüm](#release)|Genel `Release`bir uygular.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|Nesnenin yapımı sırasında döndürülen `CComObjectGlobal` HRESULT'ı içerir.|

## <a name="remarks"></a>Açıklamalar

`CComObjectGlobal`nesnenizi `Base` içeren modülde bir başvuru sayısını yönetir. `CComObjectGlobal`modül serbest bırakılmadığı sürece nesnenizin silinmemesini sağlar. Nesneniz yalnızca tüm modüldeki başvuru sayısı sıfıra düştüğünde kaldırılır.

Örneğin, bir `CComObjectGlobal`sınıf fabrikasını kullanarak, tüm istemcileri tarafından paylaşılan ortak bir genel nesne tutabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObjectGlobal`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomobjectglobaladdref"></a><a name="addref"></a>Ccomobjectglobal::Addref

Nesnenin başvuru sayısını 1 ile karşılar.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

Varsayılan `AddRef` olarak, `_Module::Lock` `_Module` [ccommodule](../../atl/reference/ccommodule-class.md) veya ondan türetilen bir sınıfın genel örneği nerede çağırır.

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="ccomobjectglobal"></a>Ccomobjectglobal::ccomobjectglobal

Oluşturucu. Aramalar `FinalConstruct` ve [m_hResFinalConstruct](#m_hresfinalconstruct) daha sonra `HRESULT` tarafından `FinalConstruct`döndürülen m_hResFinalConstruct ayarlar.

```
CComObjectGlobal(void* = NULL));
```

### <a name="remarks"></a>Açıklamalar

Taban sınıfınızı [CComObjectRoot'dan](../../atl/reference/ccomobjectroot-class.md)türemediyseniz, kendi `FinalConstruct` yönteminizi sağlamanız gerekir. Yıkıcı arıyor. `FinalRelease`

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="dtor"></a>Ccomobjectglobal::~ccomobjectglobal

Yıkıcı.

```
CComObjectGlobal();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları boşaltıyor ve [FinalRelease'i](ccomobjectrootex-class.md#finalrelease)çağırıyor.

## <a name="ccomobjectglobalm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a>CComObjectGlobal::m_hResFinalConstruct

Nesnenin yapımı sırasında `FinalConstruct` çağıran HRESULT içerir. `CComObjectGlobal`

```
HRESULT m_hResFinalConstruct;
```

## <a name="ccomobjectglobalqueryinterface"></a><a name="queryinterface"></a>CcomObjectGlobal::QueryInterface

İstenen arabirim işaretçisi için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] İstenmekte olan arabirimin GUID'i.

*ppvNesne*<br/>
[çıkış] Arabirim bulunamazsa iid veya NULL tarafından tanımlanan arabirim işaretçisine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`QueryInterface`yalnızca COM harita tablosundaki arabirimleri işler.

## <a name="ccomobjectglobalrelease"></a><a name="release"></a>CcomObjectGlobal::Sürüm

Nesnenin başvuru sayısını 1 olarak erteler.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama oluştururda, `Release` tanılama ve sınama için yararlı olabilecek bir değer verir. Hata ayıklama yapılarında `Release` her zaman 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan `Release` olarak, `_Module::Unlock` `_Module` [ccommodule](../../atl/reference/ccommodule-class.md) veya ondan türetilen bir sınıfın genel örneği nerede çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[CComObjectStack Sınıfı](../../atl/reference/ccomobjectstack-class.md)<br/>
[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
