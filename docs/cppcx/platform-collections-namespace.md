---
title: Platform::Collections Namespace | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2018
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- collection/Platform::Collections
dev_langs:
- C++
helpviewer_keywords:
- Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a8c6191f8cbcf79973a5af55d222dd6f17fc47e
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106076"
---
# <a name="platformcollections-namespace"></a>Platform::Collections Namespace

Platform::Collections ad alanı içeren `Map`, `MapView`, `Vector`, ve `VectorView` sınıfları. Bu sınıfların tanımlanan karşılık gelen arabirimin somut uygulamalarıdır [Windows::Foundation:: Collections](/uwp/api/Windows.Foundation.Collections) ad alanı. Somut koleksiyon türleri (örneğin, Javascript veya C# programı bir C++ bileşeni çağırıyor) ABI arasında taşınabilir değildir, ancak bunlar karşılık gelen onların arabirim türleri için örtük olarak dönüştürülebilir. Örneğin, doldurur ve bir koleksiyonu döndüren genel bir yöntem uygularsanız, ardından kullanmak [Platform::Collections:: Vector](../cppcx/platform-collections-vector-class.md) koleksiyon dahili olarak uygulamak ve kullanmak için [Windows::Foundation:: Collections: : Ivector](/uwp/api/Windows.Foundation.Collections.IVector_T_) dönüş türü. Daha fazla bilgi için [koleksiyonları](../cppcx/collections-c-cx.md) ve [C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Gelen bir platform::Collections:: Vector oluşturabilirsiniz bir [std::vector](../standard-library/vector-class.md) ve [Platform::Collections:: Map](../cppcx/platform-collections-map-class.md) gelen bir [std::map](../standard-library/map-class.md).

Ayrıca, Platform::Collections ad alanı geri ekleme ve giriş yineleyiciler için destek sağlar ve `Vector` ve `VectorView` yineleyiciler.

Eklemeniz gerekir (`#include`) collection.h üst bilgiyi Platform::Collections ad alanı türleri kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <collection.h>
using namespace Platform::Collections;
```

### <a name="members"></a>Üyeler

Bu ad alanı, aşağıdaki üyeleri içerir.

|Ad|Açıklama|
|----------|-----------------|
|[Platform::Collections::BackInsertIterator Sınıfı](../cppcx/platform-collections-backinsertiterator-class.md)|Bir toplamanın sonunda bir öğe ekleyen bir yineleyici temsil eder.|
|[Platform::Collections::InputIterator Sınıfı](../cppcx/platform-collections-inputiterator-class.md)|Bir koleksiyonun başında bir öğe ekleyen bir yineleyici temsil eder.|
|[Platform::Collections::Map Sınıfı](../cppcx/platform-collections-map-class.md)|Değiştirilebilir bir anahtar tarafından erişilen anahtar-değer çifti koleksiyonunu temsil eder. Benzer şekilde [std::map](../standard-library/map-class.md).|
|[Platform::Collections::MapView Sınıfı](../cppcx/platform-collections-mapview-class.md)|Bir salt okunur bir anahtar tarafından erişilen anahtar-değer çifti koleksiyonunu temsil eder.|
|[Platform::Collections::Vector Sınıfı](../cppcx/platform-collections-vector-class.md)|Öğelerin değiştirilebilir bir dizisini temsil eder. Benzer şekilde [std::vector](../standard-library/vector-class.md).|
|[Platform::Collections::VectorIterator Sınıfı](../cppcx/platform-collections-vectoriterator-class.md)|Trafiğiyle bir yineleyiciyi temsil eden bir `Vector` koleksiyonu.|
|[Platform::Collections::VectorView Sınıfı](../cppcx/platform-collections-vectorview-class.md)|Bir salt okunur dizi öğeleri temsil eder.|
|[Platform::Collections::VectorViewIterator Sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)|Trafiğiyle bir yineleyiciyi temsil eden bir `VectorView` koleksiyonu.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)

### <a name="requirements"></a>Gereksinimler

**Meta veri:** platform.winmd

**Namespace:** Platform::Collections

**Derleyici seçeneği:** /ZW

## <a name="see-also"></a>Ayrıca bkz.

[Platform Namespace](../cppcx/platform-namespace-c-cx.md)
