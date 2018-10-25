---
title: CAccessorBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAccessorBase class
- Close method
- GetHAccessor method
- GetNumAccessors method
- IsAutoAccessor method
- ReleaseAccessors method
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2e62c4242513c5147dcfd84ee5d69ec51a4816d1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053337"
---
# <a name="caccessorbase-class"></a>CAccessorBase Sınıfı

OLE DB Şablonları tüm erişenler sınıfından türetilir. `CAccessorBase` Çoklu Erişimci yönetmek bir satır kümesi sağlar. Ayrıca parametreleri ve çıkış sütunları için bağlama sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
// Replace with syntax
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Kapat](#close)|Erişimciler kapatır.|
|[GetHAccessor](#geth)|Erişimci tanıtıcısı alır.|
|[GetNumAccessors](#getnum)|Sınıfı tarafından oluşturulan erişimcileri sayısını alır.|
|[Isautoaccessor](#isauto)|Belirtilen erişimci erişimcinin olup olmadığını sınar.|
|[ReleaseAccessors](#release)|Erişimciler serbest bırakır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="close"></a> CAccessorBase::Close

Erişimciler kapatır.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız [ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md) ilk.

## <a name="geth"></a> CAccessorBase::GetHAccessor

Belirtilen bir erişimci erişimci tanıtıcısı alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HACCESSOR GetHAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>Parametreler

*nAccessor*<br/>
[in] Erişimci sıfır uzaklığı numarası.

### <a name="return-value"></a>Dönüş Değeri

Erişimci tanıtıcısı.

## <a name="getnum"></a> CAccessorBase::GetNumAccessors

Sınıfı tarafından oluşturulan erişimcileri sayısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
ULONG GetNumAccessors() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sınıfı tarafından oluşturulan erişimcileri sayısı.

## <a name="isauto"></a> CAccessorBase::ısautoaccessor

Veri taşıma işlemi sırasında otomatik olarak için erişimci alınır true değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsAutoAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>Parametreler

*nAccessor*<br/>
[in] Erişimci sıfır uzaklığı numarası.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** erişimci erişimcinin ise. Aksi halde **false**.

## <a name="release"></a> CAccessorBase::ReleaseAccessors

Sınıfı tarafından oluşturulan erişimcileri serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);
```

#### <a name="parameters"></a>Parametreler

*pUnk*<br/>
[in] Bir işaretçi bir `IUnknown` erişimci oluşturuldu COM nesnesi için arabirim.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Çağrılabilir [CAccessorRowset::Close](../../data/oledb/caccessorrowset-close.md).

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessorBase Sınıfı](../../data/oledb/caccessorbase-class.md)