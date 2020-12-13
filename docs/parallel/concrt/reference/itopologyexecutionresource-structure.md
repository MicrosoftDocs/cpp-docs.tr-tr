---
description: ': ITopologyExecutionResource yapısı hakkında daha fazla bilgi edinin'
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
ms.openlocfilehash: c2567cf9e34e0b27308e331056d5e0dbc99b2779
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334382"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource Yapısı

Kaynak Yöneticisi tarafından tanımlanan yürütme kaynağına yönelik arabirim.

## <a name="syntax"></a>Syntax

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

## <a name="itopologyexecutionresourcegetid-method"></a><a name="getid"></a> ITopologyExecutionResource:: GetID Yöntemi

Bu yürütme kaynağı için Kaynak Yöneticisi benzersiz tanımlayıcısını döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi bu yürütme kaynağı için benzersiz tanımlayıcısıdır.

## <a name="itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a> ITopologyExecutionResource:: GetNext Yöntemi

Numaralandırma düzeninde bir sonraki yürütme kaynağına bir arabirim döndürür.

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Numaralandırma düzeninde bir sonraki yürütme kaynağına yönelik arabirim. Bu yürütme kaynağının ait olduğu düğümün numaralandırma düzeninde daha fazla düğüm yoksa, bu yöntem değeri döndürür `NULL` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
