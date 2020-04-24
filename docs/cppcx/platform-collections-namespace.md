---
title: Platform::Koleksiyonlar Namespace
ms.date: 01/18/2018
ms.topic: reference
f1_keywords:
- collection/Platform::Collections
helpviewer_keywords:
- Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
ms.openlocfilehash: ab6b78f1b88c586a11276d36387fb42ea6ee667f
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032427"
---
# <a name="platformcollections-namespace"></a>Platform::Koleksiyonlar Namespace

Platform::Koleksiyonlar ad alanı `Map`, `MapView` `Vector`, `VectorView` , ve sınıfları içerir. Bu [sınıflar, Windows::Foundation::Collections](/uwp/api/windows.foundation.collections) ad alanında tanımlanan ilgili arabirimlerin somut uygulamalarıdır. Somut toplama türleri ABI genelinde taşınabilir değildir (örneğin, bir Javascript veya C# programı C++ bileşenine çağrı yaptığında), ancak dolaylı olarak karşılık gelen arabirim türlerine dönüştürülebilir. Örneğin, bir koleksiyonu dolduran ve döndüren genel bir yöntem uygularsanız, koleksiyonu dahili olarak uygulamak için [Platform::Collections::Vector'u](../cppcx/platform-collections-vector-class.md) kullanın ve [Windows:Foundation::Collections::IVector](/uwp/api/windows.foundation.collections.ivector-1) return türü olarak kullanın. Daha fazla bilgi için [C++'da](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp) [Koleksiyonlar](../cppcx/collections-c-cx.md) ve Windows Runtime Bileşenleri Oluşturma'ya bakın.

Bir Platform oluşturabilirsiniz::Koleksiyonlar::Vektör bir [std::vektör](../standard-library/vector-class.md) ve bir [Platform::Koleksiyonlar::Harita](../cppcx/platform-collections-map-class.md) bir [std::map](../standard-library/map-class.md).

Buna ek olarak, Platform::Koleksiyonlar ad alanı geri ekleme ve giriş `Vector` yineleyiciler ve `VectorView` yineleyiciler için destek sağlar.

Platformdaki türleri`#include`kullanmak için ( ) collection.h üstbilgisini eklemeniz gerekir::Koleksiyonlar ad alanı.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <collection.h>
using namespace Platform::Collections;
```

### <a name="members"></a>Üyeler

Bu ad alanı aşağıdaki üyeleri içerir.

|Adı|Açıklama|
|----------|-----------------|
|[Platform::Koleksiyonlar::BackInsertIterator Sınıfı](../cppcx/platform-collections-backinsertiterator-class.md)|Koleksiyonun sonuna öğe ekleyen bir yineleyiciyi temsil eder.|
|[Platform::Collections::InputIterator Sınıfı](../cppcx/platform-collections-inputiterator-class.md)|Koleksiyonun başına bir öğe ekleyen bir yineleyiciyi temsil eder.|
|[Platform::Collections::Map Sınıfı](../cppcx/platform-collections-map-class.md)|Bir anahtar tarafından erişilen anahtar değer çiftlerinin değiştirilebilir bir koleksiyonunu temsil eder. [Std benzer::harita](../standard-library/map-class.md).|
|[Platform::Koleksiyonlar::MapView Sınıfı](../cppcx/platform-collections-mapview-class.md)|Bir anahtar tarafından erişilen salt okunur anahtar değer çiftleri koleksiyonunu temsil eder.|
|[Platform::Collections::Vector Sınıfı](../cppcx/platform-collections-vector-class.md)|Değiştirilebilir bir öğe dizisini temsil eder. [Std benzer::vektör](../standard-library/vector-class.md).|
|[Platform::Collections::VectorIterator Sınıfı](../cppcx/platform-collections-vectoriterator-class.md)|Koleksiyonda geçiş yapan bir yineleyiciyi `Vector` temsil eder.|
|[Platform::Collections::VectorView Sınıfı](../cppcx/platform-collections-vectorview-class.md)|Salt okunur öğe dizisini temsil eder.|
|[Platform::Koleksiyonlar::VectorViewIterator Sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)|Koleksiyonda geçiş yapan bir yineleyiciyi `VectorView` temsil eder.|

## <a name="inheritance-hierarchy"></a>Kalıtım hiyerarşisi

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)

### <a name="requirements"></a>Gereksinimler

**Meta veriler:** platform.winmd

**Ad alanı:** Platform::Koleksiyonlar

**Derleyici seçeneği:** /ZW

## <a name="see-also"></a>Ayrıca bkz.

[Platform İsim Alanı](../cppcx/platform-namespace-c-cx.md)
