---
title: Platform::Collections Namespace | Microsoft Docs
ms.custom: 
ms.date: 01/18/2018
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- collection/Platform::Collections
dev_langs:
- C++
helpviewer_keywords:
- Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f7c99f99e0935fd96aa02240de2c0c72ce890a0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="platformcollections-namespace"></a>Platform::Collections Namespace

Platform::Collections ad alanında `Map`, `MapView`, `Vector`, ve `VectorView` sınıfları. Bu sınıfların tanımlanan karşılık gelen arabirimler somut uygulamalarıdır [Windows::Foundation::Collections](http://go.microsoft.com/fwlink/p/?LinkId=262645) ad alanı. Somut koleksiyon türleri (örneğin bir Javascript veya C# C++ bileşeni çağrılarını program) ABI üzerinden taşınabilir değildir, ancak karşılık gelen arabirimi türlerini örtük olarak dönüştürülebilir. Örneğin, doldurur ve koleksiyonu döndüren bir genel yöntem uygularsanız, daha sonra kullanmak [Platform::Collections:: Vector](../cppcx/platform-collections-vector-class.md) koleksiyonu dahili olarak uygulamak ve kullanmak için [Windows::Foundation::Collections: : IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) dönüş türü. Daha fazla bilgi için bkz: [koleksiyonları](../cppcx/collections-c-cx.md) ve [C++'da Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Gelen bir platform::Collections:: Vector oluşturabileceğiniz bir [std::vector](../standard-library/vector-class.md) ve [Platform::Collections](../cppcx/platform-collections-map-class.md) gelen bir [std::map](../standard-library/map-class.md).

Ayrıca, Platform::Collections ad alanı geri INSERT ve giriş yineleyiciler için destek sağlar ve `Vector` ve `VectorView` yineleyiciler.

Eklemeniz gerekir (`#include`) türlerine Platform::Collections ad alanını kullanmak için collection.h üstbilgi.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <collection.h>
using namespace Platform::Collections;
```

### <a name="members"></a>Üyeler

Bu ad alanı, aşağıdaki üyeleri içerir.

|Ad|Açıklama|
|----------|-----------------|
|[Platform::Collections::BackInsertIterator Sınıfı](../cppcx/platform-collections-backinsertiterator-class.md)|Bir koleksiyonun sonuna bir öğe ekler yineleyici temsil eder.|
|[Platform::Collections::InputIterator Sınıfı](../cppcx/platform-collections-inputiterator-class.md)|Bir koleksiyon başına bir öğe ekler yineleyici temsil eder.|
|[Platform::Collections::Map Sınıfı](../cppcx/platform-collections-map-class.md)|Bir anahtar tarafından erişilen anahtar-değer çiftleri değiştirilebilir bir koleksiyonunu temsil eder. Benzer şekilde [std::map](../standard-library/map-class.md).|
|[Platform::Collections::MapView Sınıfı](../cppcx/platform-collections-mapview-class.md)|Bir anahtar tarafından erişilen anahtar-değer çiftleri salt okunur bir koleksiyonunu temsil eder.|
|[Platform::Collections::Vector Sınıfı](../cppcx/platform-collections-vector-class.md)|Öğeleri değiştirilebilir bir dizi temsil eder. Benzer şekilde [std::vector](../standard-library/vector-class.md).|
|[Platform::Collections::VectorIterator Sınıfı](../cppcx/platform-collections-vectoriterator-class.md)|Geçeceğini yineleyici temsil eden bir `Vector` koleksiyonu.|
|[Platform::Collections::VectorView Sınıfı](../cppcx/platform-collections-vectorview-class.md)|Öğe salt okunur bir dizi temsil eder.|
|[Platform::Collections::VectorViewIterator Sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)|Geçeceğini yineleyici temsil eden bir `VectorView` koleksiyonu.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)

### <a name="requirements"></a>Gereksinimler

**Meta veriler:** platform.winmd

**Namespace:** Platform::Collections

**Derleyici seçeneği:** /ZW

## <a name="see-also"></a>Ayrıca bkz.

[Platform Namespace](../cppcx/platform-namespace-c-cx.md)  
