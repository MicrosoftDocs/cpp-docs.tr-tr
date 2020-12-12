---
description: 'Şu konuda daha fazla bilgi edinin: ıollectiononstlımpl sınıfı'
title: Iollectiononstlımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl::get__NewEnum
- ATLCOM/ATL::ICollectionOnSTLImpl::getcount
- ATLCOM/ATL::ICollectionOnSTLImpl::get_Item
- ATLCOM/ATL::ICollectionOnSTLImpl::m_coll
helpviewer_keywords:
- ICollectionOnSTLImpl class
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
ms.openlocfilehash: 089fc0fbd8f410d740646e2a653b076d32448647
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139613"
---
# <a name="icollectiononstlimpl-class"></a>Iollectiononstlımpl sınıfı

Bu sınıf, bir koleksiyon sınıfı tarafından kullanılan yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Bir COM koleksiyon arabirimi.

*CollType*<br/>
C++ standart kitaplığı kapsayıcı sınıfı.

*ItemType*<br/>
Kapsayıcı arabirimi tarafından kullanıma sunulan öğenin türü.

*CopyItem*<br/>
Bir [kopyalama ilkesi sınıfı](../../atl/atl-copy-policy-classes.md).

*EnumType*<br/>
[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)uyumlu Numaralandırıcı sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Iollectiononstlımpl:: get__NewEnum](#newenum)|Koleksiyon için bir Numaralandırıcı nesnesi döndürür.|
|[Iollectiononstlımpl:: GetCount](#get_count)|Koleksiyondaki öğe sayısını döndürür.|
|[Iollectiononstlımpl:: get_Item](#get_item)|Koleksiyondan istenen öğeyi döndürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Iollectiononstlımpl:: m_coll](#m_coll)|Koleksiyon.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir koleksiyon arabiriminin üç yöntemi için uygulama sağlar: [GetCount](#get_count), [get_Item](#get_item)ve [get__NewEnum](#newenum).

Bu sınıfı kullanmak için:

- Uygulamak istediğiniz bir koleksiyon arabirimini tanımlayın (veya ödünç vermek).

- Sınıfınızı `ICollectionOnSTLImpl` Bu koleksiyon arabirimine göre özelleşten türetebilirsiniz.

- Tarafından işlenmeyen koleksiyon arabiriminden herhangi bir yöntemi uygulamak için türetilmiş sınıfınızı kullanın `ICollectionOnSTLImpl` .

> [!NOTE]
> Koleksiyon arabirimi çift bir arabirim ise, ATL 'nin [](../../atl/reference/idispatchimpl-class.md) `ICollectionOnSTLImpl` yöntemlerin uygulanmasını sağlaması için, ATL 'yi ilk şablon parametresi olarak geçirerek, IDispatchImpl 'den sınıfınızı türetirsiniz `IDispatch` .

- Koleksiyonu doldurmak için [m_coll](#m_coll) üyesine öğe ekleyin.

Daha fazla bilgi ve örnek için bkz. [atl koleksiyonları ve Numaralandırıcılar](../../atl/atl-collections-and-enumerators.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="icollectiononstlimplgetcount"></a><a name="get_count"></a> Iollectiononstlımpl:: GetCount

Bu yöntem koleksiyondaki öğe sayısını döndürür.

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>Parametreler

*pcount*<br/>
dışı Koleksiyondaki öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="icollectiononstlimplget_item"></a><a name="get_item"></a> Iollectiononstlımpl:: get_Item

Bu yöntem, koleksiyondan belirtilen öğeyi döndürür.

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>Parametreler

*Dizin oluşturma*<br/>
'ndaki Koleksiyondaki bir öğenin 1 tabanlı dizini.

*pvar*<br/>
dışı *Dizine* karşılık gelen öğe.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Öğe, özelleşmenin bir şablon bağımsız değişkeni olarak geçirilmiş [kopyalama ilkesi sınıfının](../../atl/atl-copy-policy-classes.md) Copy yöntemi kullanılarak [m_coll](#m_coll) belirtilen konumdaki veriler kopyalanarak elde edilir `ICollectionOnSTLImpl` .

## <a name="icollectiononstlimplget__newenum"></a><a name="newenum"></a> Iollectiononstlımpl:: get__NewEnum

Koleksiyon için bir Numaralandırıcı nesnesi döndürür.

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>Parametreler

*ppUnk*<br/>
dışı Yeni oluşturulan bir Numaralandırıcı nesnesinin **IUnknown** işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yeni oluşturulan Numaralandırıcı orijinal koleksiyonda bir yineleyici tutar, `m_coll` (yani hiçbir kopya yapılmaz) ve bekleyen Numaralandırıcılar varken koleksiyonun etkin kalmasını sağlamak için koleksiyon nesnesinde BIR com başvurusu tutar.

## <a name="icollectiononstlimplm_coll"></a><a name="m_coll"></a> Iollectiononstlımpl:: m_coll

Bu üye, koleksiyon tarafından temsil edilen öğeleri barındırır.

```
CollType m_coll;
```

## <a name="see-also"></a>Ayrıca bkz.

[ATLCollections örneği](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
