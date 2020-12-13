---
description: 'Daha fazla bilgi edinin: Platform:: Collections ad alanı'
title: 'Platform:: Collections ad alanı'
ms.date: 01/18/2018
ms.topic: reference
f1_keywords:
- collection/Platform::Collections
helpviewer_keywords:
- Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
ms.openlocfilehash: d80479ed73183450dedd86119dda2da1fab800e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340417"
---
# <a name="platformcollections-namespace"></a>Platform:: Collections ad alanı

Platform:: Collections ad alanı,, `Map` , `MapView` `Vector` ve sınıflarını içerir `VectorView` . Bu sınıflar, [Windows:: Foundation:: Collections](/uwp/api/windows.foundation.collections) ad alanında tanımlanan ilgili arabirimlerin somut uygulamalarıdır. Somut koleksiyon türleri ABı arasında taşınabilir (örneğin, bir JavaScript veya C# programı bir C++ bileşenine çağrı yapıldığında), ancak bunlara karşılık gelen arabirim türlerine örtük olarak dönüştürülebilir. Örneğin, bir koleksiyonu dolduran ve döndüren bir ortak yöntem uygularsanız, koleksiyonu dahili olarak uygulamak için [Platform:: Collections:: vector](../cppcx/platform-collections-vector-class.md) öğesini kullanın ve dönüş türü olarak [Windows:: Foundation:: Collections:: ivector](/uwp/api/windows.foundation.collections.ivector-1) kullanın. Daha fazla bilgi için bkz. [koleksiyonlar](../cppcx/collections-c-cx.md) ve [C++ ' da Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Bir std:: [Vector](../standard-library/vector-class.md) öğesinden bir platform:: Collections:: vector ve bir std:: [Map](../standard-library/map-class.md)öğesinden [Platform:: Collections:: map](../cppcx/platform-collections-map-class.md) ' i oluşturabilirsiniz.

Ayrıca, Platform:: Collections ad alanı, arka INSERT ve Input yineleyiciler, ve yineleyiciler için destek sağlar `Vector` `VectorView` .

`#include`Platform:: Collections ad alanındaki türleri kullanmak için Collection. h üst bilgisini dahil etmeniz gerekir.

## <a name="syntax"></a>Syntax

```cpp
#include <collection.h>
using namespace Platform::Collections;
```

### <a name="members"></a>Üyeler

Bu ad alanı aşağıdaki üyeleri içerir.

|Ad|Açıklama|
|----------|-----------------|
|[Platform:: Collections:: Backınsertıterator sınıfı](../cppcx/platform-collections-backinsertiterator-class.md)|Bir koleksiyonun sonuna bir öğe ekleyen bir yineleyiciyi temsil eder.|
|[Platform:: Collections:: InputIterator sınıfı](../cppcx/platform-collections-inputiterator-class.md)|Bir koleksiyonun başlangıcında bir öğe ekleyen bir yineleyiciyi temsil eder.|
|[Platform:: Collections:: Map sınıfı](../cppcx/platform-collections-map-class.md)|Bir anahtar tarafından erişilen anahtar-değer çiftlerinin değiştirilebilir koleksiyonunu temsil eder. [Std:: Map](../standard-library/map-class.md)ile benzerdir.|
|[Platform:: Collections:: MapView Sınıfı](../cppcx/platform-collections-mapview-class.md)|Bir anahtar tarafından erişilen anahtar-değer çiftlerinin salt okunurdur bir koleksiyonunu temsil eder.|
|[Platform:: Collections:: vector Sınıfı](../cppcx/platform-collections-vector-class.md)|Değiştirilebilir öğe dizisini temsil eder. [Std:: vector](../standard-library/vector-class.md)öğesine benzer.|
|[Platform:: Collections:: Vectorterator sınıfı](../cppcx/platform-collections-vectoriterator-class.md)|Bir koleksiyondaki bir yineleyiciyi temsil eder `Vector` .|
|[Platform:: Collections:: VectorView sınıfı](../cppcx/platform-collections-vectorview-class.md)|Öğelerin salt okunurdur dizisini temsil eder.|
|[Platform:: Collections:: Vectorviewwiterator sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)|Bir koleksiyondaki bir yineleyiciyi temsil eder `VectorView` .|

## <a name="inheritance-hierarchy"></a>Devralma hiyerarşisi

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)

### <a name="requirements"></a>Gereksinimler

**Meta veri:** platform. winmd

**Ad alanı:** Platform:: Collections

**Derleyici seçeneği:** /ZW

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
