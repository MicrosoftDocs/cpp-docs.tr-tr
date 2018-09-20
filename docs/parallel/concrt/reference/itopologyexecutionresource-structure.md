---
title: Itopologyexecutionresource yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60a0097aded73e3e0251d38daf5da71197668d3a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383798"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource Yapısı

Kaynak Yöneticisi tarafından tanımlanan bir yürütme kaynağı arabirim.

## <a name="syntax"></a>Sözdizimi

```
struct ITopologyExecutionResource;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Itopologyexecutionresource::GetID](#getid)|Bu yürütme kaynak için Resource Manager'ın benzersiz tanımlayıcısını döndürür.|
|[Itopologyexecutionresource::GetNext](#getnext)|Sonraki yürütme kaynak numaralandırma sırasında arasında bir arabirim döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, genellikle kaynak yöneticisi tarafından gözlemlenen sistemin topolojisi yürütmek için kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ITopologyExecutionResource`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="getid"></a>  Itopologyexecutionresource::GetID metodu

Bu yürütme kaynak için Resource Manager'ın benzersiz tanımlayıcısını döndürür.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Resource Manager'ın bu yürütme kaynağın benzersiz tanımlayıcısı.

##  <a name="getnext"></a>  Itopologyexecutionresource::GetNext metodu

Sonraki yürütme kaynak numaralandırma sırasında arasında bir arabirim döndürür.

```
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Sonraki yürütme kaynak numaralandırma sırasında bir arabirim. Bu yürütme kaynağın ait olduğu düğüm sabit listesi sırasına göre daha fazla düğüm varsa, bu yöntem değeri döndüreceği `NULL`.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
