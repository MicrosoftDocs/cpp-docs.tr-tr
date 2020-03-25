---
title: CAccessorBase Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAccessorBase
- CAccessorBase.Close
- CAccessorBase::Close
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
- CAccessorBase::GetNumAccessors
- GetNumAccessors
- CAccessorBase.GetNumAccessors
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
- CAccessorBase::ReleaseAccessors
- CAccessorBase.ReleaseAccessors
- ReleaseAccessors
helpviewer_keywords:
- CAccessorBase class
- Close method
- GetHAccessor method
- GetNumAccessors method
- IsAutoAccessor method
- ReleaseAccessors method
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
ms.openlocfilehash: 8aef8a04d7adff903e21491a91014d55aab769da
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212298"
---
# <a name="caccessorbase-class"></a>CAccessorBase Sınıfı

OLE DB şablonlarındaki tüm erişimciler bu sınıftan türetilir. `CAccessorBase`, bir satır kümesinin birden çok erişimciyi yönetmesine izin verir. Ayrıca, hem parametreler hem de çıkış sütunları için bağlama sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
// Replace with syntax
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[~Eksik](#close)|Erişimcileri kapatır.|
|[GetHAccessor](#geth)|Erişimci tanıtıcısını alır.|
|[GetNumAccessors](#getnum)|Sınıfı tarafından oluşturulan erişimcilerinin sayısını alır.|
|[IsAutoAccessor](#isauto)|Belirtilen erişimcinin bir oto erişimcisi olup olmadığını sınar.|
|[Releaseerişimcileri](#release)|Erişimcileri yayınlar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="caccessorbaseclose"></a><a name="close"></a>CAccessorBase:: Close

Erişimcileri kapatır.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Önce [Releaseerişimcileri](../../data/oledb/caccessorbase-releaseaccessors.md) 'i çağırmanız gerekir.

## <a name="caccessorbasegethaccessor"></a><a name="geth"></a>CAccessorBase:: GetHAccessor

Belirtilen erişimcinin erişimci tanıtıcısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HACCESSOR GetHAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>Parametreler

*nAccessor*<br/>
'ndaki Erişimcinin sıfır-fark numarası.

### <a name="return-value"></a>Dönüş Değeri

Erişimci tanıtıcısı.

## <a name="caccessorbasegetnumaccessors"></a><a name="getnum"></a>CAccessorBase:: GetNumAccessors

Sınıfı tarafından oluşturulan erişimcilerinin sayısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
ULONG GetNumAccessors() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sınıfı tarafından oluşturulan erişimcilerinin sayısı.

## <a name="caccessorbaseisautoaccessor"></a><a name="isauto"></a>CAccessorBase:: ısoto erişimcisi

Taşıma işlemi sırasında erişimci için veriler otomatik olarak alınırsa true döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsAutoAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>Parametreler

*nAccessor*<br/>
'ndaki Erişimcinin sıfır-fark numarası.

### <a name="return-value"></a>Dönüş Değeri

Erişimci bir oto erişimcisi ise, **true** döndürür. Aksi takdirde, **false**döndürür.

## <a name="caccessorbasereleaseaccessors"></a><a name="release"></a>CAccessorBase:: Releaseerişimcileri

Sınıfı tarafından oluşturulan erişimcileri yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);
```

#### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki Erişimcilerinin oluşturulduğu COM nesnesi için `IUnknown` arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

[CAccessorRowset:: Close](../../data/oledb/caccessorrowset-close.md)öğesinden çağırılır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessorBase Sınıfı](../../data/oledb/caccessorbase-class.md)
