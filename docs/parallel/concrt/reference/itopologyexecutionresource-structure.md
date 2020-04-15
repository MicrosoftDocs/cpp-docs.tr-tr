---
title: ITopologyExecutionResource Yapısı
ms.date: 11/04/2016
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
ms.openlocfilehash: 2c9221cab1ac2d48bd099a769188e4bee797823c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368142"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource Yapısı

Kaynak Yöneticisi tarafından tanımlandığı gibi yürütme kaynağına arabirim.

## <a name="syntax"></a>Sözdizimi

```cpp
struct ITopologyExecutionResource;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[ITopologyExecutionResource::GetId](#getid)|Bu yürütme kaynağı için Kaynak Yöneticisi'nin benzersiz tanımlayıcısını döndürür.|
|[ITopologyExecutionResource::GetNext](#getnext)|Numaralandırma sırasına göre bir sonraki yürütme kaynağına bir arabirim döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim genellikle Kaynak Yöneticisi tarafından gözlendiği gibi sistemin topolojisi yürümek için kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ITopologyExecutionResource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="itopologyexecutionresourcegetid-method"></a><a name="getid"></a>ITopologyExecutionResource::GetId Yöntemi

Bu yürütme kaynağı için Kaynak Yöneticisi'nin benzersiz tanımlayıcısını döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi'nin bu yürütme kaynağı için benzersiz tanımlayıcısı.

## <a name="itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a>ITopologyExecutionResource::GetNext Yöntemi

Numaralandırma sırasına göre bir sonraki yürütme kaynağına bir arabirim döndürür.

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Numaralandırma sırasına göre bir sonraki yürütme kaynağına bir arabirim. Bu yürütme kaynağının ait olduğu düğümün numaralandırma sırasına başka düğüm yoksa, bu yöntem `NULL`değeri döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
