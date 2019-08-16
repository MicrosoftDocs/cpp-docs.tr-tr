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
ms.openlocfilehash: 0d27a6fa3c0070cd32c78971a7544327c51d4393
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496910"
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject sınıfı

Bu sınıf bir tear arabirimi uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
' Dan türetilmiş, ve yırt nesnenizin `CComTearOffObjectBase` olmasını istediğiniz arabirimlerden türeten kapalı sınıfınız.

ATL, kendi çıkarma arabirimlerini iki `CComTearOffObjectBase` aşamada uygular — Yöntemler başvuru `QueryInterface`sayısını işler, ancak `CComTearOffObject` [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)uygular.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComTearOffObject:: CComTearOffObject](#ccomtearoffobject)|Oluşturucu.|
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComTearOffObject:: AddRef](#addref)|Bir `CComTearOffObject` nesne için başvuru sayısını artırır.|
|[CComTearOffObject:: QueryInterface](#queryinterface)|Ayırma sınıfınız veya Owner sınıfında istenen arabirime yönelik bir işaretçi döndürür.|
|[CComTearOffObject:: Release](#release)|Bir `CComTearOffObject` nesnenin başvuru sayısını azaltır ve yok eder.|

### <a name="ccomtearoffobjectbase-methods"></a>CComTearOffObjectBase yöntemleri

|||
|-|-|
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Oluşturucu.|

### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase veri üyeleri

|||
|-|-|
|[m_pOwner](#m_powner)|Sahip sınıfından türetilmiş bir `CComObject` işaretçisi.|

## <a name="remarks"></a>Açıklamalar

`CComTearOffObject`yalnızca bu arabirim için sorgulandığında oluşturulan ayrı bir nesne olarak bir ayırıcı arabirim uygular. Başvuru sayısı sıfır olduğunda, tear silinir. Genellikle, bir tear kullanılması, ana nesnenizin tüm örneklerinde bir vtable işaretçisi kaydettiğinde, nadiren kullanılan bir arabirim için bir yırma arabirimi oluşturursunuz.

Bu sınıfın, yırtan `CComTearOffObjectBase` kapatma nesnesinin desteklemesini istediğiniz arabirimlerden ve bunlardan herhangi bir olanını uygulayan sınıfını türetebilirsiniz. `CComTearOffObjectBase`, sahip sınıfı ve iş parçacığı modelinde şablonsaldır. Owner sınıfı, bir tear 'nin uygulandığı nesnenin sınıfıdır. Bir iş parçacığı modeli belirtmezseniz, varsayılan iş parçacığı modeli kullanılır.

Yırma sınıfınız için bir COM Haritası oluşturmalısınız. ATL, tear 'yi örneklendiriken, veya `CComTearOffObject<CYourTearOffClass>` `CComCachedTearOffObject<CYourTearOffClass>`oluşturur.

Örneğin, BEEPER örneğinde, `CBeeper2` sınıfı, tear sınıfıdır `CBeeper` ve sınıf Owner sınıfıdır:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComTearOffObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="addref"></a>CComTearOffObject:: AddRef

`CComTearOffObject` Nesnenin başvuru sayısını bir artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

##  <a name="ccomtearoffobject"></a>CComTearOffObject:: CComTearOffObject

Oluşturucu.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki Bir `CComObject<Owner>` nesnenin işaretçisine dönüştürülecek işaretçi.

### <a name="remarks"></a>Açıklamalar

Sahibin başvuru sayısını bir artırır.

##  <a name="dtor"></a>CComTearOffObject:: ~ CComTearOffObject

Yok edicisi.

```
~CComTearOffObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır, sonlandırmayı çağırır ve modül kilit sayısını azaltır.

##  <a name="ccomtearoffobjectbase"></a>CComTearOffObject:: CComTearOffObjectBase

Oluşturucu.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Açıklamalar

[M_pOwner](#m_powner) üyesini null olarak başlatır.

##  <a name="m_powner"></a>CComTearOffObject:: m_pOwner

*Sahibinden*türetilmiş bir [CComObject](../../atl/reference/ccomobject-class.md) nesnesine yönelik bir işaretçi.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>Parametreler

*İnde*<br/>
'ndaki Bir yırma uygulanan sınıf.

### <a name="remarks"></a>Açıklamalar

İşaretçi oluşturma sırasında NULL olarak başlatılır.

##  <a name="queryinterface"></a>CComTearOffObject:: QueryInterface

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

İlk olarak, ayırma sınıflarınızdaki arabirimler için sorgular. Arabirim orada değilse, sahip nesnesi üzerindeki arabirim için sorgular. İstenen arabirim ise `IUnknown`, sahibinin ' i `IUnknown` döndürür.

##  <a name="release"></a>CComTearOffObject:: Release

Başvuru sayısını bir sayı azaltır ve başvuru sayısı sıfır ise, `CComTearOffObject`öğesini siler.

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama olmayan derlemelerde, her zaman sıfır döndürür. Hata ayıklama yapılarında, tanılama veya test için yararlı olabilecek bir değer döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComCachedTearOffObject Sınıfı](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
