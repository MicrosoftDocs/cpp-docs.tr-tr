---
description: 'Daha fazla bilgi edinin: ITopologyNode Yapısı'
title: ITopologyNode Yapısı
ms.date: 11/04/2016
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
ms.openlocfilehash: 1d603e35728791ff94e43b03d890061dec834660
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334368"
---
# <a name="itopologynode-structure"></a>ITopologyNode Yapısı

Kaynak Yöneticisi tarafından tanımlanan bir topoloji düğümüne yönelik arabirim. Bir düğüm bir veya daha fazla yürütme kaynağı içeriyor.

## <a name="syntax"></a>Syntax

```cpp
struct ITopologyNode;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ITopologyNode:: GetExecutionResourceCount](#getexecutionresourcecount)|Bu düğüm altında birlikte gruplanmış yürütme kaynakları sayısını döndürür.|
|[ITopologyNode:: GetFirstExecutionResource](#getfirstexecutionresource)|Numaralandırma düzeninde bu düğüm altında gruplandırılan ilk yürütme kaynağını döndürür.|
|[ITopologyNode:: GetId](#getid)|Bu düğüm için Kaynak Yöneticisi benzersiz tanımlayıcısını döndürür.|
|[ITopologyNode:: GetNext](#getnext)|Numaralandırma düzeninde bir sonraki topoloji düğümüne bir arabirim döndürür.|
|[ITopologyNode:: GetNumaNode](#getnumanode)|Bu kaynak maanger düğümünün ait olduğu Windows atanan NUMA düğüm numarasını döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim genellikle sistemin topolojisini Kaynak Yöneticisi gözlemlediği şekilde rehberlik etmek için kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ITopologyNode`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="itopologynodegetexecutionresourcecount-method"></a><a name="getexecutionresourcecount"></a> ITopologyNode:: GetExecutionResourceCount yöntemi

Bu düğüm altında birlikte gruplanmış yürütme kaynakları sayısını döndürür.

```cpp
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu düğüm altında birlikte gruplanmış yürütme kaynakları sayısı.

## <a name="itopologynodegetfirstexecutionresource-method"></a><a name="getfirstexecutionresource"></a> ITopologyNode:: GetFirstExecutionResource yöntemi

Numaralandırma düzeninde bu düğüm altında gruplandırılan ilk yürütme kaynağını döndürür.

```cpp
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu düğüm altında numaralandırma düzeninde gruplandırılan ilk yürütme kaynağı.

## <a name="itopologynodegetid-method"></a><a name="getid"></a> ITopologyNode:: GetID Yöntemi

Bu düğüm için Kaynak Yöneticisi benzersiz tanımlayıcısını döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi bu düğüm için benzersiz tanımlayıcısıdır.

### <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma Zamanı, işlemci düğümleri gruplarındaki sistemdeki donanım iş parçacıklarını temsil eder. Düğümler genellikle sistemin donanım topolojisinden türetilir. Örneğin, belirli bir yuvada veya belirli bir NUMA düğümündeki tüm işlemciler aynı işlemci düğümüne ait olabilir. Kaynak Yöneticisi, bu düğümlere `0` kadar ve dahil olmak üzere benzersiz tanımlayıcılar atar ve bu `nodeCount - 1` , `nodeCount` sistemdeki toplam işlemci düğümü sayısını temsil eder.

Düğüm sayısı [GetProcessorNodeCount](concurrency-namespace-functions.md)işlevinden elde edilebilir.

## <a name="itopologynodegetnext-method"></a><a name="getnext"></a> ITopologyNode:: GetNext Yöntemi

Numaralandırma düzeninde bir sonraki topoloji düğümüne bir arabirim döndürür.

```cpp
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Numaralandırma düzeninde bir sonraki düğüme yönelik arabirim. Sistem topolojisinin numaralandırma düzeninde daha fazla düğüm yoksa, bu yöntem değeri döndürür `NULL` .

## <a name="itopologynodegetnumanode-method"></a><a name="getnumanode"></a> ITopologyNode:: GetNumaNode Yöntemi

Bu kaynak maanger düğümünün ait olduğu Windows atanan NUMA düğüm numarasını döndürür.

```cpp
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu Kaynak Yöneticisi düğümünün ait olduğu Windows atanan NUMA düğüm numarası.

### <a name="remarks"></a>Açıklamalar

Bu düğüme ait sanal bir işlemci kökünde çalışan bir iş parçacığı proxy 'si, bu yöntemin döndürdüğü NUMA düğümü için en az NUMA düğüm düzeyiyle benzeşimine sahip olacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
