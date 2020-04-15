---
title: ICollectionOnSTLImpl Sınıfı
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
ms.openlocfilehash: a8ccab08b89da8c1b8ef56c8932e27a6c74e62aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329901"
---
# <a name="icollectiononstlimpl-class"></a>ICollectionOnSTLImpl Sınıfı

Bu sınıf, bir koleksiyon sınıfı tarafından kullanılan yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Com toplama arabirimi.

*CollType*<br/>
C++ Standart Kitaplık kapsayıcı sınıfı.

*ItemType*<br/>
Kapsayıcı arabirimi tarafından açığa çıkarılan öğe türü.

*CopyItem*<br/>
Bir [kopya ilkesi sınıfı.](../../atl/atl-copy-policy-classes.md)

*Enumtype*<br/>
[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)uyumlu bir enumerator sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[ICollectionOnSTLImpl::get__NewEnum](#newenum)|Koleksiyon için bir sayısallaştırıcı nesne döndürür.|
|[ICollectionOnSTLImpl::getcount](#get_count)|Koleksiyondaki öğe sayısını verir.|
|[ICollectionOnSTLImpl::get_Item](#get_item)|Koleksiyondan istenen öğeyi döndürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[ICollectionOnSTLImpl::m_coll](#m_coll)|Koleksiyon.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf bir koleksiyon arabiriminin üç yöntemi için uygulama sağlar: [getcount](#get_count), [get_Item](#get_item)ve [get__NewEnum.](#newenum)

Bu sınıfı kullanmak için:

- Uygulamak istediğiniz bir koleksiyon arabirimini tanımlayın (veya ödünç alın).

- Sınıfınızı bu koleksiyon arabirimine `ICollectionOnSTLImpl` dayalı bir uzmanlıktan türetin.

- Türemiş sınıfınızı, '' tarafından işlenmemiş `ICollectionOnSTLImpl`koleksiyon arabiriminden herhangi bir yöntem uygulamak için kullanın.

> [!NOTE]
> Koleksiyon arabirimi çift arabirim ise, sınıfınızı [IDispatchImpl'den](../../atl/reference/idispatchimpl-class.md)türetin, atl'nin `ICollectionOnSTLImpl` `IDispatch` yöntemlerin uygulanmasını sağlamasını istiyorsanız ilk şablon parametresi olarak uzmanlık tan geçirin.

- Koleksiyonu doldurmak için [m_coll](#m_coll) üyeye öğeler ekleyin.

Daha fazla bilgi ve örnekler için [ATL Koleksiyonları ve Sayısallaştırıcılar'a](../../atl/atl-collections-and-enumerators.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="icollectiononstlimplgetcount"></a><a name="get_count"></a>ICollectionOnSTLImpl::getcount

Bu yöntem, koleksiyondaki madde sayısını döndürür.

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>Parametreler

*pcount*<br/>
[çıkış] Koleksiyondaki öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="icollectiononstlimplget_item"></a><a name="get_item"></a>ICollectionOnSTLImpl::get_Item

Bu yöntem, koleksiyondan belirtilen öğeyi döndürür.

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>Parametreler

*Dizin oluşturma*<br/>
[içinde] Koleksiyondaki bir öğenin 1 tabanlı dizini.

*pvar*<br/>
[çıkış] *Dizin'e*karşılık gelen öğe.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Madde, `ICollectionOnSTLImpl` uzmanlık alanında şablon bağımsız değişkeni olarak geçirilen [kopya ilkesi sınıfının](../../atl/atl-copy-policy-classes.md) kopyalama yöntemi kullanılarak [m_coll](#m_coll) belirtilen konumdaki veriler kopyalayarak elde edilir.

## <a name="icollectiononstlimplget__newenum"></a><a name="newenum"></a>ICollectionOnSTLImpl::get__NewEnum

Koleksiyon için bir sayısallaştırıcı nesne döndürür.

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>Parametreler

*ppUnk*<br/>
[çıkış] Yeni oluşturulan bir numaralandırma nesnesinin **Bilinmeyen** işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yeni oluşturulan enumerator orijinal koleksiyonda bir yineleyici `m_coll`tutar, (bu yüzden hiçbir kopya yapılır) ve olağanüstü noumerators varken koleksiyonun canlı kalmasını sağlamak için koleksiyon nesnesi üzerinde bir COM referans tutar.

## <a name="icollectiononstlimplm_coll"></a><a name="m_coll"></a>ICollectionOnSTLImpl::m_coll

Bu üye, koleksiyon tarafından temsil edilen öğeleri tutar.

```
CollType m_coll;
```

## <a name="see-also"></a>Ayrıca bkz.

[ATLCollections Örnek](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
