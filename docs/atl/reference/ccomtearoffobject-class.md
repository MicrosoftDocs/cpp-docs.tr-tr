---
title: CComTearOffObject sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
ms.openlocfilehash: 3eee1d33d5eded75d8805584a24e6b6f396a8369
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833627"
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject sınıfı

Bu sınıf bir tear arabirimi uygular.

## <a name="syntax"></a>Söz dizimi

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
' Dan türetilmiş, `CComTearOffObjectBase` ve yırt nesnenizin olmasını istediğiniz arabirimlerden türeten kapalı sınıfınız.

ATL, kendi çıkarma arabirimlerini iki aşamada uygular — `CComTearOffObjectBase` Yöntemler başvuru sayısını işler, `QueryInterface` ancak `CComTearOffObject` [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)uygular.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComTearOffObject:: CComTearOffObject](#ccomtearoffobject)|Oluşturucu.|
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComTearOffObject:: AddRef](#addref)|Bir nesne için başvuru sayısını artırır `CComTearOffObject` .|
|[CComTearOffObject:: QueryInterface](#queryinterface)|Ayırma sınıfınız veya Owner sınıfında istenen arabirime yönelik bir işaretçi döndürür.|
|[CComTearOffObject:: Release](#release)|Bir nesnenin başvuru sayısını azaltır `CComTearOffObject` ve yok eder.|

### <a name="ccomtearoffobjectbase-methods"></a>CComTearOffObjectBase yöntemleri

|İşlev|Açıklama|
|-|-|
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Oluşturucu.|

### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase veri üyeleri

|Veri üyesi|Açıklama|
|-|-|
|[m_pOwner](#m_powner)|`CComObject`Sahip sınıfından türetilmiş bir işaretçisi.|

## <a name="remarks"></a>Açıklamalar

`CComTearOffObject` yalnızca bu arabirim için sorgulandığında oluşturulan ayrı bir nesne olarak bir ayırıcı arabirim uygular. Başvuru sayısı sıfır olduğunda, tear silinir. Genellikle, bir tear kullanılması, ana nesnenizin tüm örneklerinde bir vtable işaretçisi kaydettiğinde, nadiren kullanılan bir arabirim için bir yırma arabirimi oluşturursunuz.

Bu sınıfın, `CComTearOffObjectBase` yırtan kapatma nesnesinin desteklemesini istediğiniz arabirimlerden ve bunlardan herhangi bir olanını uygulayan sınıfını türetebilirsiniz. `CComTearOffObjectBase` , sahip sınıfı ve iş parçacığı modelinde şablonsaldır. Owner sınıfı, bir tear 'nin uygulandığı nesnenin sınıfıdır. Bir iş parçacığı modeli belirtmezseniz, varsayılan iş parçacığı modeli kullanılır.

Yırma sınıfınız için bir COM Haritası oluşturmalısınız. ATL, tear 'yi örneklendiriken, `CComTearOffObject<CYourTearOffClass>` veya oluşturur `CComCachedTearOffObject<CYourTearOffClass>` .

Örneğin, BEEPER örneğinde, sınıfı, tear sınıfıdır `CBeeper2` ve `CBeeper` sınıf Owner sınıfıdır:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComTearOffObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomtearoffobjectaddref"></a><a name="addref"></a> CComTearOffObject:: AddRef

Nesnenin başvuru sayısını `CComTearOffObject` bir artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="ccomtearoffobject"></a> CComTearOffObject:: CComTearOffObject

Oluşturucu.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki Bir nesnenin işaretçisine dönüştürülecek işaretçi `CComObject<Owner>` .

### <a name="remarks"></a>Açıklamalar

Sahibin başvuru sayısını bir artırır.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="dtor"></a> CComTearOffObject:: ~ CComTearOffObject

Yok edicisi.

```
~CComTearOffObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır, sonlandırmayı çağırır ve modül kilit sayısını azaltır.

## <a name="ccomtearoffobjectccomtearoffobjectbase"></a><a name="ccomtearoffobjectbase"></a> CComTearOffObject:: CComTearOffObjectBase

Oluşturucu.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Açıklamalar

[M_pOwner](#m_powner) üyesini null olarak başlatır.

## <a name="ccomtearoffobjectm_powner"></a><a name="m_powner"></a> CComTearOffObject:: m_pOwner

*Sahibinden*türetilmiş bir [CComObject](../../atl/reference/ccomobject-class.md) nesnesine yönelik bir işaretçi.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>Parametreler

*Sahibi*<br/>
'ndaki Bir yırma uygulanan sınıf.

### <a name="remarks"></a>Açıklamalar

İşaretçi oluşturma sırasında NULL olarak başlatılır.

## <a name="ccomtearoffobjectqueryinterface"></a><a name="queryinterface"></a> CComTearOffObject:: QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İstenen arabirimin IID 'si.

*ppvObject*<br/>
dışı Arabirim bulunmazsa, *IID*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi veya ARABIRIM bulunamazsa null.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

İlk olarak, ayırma sınıflarınızdaki arabirimler için sorgular. Arabirim orada değilse, sahip nesnesi üzerindeki arabirim için sorgular. İstenen arabirim ise, `IUnknown` sahibinin ' i döndürür `IUnknown` .

## <a name="ccomtearoffobjectrelease"></a><a name="release"></a> CComTearOffObject:: Release

Başvuru sayısını bir sayı azaltır ve başvuru sayısı sıfır ise, öğesini siler `CComTearOffObject` .

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama olmayan derlemelerde, her zaman sıfır döndürür. Hata ayıklama yapılarında, tanılama veya test için yararlı olabilecek bir değer döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComCachedTearOffObject sınıfı](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
