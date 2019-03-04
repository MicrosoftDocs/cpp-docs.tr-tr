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
ms.openlocfilehash: 867e0543d1b9f2810a3fe761f038947c4d88da4d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268635"
---
# <a name="itopologynode-structure"></a>ITopologyNode Yapısı

Kaynak Yöneticisi tarafından tanımlandığı gibi bir topoloji düğüm için bir arabirim. Bir düğüm, bir veya daha fazla yürütme kaynakları içerir.

## <a name="syntax"></a>Sözdizimi

```
struct ITopologyNode;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Itopologynode::getexecutionresourcecount](#getexecutionresourcecount)|Bu düğüm altında gruplanmış yürütme kaynakların sayısını döndürür.|
|[Itopologynode::getfirstexecutionresource](#getfirstexecutionresource)|Numaralandırma sırasında bu düğüm altında gruplandırılmış ilk yürütme kaynak döndürür.|
|[Itopologynode::GetID](#getid)|Resource Manager'ın bu düğüm için benzersiz tanımlayıcı döndürür.|
|[Itopologynode::GetNext](#getnext)|Numaralandırma sırasında sonraki topolojisi düğümü için bir arabirim döndürür.|
|[Itopologynode::getnumanode](#getnumanode)|Windows döndürür, bu kaynak yöneticisi düğümünün ait olduğu NUMA düğüm numarasını atadı.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, genellikle kaynak yöneticisi tarafından gözlemlenen sistemin topolojisi yürütmek için kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ITopologyNode`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="getexecutionresourcecount"></a>  Itopologynode::getexecutionresourcecount metodu

Bu düğüm altında gruplanmış yürütme kaynakların sayısını döndürür.

```
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Yürütme kaynak sayısı, bu düğüm altında gruplanmış.

##  <a name="getfirstexecutionresource"></a>  Itopologynode::getfirstexecutionresource metodu

Numaralandırma sırasında bu düğüm altında gruplandırılmış ilk yürütme kaynak döndürür.

```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Numaralandırma sırasında bu düğüm altında ilk yürütme kaynak gruplandırılır.

##  <a name="getid"></a>  Itopologynode::GetID metodu

Resource Manager'ın bu düğüm için benzersiz tanımlayıcı döndürür.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Resource Manager'ın bu düğüm için benzersiz tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma zamanı işlemci düğümleri gruplar halinde sistemdeki donanım iş parçacıklarının temsil eder. Düğümleri genellikle sistem donanım topolojisinden türetilir. Örneğin, belirli bir yuva veya belirli bir NUMA düğümünde tüm işlemcilerin aynı işlemci düğüme ait olabilir. Resource Manager sürümünden itibaren bu düğümler benzersiz tanımlayıcı atar `0` dahil `nodeCount - 1`burada `nodeCount` işlemci düğüm sistemdeki toplam sayısını temsil eder.

Düğüm sayısı işlevden elde edilebilir [GetProcessorNodeCount](concurrency-namespace-functions.md).

##  <a name="getnext"></a>  Itopologynode::GetNext metodu

Numaralandırma sırasında sonraki topolojisi düğümü için bir arabirim döndürür.

```
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Numaralandırma sırasında sonraki düğümü bir arabirim. Sistemin topolojisi sabit listesi sırasına göre daha fazla düğüm varsa, bu yöntem değeri döndüreceği `NULL`.

##  <a name="getnumanode"></a>  Itopologynode::getnumanode metodu

Windows döndürür, bu kaynak yöneticisi düğümünün ait olduğu NUMA düğüm numarasını atadı.

```
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Windows, bu kaynak yöneticisi düğümünün ait olduğu NUMA düğüm numarasını atadı.

### <a name="remarks"></a>Açıklamalar

Bu düğüme ait bir sanal işlemci kökünde çalışan iş parçacığı proxy en az benzeşimi olacaktır NUMA nodu düzeyinde bu yöntem tarafından döndürülen NUMA düğümü için.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
