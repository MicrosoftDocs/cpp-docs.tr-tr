---
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
ms.openlocfilehash: 1b4cb6a856d6da7b8eee7f9cba1ad51e375c024d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140054"
---
# <a name="itopologynode-structure"></a>ITopologyNode Yapısı

Kaynak Yöneticisi tarafından tanımlanan bir topoloji düğümüne yönelik arabirim. Bir düğüm bir veya daha fazla yürütme kaynağı içeriyor.

## <a name="syntax"></a>Sözdizimi

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

## <a name="getexecutionresourcecount"></a>ITopologyNode:: GetExecutionResourceCount yöntemi

Bu düğüm altında birlikte gruplanmış yürütme kaynakları sayısını döndürür.

```cpp
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu düğüm altında birlikte gruplanmış yürütme kaynakları sayısı.

## <a name="getfirstexecutionresource"></a>ITopologyNode:: GetFirstExecutionResource yöntemi

Numaralandırma düzeninde bu düğüm altında gruplandırılan ilk yürütme kaynağını döndürür.

```cpp
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu düğüm altında numaralandırma düzeninde gruplandırılan ilk yürütme kaynağı.

## <a name="getid"></a>ITopologyNode:: GetID Yöntemi

Bu düğüm için Kaynak Yöneticisi benzersiz tanımlayıcısını döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi bu düğüm için benzersiz tanımlayıcısıdır.

### <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma Zamanı, işlemci düğümleri gruplarındaki sistemdeki donanım iş parçacıklarını temsil eder. Düğümler genellikle sistemin donanım topolojisinden türetilir. Örneğin, belirli bir yuvada veya belirli bir NUMA düğümündeki tüm işlemciler aynı işlemci düğümüne ait olabilir. Kaynak Yöneticisi, bu düğümlere `0` başlayarak `nodeCount - 1`dahil olmak üzere benzersiz tanımlayıcılar atar; burada `nodeCount`, sistemdeki toplam işlemci düğümü sayısını temsil eder.

Düğüm sayısı [GetProcessorNodeCount](concurrency-namespace-functions.md)işlevinden elde edilebilir.

## <a name="getnext"></a>ITopologyNode:: GetNext Yöntemi

Numaralandırma düzeninde bir sonraki topoloji düğümüne bir arabirim döndürür.

```cpp
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Numaralandırma düzeninde bir sonraki düğüme yönelik arabirim. Sistem topolojisinin numaralandırma düzeninde daha fazla düğüm yoksa, bu yöntem `NULL`değer döndürür.

## <a name="getnumanode"></a>ITopologyNode:: GetNumaNode Yöntemi

Bu kaynak maanger düğümünün ait olduğu Windows atanan NUMA düğüm numarasını döndürür.

```cpp
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu Kaynak Yöneticisi düğümünün ait olduğu Windows atanan NUMA düğüm numarası.

### <a name="remarks"></a>Açıklamalar

Bu düğüme ait sanal bir işlemci kökünde çalışan bir iş parçacığı proxy 'si, bu yöntemin döndürdüğü NUMA düğümü için en az NUMA düğüm düzeyiyle benzeşimine sahip olacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
