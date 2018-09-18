---
title: CComObjectGlobal sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 141940ef5d5c7d23ea3cf049e64e9f4c6974fce0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076664"
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal sınıfı

Bu sınıf modül bulunduğu bir başvuru sayısını yönetir, `Base` nesne.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComObjectGlobal : public Base
```

#### <a name="parameters"></a>Parametreler

*temel*<br/>
Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)iyi herhangi diğer bir arabirim uğradıysa nesnede desteklemek istediğiniz gibi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|Oluşturucu.|
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectGlobal::AddRef](#addref)|Genel bir uygulayan `AddRef`.|
|[CComObjectGlobal::QueryInterface](#queryinterface)|Genel bir uygulayan `QueryInterface`.|
|[CComObjectGlobal::Release](#release)|Genel bir uygulayan `Release`.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|Oluşumu sırasında döndürülen HRESULT içeren `CComObjectGlobal` nesne.|

## <a name="remarks"></a>Açıklamalar

`CComObjectGlobal` içeren modül üzerinde bir başvuru sayısını yönetir, `Base` nesne. `CComObjectGlobal` Modül serbest bırakılmaz sürece, nesne silinmeyecek sağlar. Tüm modül başvuru sayısı sıfıra gittiğinde nesnenizin yalnızca kaldırılacak.

Örneğin, kullanarak `CComObjectGlobal`, bir sınıf üreteci, tüm istemciler tarafından paylaşılan ortak bir genel nesne içerebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObjectGlobal`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="addref"></a>  CComObjectGlobal::AddRef

Nesnenin başvuru sayısının 1 artar.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı ve test olabilir bir değer.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `AddRef` çağrıları `_Module::Lock`burada `_Module` genel örneğinin [CComModule](../../atl/reference/ccommodule-class.md) veya ondan türetilmiş bir sınıf.

##  <a name="ccomobjectglobal"></a>  CComObjectGlobal::CComObjectGlobal

Oluşturucu. Çağrıları `FinalConstruct` ve ardından ayarlar [m_hResFinalConstruct](#m_hresfinalconstruct) için `HRESULT` tarafından döndürülen `FinalConstruct`.

```
CComObjectGlobal(void* = NULL));
```

### <a name="remarks"></a>Açıklamalar

Varsa, temel sınıftan türetilmemiş [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), kendi sağlamalısınız `FinalConstruct` yöntemi. Yıkıcı çağrıları `FinalRelease`.

##  <a name="dtor"></a>  CComObjectGlobal:: ~ CComObjectGlobal

Yıkıcı.

```
CComObjectGlobal();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları ve aramalar boşaltır [FinalRelease](ccomobjectrootex-class.md#finalrelease).

##  <a name="m_hresfinalconstruct"></a>  CComObjectGlobal::m_hResFinalConstruct

Arama HRESULT içeren `FinalConstruct` yapımı sırasında `CComObjectGlobal` nesne.

```
HRESULT m_hResFinalConstruct;
```

##  <a name="queryinterface"></a>  CComObjectGlobal::QueryInterface

İstenen arabirim işaretçisi için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*IID*<br/>
[in] İstenen arabiriminin GUID'si.

*ppvObject*<br/>
[out] IID veya NULL arabirimi bulunamazsa, belirtilen arabirim işaretçisini bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

`QueryInterface` yalnızca COM eşleme tablosunda arabirimleri işler.

##  <a name="release"></a>  CComObjectGlobal::Release

Başvuru tarafından 1 nesne sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında `Release` tanılama için kullanışlı ve test olabilecek bir değer döndürür. Hata ayıklama olmayan yapılarında `Release` her zaman 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `Release` çağrıları `_Module::Unlock`burada `_Module` genel örneğinin [CComModule](../../atl/reference/ccommodule-class.md) veya ondan türetilmiş bir sınıf.

## <a name="see-also"></a>Ayrıca Bkz.

[CComObjectStack Sınıfı](../../atl/reference/ccomobjectstack-class.md)<br/>
[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
