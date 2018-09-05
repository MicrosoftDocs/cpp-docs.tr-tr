---
title: CComTearOffObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
dev_langs:
- C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3814dacff2861bf78800adb8a019b696ce2756b7
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752768"
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject sınıfı

Bu sınıf, bir etiket arabirimini uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>Parametreler

*temel*  
Bölünmüş sınıfınızı türetilen `CComTearOffObjectBase` ve desteklemek için etkinleştiriliyorken nesneyi istediğiniz arabirimleri.

ATL iki aşamada etkinleştiriliyorken arabirimlerini uygular — `CComTearOffObjectBase` yöntemleri işleyen başvuru sayısı ve `QueryInterface`, ancak `CComTearOffObject` uygulayan [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown).

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|Oluşturucu.|
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComTearOffObject::AddRef](#addref)|İçin başvuru sayısını artırır bir `CComTearOffObject` nesne.|
|[CComTearOffObject::QueryInterface](#queryinterface)|Bir işaretçi için istenen arabirim etkinleştiriliyorken sınıfınızın veya sahip sınıf döndürür.|
|[CComTearOffObject::Release](#release)|Başvuru sayısı için azaltır bir `CComTearOffObject` nesne ve yok eder.|

### <a name="ccomtearoffobjectbase-methods"></a>CComTearOffObjectBase yöntemleri

|||
|-|-|
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Oluşturucu.|

### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase veri üyesi

|||
|-|-|
|[m_pOwner](#m_powner)|Bir işaretçi bir `CComObject` sahibi sınıfından türetilen.|

## <a name="remarks"></a>Açıklamalar

`CComTearOffObject` Bu arabirim için sorgulandığında örneği ayrı bir nesne olarak bölünmüş arabirim uygular. Başvuru sayısı sıfır olduğunda etkinleştiriliyorken silinir. Genellikle, bir bölünmüş arabirimi kullanarak bir bölünmüş bir vtable işaretçi ana nesneyi tüm örnekleri kaydeder olduğundan, nadiren kullanılır bir arabirim için oluşturun.

Bölünmüş gelen uygulayan bir sınıfa türetilmelidir `CComTearOffObjectBase` ve desteklemek için etkinleştiriliyorken nesneyi istediğiniz hangi arabirimleri. `CComTearOffObjectBase` sahibi sınıfı ve iş parçacığı modeline şablonlaştırılmış. Kendisi için bir bölünmüş uygulanan nesnenin sınıfını sahibi sınıftır. Bir iş parçacığı modeli belirtmezseniz varsayılan iş parçacığı modeli kullanılır.

Bölünmüş sınıfınız için bir COM eşlemesi oluşturmanız gerekir. ATL etkinleştiriliyorken başlattığında oluşturacağı `CComTearOffObject<CYourTearOffClass>` veya `CComCachedTearOffObject<CYourTearOffClass>`.

Örneğin, sesli İKAZ örnekteki `CBeeper2` etkinleştiriliyorken sınıfı ve `CBeeper` sahibi sınıfı:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComTearOffObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="addref"></a>  CComTearOffObject::AddRef

Başvuru sayısını artırır `CComTearOffObject` bir nesne.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı ve test olabilir bir değer.

##  <a name="ccomtearoffobject"></a>  CComTearOffObject::CComTearOffObject

Oluşturucu.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*  
[in] Bir işaretçiye dönüştürülür işaretçi bir `CComObject<Owner>` nesne.

### <a name="remarks"></a>Açıklamalar

Sahibin başvuru sayısını bire artırır.

##  <a name="dtor"></a>  CComTearOffObject:: ~ CComTearOffObject

Yıkıcı.

```
~CComTearOffObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakan, modül FinalRelease ve azaltır çağırır kilit sayısı.

##  <a name="ccomtearoffobjectbase"></a>  CComTearOffObject::CComTearOffObjectBase

Oluşturucu.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Açıklamalar

Başlatır [m_pOwner](#m_powner) üyesi null.

##  <a name="m_powner"></a>  CComTearOffObject::m_pOwner

Bir işaretçi bir [CComObject](../../atl/reference/ccomobject-class.md) sınıfından türetilen nesne *sahibi*.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>Parametreler

*Sahibi*  
[in] Kendisi için bir bölünmüş uygulanan sınıfı.

### <a name="remarks"></a>Açıklamalar

İşaretçiyi, oluşturma sırasında NULL olarak başlatılır.

##  <a name="queryinterface"></a>  CComTearOffObject::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*IID*  
[in] İstenen arabirim Laboratuvardaki.

*ppvObject*  
[out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *IID*, veya arabirim bulunamazsa NULL.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

İlk etkinleştiriliyorken sınıfınızın arabirimleri için sorgular. Arabirimi, sorgular için sahip nesne arabirimi yoksa. İstenen arabirimi ise `IUnknown`, döndürür `IUnknown` sahibinin.

##  <a name="release"></a>  CComTearOffObject::Release

Başvuru sayısını bir azaltır ve başvuru sayısı sıfır ise siler `CComTearOffObject`.

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama olmayan yapılarında, her zaman sıfır döndürür. Hata ayıklama yapılarında, tanılama için kullanışlı veya test olabilecek bir değer döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CComCachedTearOffObject sınıfı](../../atl/reference/ccomcachedtearoffobject-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
