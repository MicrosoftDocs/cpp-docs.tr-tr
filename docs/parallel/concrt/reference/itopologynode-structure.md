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
ms.openlocfilehash: 7cb815c4f7dc5ad09e8d352abc3f3375b8d9e205
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368101"
---
# <a name="itopologynode-structure"></a>ITopologyNode Yapısı

Kaynak Yöneticisi tarafından tanımlandığı gibi topoloji düğümüne arabirim. Düğüm bir veya daha fazla yürütme kaynağı içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct ITopologyNode;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[İtopolojiNode::GetExecutionResourceCount](#getexecutionresourcecount)|Bu düğüm altında birlikte gruplanan yürütme kaynaklarının sayısını döndürür.|
|[İTopolojiNode::GetFirstExecutionResource](#getfirstexecutionresource)|Numaralandırma sırasına göre bu düğüm altında gruplanan ilk yürütme kaynağını döndürür.|
|[İTopolojiNode::GetId](#getid)|Kaynak Yöneticisi'nin bu düğüm için benzersiz tanımlayıcısını döndürür.|
|[İTopolojiNode::GetNext](#getnext)|Bir arabirimi numaralandırma sırasına göre bir sonraki topoloji düğümüne döndürür.|
|[İTopolojiNode::GetNumaNode](#getnumanode)|Bu Kaynak Maanger düğümünün ait olduğu NUMA düğüm numarasını atanan Windows'u döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim genellikle Kaynak Yöneticisi tarafından gözlendiği gibi sistemin topolojisi yürümek için kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ITopologyNode`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="itopologynodegetexecutionresourcecount-method"></a><a name="getexecutionresourcecount"></a>İtopolojiNode::GetExecutionResourceCount Yöntemi

Bu düğüm altında birlikte gruplanan yürütme kaynaklarının sayısını döndürür.

```cpp
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu düğüm altında gruplanmış yürütme kaynaklarının sayısı.

## <a name="itopologynodegetfirstexecutionresource-method"></a><a name="getfirstexecutionresource"></a>İTopolojiNode::GetFirstExecutionResource Yöntemi

Numaralandırma sırasına göre bu düğüm altında gruplanan ilk yürütme kaynağını döndürür.

```cpp
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Numaralandırma sırasına göre bu düğüm altında gruplanan ilk yürütme kaynağı.

## <a name="itopologynodegetid-method"></a><a name="getid"></a>İTopolojiNode::GetId Yöntemi

Kaynak Yöneticisi'nin bu düğüm için benzersiz tanımlayıcısını döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi'nin bu düğüm için benzersiz tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma Süresi, işlemci düğümleri gruplarında sistemdeki donanım iş parçacıklarını temsil eder. Düğümler genellikle sistemin donanım topolojisinden türetilir. Örneğin, belirli bir soketveya belirli bir NUMA düğümündeki tüm işlemciler aynı işlemci düğümüne ait olabilir. Kaynak Yöneticisi, sistemdeki toplam işlemci düğümü sayısını temsil eden `0` `nodeCount - 1` `nodeCount` ve dahil olmak üzere bu düğümlere benzersiz tanımlayıcılar atar.

Düğüm sayısı [GetProcessorNodeCount](concurrency-namespace-functions.md)işlevinden elde edilebilir.

## <a name="itopologynodegetnext-method"></a><a name="getnext"></a>İTopolojiNode::GetNext Yöntemi

Bir arabirimi numaralandırma sırasına göre bir sonraki topoloji düğümüne döndürür.

```cpp
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Numaralandırma sırasına göre bir sonraki düğüme arabirim. Sistem topolojisinin numaralandırma sırasına göre daha fazla düğüm yoksa, bu yöntem `NULL`değeri döndürür.

## <a name="itopologynodegetnumanode-method"></a><a name="getnumanode"></a>İTopolojiNode::GetNumaNode Yöntemi

Bu Kaynak Maanger düğümünün ait olduğu NUMA düğüm numarasını atanan Windows'u döndürür.

```cpp
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Windows, bu Kaynak Yöneticisi düğümünün ait olduğu NUMA düğüm numarasını atadı.

### <a name="remarks"></a>Açıklamalar

Bu düğüme ait sanal işlemci kökünde çalışan bir iş parçacığı proxy'si, bu yöntemle döndürülen NUMA düğümü için en az NUMA düğüm düzeyine yakınlık sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
