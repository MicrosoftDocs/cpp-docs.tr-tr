---
title: Icollectiononstlımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl::get__NewEnum
- ATLCOM/ATL::ICollectionOnSTLImpl::getcount
- ATLCOM/ATL::ICollectionOnSTLImpl::get_Item
- ATLCOM/ATL::ICollectionOnSTLImpl::m_coll
dev_langs:
- C++
helpviewer_keywords:
- ICollectionOnSTLImpl class
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2b70e7332c5f0a24af80ddb5cfd14a8ecf146de
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025158"
---
# <a name="icollectiononstlimpl-class"></a>Icollectiononstlımpl sınıfı

Bu sınıf, bir koleksiyon sınıfı tarafından kullanılan yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
COM koleksiyon arabirimi.

*CollType*<br/>
Bir C++ Standart Kitaplığı kapsayıcı sınıfı.

*Itemtype*<br/>
Kapsayıcı arabirimi tarafından sunulan öğe türü.

*CopyItem*<br/>
A [kopyalama İlkesi sınıfı](../../atl/atl-copy-policy-classes.md).

*EnumType*<br/>
A [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)-uyumlu Numaralandırıcı sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ICollectionOnSTLImpl::get__NewEnum](#newenum)|Koleksiyon için bir numaralandırıcı nesnesi döndürür.|
|[ICollectionOnSTLImpl::getcount](#get_count)|Koleksiyondaki öğe sayısını döndürür.|
|[ICollectionOnSTLImpl::get_Item](#get_item)|İstenen öğe koleksiyonundan döndürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[ICollectionOnSTLImpl::m_coll](#m_coll)|Koleksiyonu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf bir koleksiyon arabirimi için üç yöntem uygulamasını sağlar: [getcount](#get_count), [get_Item](#get_item), ve [get__NewEnum](#newenum).

Bu sınıf kullanmak için:

- Uygulamak istediğiniz bir koleksiyonu arabirimi tanımlayın (veya ödünç alın).

- Sınıfınıza özelleştirmesi türetilen `ICollectionOnSTLImpl` Bu koleksiyonu arabirimi esas alan.

- Türetilmiş sınıfınızın herhangi bir yöntem tarafından işlenmemiş koleksiyon arabiriminden uygulamak için kullanma `ICollectionOnSTLImpl`.

> [!NOTE]
>  Çift arabirim koleksiyon arabirimi ise, sınıfından türetilir [Idispatchımpl](../../atl/reference/idispatchimpl-class.md), geçen `ICollectionOnSTLImpl` uygulamasını sağlamak üzere ATL isterseniz ilk şablon parametresi olarak özelleştirmesi `IDispatch` yöntemleri.

- Öğe ekleme [m_coll](#m_coll) koleksiyonu doldurmak için üye.

Daha fazla bilgi ve örnekler için bkz. [ATL koleksiyonları ve numaralandırıcıları](../../atl/atl-collections-and-enumerators.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="get_count"></a>  ICollectionOnSTLImpl::getcount

Bu yöntem, koleksiyondaki öğe sayısını döndürür.

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>Parametreler

*pcount*<br/>
[out] Koleksiyondaki öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="get_item"></a>  ICollectionOnSTLImpl::get_Item

Bu yöntem, koleksiyondan belirtilen öğeyi döndürür.

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>Parametreler

*Index*<br/>
[in] Koleksiyondaki bir öğe 1 tabanlı dizini.

*pvar*<br/>
[out] Öğesi için karşılık gelen *dizin*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Öğe, belirtilen konumda verileri kopyalayarak elde edilen [m_coll](#m_coll) kopyalama yöntemini kullanarak [kopyalama İlkesi sınıfı](../../atl/atl-copy-policy-classes.md) bir şablon bağımsız değişken olarak geçirilen `ICollectionOnSTLImpl` özelleştirmesi.

##  <a name="newenum"></a>  ICollectionOnSTLImpl::get__NewEnum

Koleksiyon için bir numaralandırıcı nesnesi döndürür.

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>Parametreler

*ppUnk*<br/>
[out] **IUnknown** yeni oluşturulan Numaralandırıcı nesnesi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Yeni oluşturulan Numaralandırıcı bir yineleyicinin özgün koleksiyonunda tutar `m_coll`, (bir kopya yapılmadı şekilde) ve bekleyen numaralandırıcılar varken, koleksiyon Canlı kalmasını sağlamak için koleksiyon nesnesinde bir COM başvurusu içerir.

##  <a name="m_coll"></a>  ICollectionOnSTLImpl::m_coll

Bu üye, koleksiyon tarafından temsil edilen öğeleri içerir.

```
CollType m_coll;
```

## <a name="see-also"></a>Ayrıca Bkz.

[ATLCollections örnek](../../visual-cpp-samples.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
