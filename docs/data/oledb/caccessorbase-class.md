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
ms.openlocfilehash: 81b0ecd8ded7acb0c0e376d0869decb2bfcb590e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509123"
---
# <a name="caccessorbase-class"></a>CAccessorBase Sınıfı

OLE DB şablonlarındaki tüm erişimciler bu sınıftan türetilir. `CAccessorBase` bir satır kümesinin birden çok erişimciyi yönetmesine izin verir. Ayrıca, hem parametreler hem de çıkış sütunları için bağlama sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
// Replace with syntax
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|--|--|
| [Kapat](#close) | Erişimcileri kapatır. |
| [GetHAccessor](#geth) | Erişimci tanıtıcısını alır. |
| [GetNumAccessors](#getnum) | Sınıfı tarafından oluşturulan erişimcilerinin sayısını alır. |
| [IsAutoAccessor](#isauto) | Belirtilen erişimcinin bir oto erişimcisi olup olmadığını sınar. |
| [Releaseerişimcileri](#release) | Erişimcileri yayınlar. |

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="caccessorbaseclose"></a><a name="close"></a> CAccessorBase:: Close

Erişimcileri kapatır.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Önce [Releaseerişimcileri](#release) 'i çağırmanız gerekir.

## <a name="caccessorbasegethaccessor"></a><a name="geth"></a> CAccessorBase:: GetHAccessor

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

## <a name="caccessorbasegetnumaccessors"></a><a name="getnum"></a> CAccessorBase:: GetNumAccessors

Sınıfı tarafından oluşturulan erişimcilerinin sayısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
ULONG GetNumAccessors() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sınıfı tarafından oluşturulan erişimcilerinin sayısı.

## <a name="caccessorbaseisautoaccessor"></a><a name="isauto"></a> CAccessorBase:: ısoto erişimcisi

Taşıma işlemi sırasında erişimci için veriler otomatik olarak alınırsa true döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsAutoAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>Parametreler

*nAccessor*<br/>
'ndaki Erişimcinin sıfır-fark numarası.

### <a name="return-value"></a>Dönüş Değeri

**`true`** Erişimci bir oto erişimcisi ise döndürür. Aksi takdirde, döndürür **`false`** .

## <a name="caccessorbasereleaseaccessors"></a><a name="release"></a> CAccessorBase:: Releaseerişimcileri

Sınıfı tarafından oluşturulan erişimcileri yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);
```

#### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki `IUnknown` Erişimcilerinin OLUŞTURULDUĞU com nesnesi için bir arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

[CAccessorRowset:: Close](./caccessorrowset-class.md#close)öğesinden çağırılır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessorBase sınıfı](../../data/oledb/caccessorbase-class.md)
