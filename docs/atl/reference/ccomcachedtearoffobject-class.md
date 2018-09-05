---
title: CComCachedTearOffObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a6835cb1f8fb6365149b91c30881b4966b4b644
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765664"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject sınıfı

Bu sınıfın uyguladığı [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) bölünmüş arabirim.

## <a name="syntax"></a>Sözdizimi

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parametreler

`contained`  
Bölünmüş sınıfınızı türetilen `CComTearOffObjectBase` ve desteklemek için etkinleştiriliyorken nesneyi istediğiniz arabirimleri.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|Oluşturucu.|
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject::AddRef](#addref)|İçin başvuru sayısını artırır bir `CComCachedTearOffObject` nesne.|
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|Çağrıları `m_contained::FinalConstruct` (etkinleştiriliyorken sınıfının yöntemi).|
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|Çağrıları `m_contained::FinalRelease` (etkinleştiriliyorken sınıfının yöntemi).|
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Bir işaretçi döndürür `IUnknown` , `CComCachedTearOffObject` nesnesi veya etkinleştiriliyorken sınıfınıza istenen Arabirimi'ne (sınıfı `contained`).|
|[CComCachedTearOffObject::Release](#release)|Başvuru sayısı için azaltır bir `CComCachedTearOffObject` nesne ve başvuru sayısının 0 olması durumunda yok eder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject::m_contained](#m_contained)|A `CComContainedObject` , bölünmüş sınıftan türetilmiş bir nesneye (sınıfı `contained`).|

## <a name="remarks"></a>Açıklamalar

`CComCachedTearOffObject` uygulayan [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) bölünmüş arabirim. Bu sınıf farklıdır `CComTearOffObject` bakımından `CComCachedTearOffObject` kendi `IUnknown`sahibi nesnenin ayrı `IUnknown` (sahibi için etkinleştiriliyorken oluşturulmakta olan nesnesidir). `CComCachedTearOffObject` kendi tutar başvuru sayısı, `IUnknown` ve, başvuru sayısı sıfır olduğunda kendisini siler. Ancak, herhangi bir alt etkinleştiriliyorken sorgularsanız arabirimleri, sahibi nesnenin başvuru sayısını `IUnknown` artırılacaktır.

Varsa `CComCachedTearOffObject` bölünmüş uygulama zaten oluşturulana ve etkinleştiriliyorken arabirimi yeniden aynı sorgulanan nesne `CComCachedTearOffObject` nesne yeniden kullanılabilir. Bölünmüş arabirim tarafından uygulanırsa, buna karşılık, bir `CComTearOffObject` yeniden için sahip nesne, sorgulanan başka bir `CComTearOffObject` örneği oluşturulur.

Sahibi sınıf uygulamalıdır `FinalRelease` ve çağrı `Release` önbelleğe alınan üzerinde `IUnknown` için `CComCachedTearOffObject`, hangi başvuru sayımına azaltma. Bu neden olacak `CComCachedTearOffObject`'s `FinalRelease` çağrılabilir ve etkinleştiriliyorken silin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="addref"></a>  CComCachedTearOffObject::AddRef

Başvuru sayısını artırır `CComCachedTearOffObject` 1 nesne.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı ve test olabilir bir değer.

##  <a name="ccomcachedtearoffobject"></a>  CComCachedTearOffObject::CComCachedTearOffObject

Oluşturucu.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*  
[in] İşaretçi `IUnknown` , `CComCachedTearOffObject`.

### <a name="remarks"></a>Açıklamalar

Başlatır `CComContainedObject` üyesi [m_contained](#m_contained).

##  <a name="dtor"></a>  CComCachedTearOffObject:: ~ CComCachedTearOffObject

Yıkıcı.

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları ve aramalar boşaltır [FinalRelease](#finalrelease).

##  <a name="finalconstruct"></a>  CComCachedTearOffObject::FinalConstruct

Çağrıları `m_contained::FinalConstruct` oluşturmak için `m_contained`, `CComContainedObject` <  `contained`> etkinleştiriliyorken sınıfınıza tarafından uygulanan arabirimi erişmek için kullanılan nesne.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="finalrelease"></a>  CComCachedTearOffObject::FinalRelease

Çağrıları `m_contained::FinalRelease` ücretsiz `m_contained`, `CComContainedObject` <  `contained`> nesne.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComCachedTearOffObject::m_contained

A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) , bölünmüş sınıftan türetilmiş bir nesneye.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*yer alan*  
[in] Bölünmüş sınıfınızı türetilen `CComTearOffObjectBase` ve desteklemek için etkinleştiriliyorken nesneyi istediğiniz arabirimleri.

### <a name="remarks"></a>Açıklamalar

Yöntemleri `m_contained` devralan etkinleştiriliyorken sınıfınıza etkinleştiriliyorken arabiriminde önbelleğe alınmış etkinleştiriliyorken nesnenin erişmek için kullanılan `QueryInterface`, `FinalConstruct`, ve `FinalRelease`.

##  <a name="queryinterface"></a>  CComCachedTearOffObject::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*IID*  
[in] İstenen arabiriminin GUID'si.

*ppvObject*  
[out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *IID*, veya arabirim bulunamazsa NULL.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

İstenen arabirimi ise `IUnknown`, bir işaretçi döndürür `CComCachedTearOffObject`kişinin kendi `IUnknown` ve başvuru sayısını artırır. Aksi takdirde, arabirimin etkinleştiriliyorken sınıfı kullanarak sorgular [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) yöntemi öğesinden devralınan `CComObjectRootEx`.  

##  <a name="release"></a>  CComCachedTearOffObject::Release

Başvuru sayısı 1 ile azaltır ve başvuru sayısının 0 olması durumunda siler `CComCachedTearOffObject` nesne.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama olmayan yapılarında, her zaman 0 değerini döndürür. Hata ayıklama yapılarında, tanılama için kullanışlı veya test olabilecek bir değer döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CComTearOffObject sınıfı](../../atl/reference/ccomtearoffobject-class.md)   
[CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
