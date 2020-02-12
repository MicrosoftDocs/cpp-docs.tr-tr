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
ms.openlocfilehash: 82193a9b592cded96f3726cbabd6cf646eaa27c8
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140076"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource Yapısı

Kaynak Yöneticisi tarafından tanımlanan yürütme kaynağına yönelik arabirim.

## <a name="syntax"></a>Sözdizimi

```cpp
struct ITopologyExecutionResource;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ITopologyExecutionResource:: GetId](#getid)|Bu yürütme kaynağı için Kaynak Yöneticisi benzersiz tanımlayıcısını döndürür.|
|[ITopologyExecutionResource:: GetNext](#getnext)|Numaralandırma düzeninde bir sonraki yürütme kaynağına bir arabirim döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim genellikle sistemin topolojisini Kaynak Yöneticisi gözlemlediği şekilde rehberlik etmek için kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ITopologyExecutionResource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="getid"></a>ITopologyExecutionResource:: GetID Yöntemi

Bu yürütme kaynağı için Kaynak Yöneticisi benzersiz tanımlayıcısını döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi bu yürütme kaynağı için benzersiz tanımlayıcısıdır.

## <a name="getnext"></a>ITopologyExecutionResource:: GetNext Yöntemi

Numaralandırma düzeninde bir sonraki yürütme kaynağına bir arabirim döndürür.

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Numaralandırma düzeninde bir sonraki yürütme kaynağına yönelik arabirim. Bu yürütme kaynağının ait olduğu düğümün numaralandırma düzeninde daha fazla düğüm yoksa, bu yöntem `NULL`değer döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
