---
title: Platform::Collections Namespace | Microsoft Docs
ms.custom: 
ms.date: 01/25/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: collection/Platform::Collections
dev_langs: C++
helpviewer_keywords: Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 04514a4d4ddbba8b6c28e35e964deb153803580f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="platformcollections-namespace"></a>Platform::Collections Namespace
Platform::Collection ad alanında `Map`, `MapView`, `Vector`, ve `VectorView` sınıfları. Bu sınıfların tanımlanan karşılık gelen arabirimler somut uygulamalarıdır [Windows::Foundation::Collections](http://go.microsoft.com/fwlink/p/?LinkId=262645) ad alanı. Somut koleksiyon türleri (örneğin bir Javascript veya C# C++ bileşeni çağrılarını program) ABI üzerinden taşınabilir değildir, ancak karşılık gelen arabirimi türlerini örtük olarak dönüştürülebilir. Örneğin, doldurur ve koleksiyonu döndüren bir genel yöntem uygularsanız, daha sonra kullanmak [Platform::Collections:: Vector](../cppcx/platform-collections-vector-class.md) koleksiyonu dahili olarak uygulamak ve kullanmak için [Windows::Foundation::Collections: : IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) dönüş türü. Daha fazla bilgi için bkz: [koleksiyonları](../cppcx/collections-c-cx.md) ve [C++'da Windows çalışma zamanı bileşenleri oluşturma](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md).  
  
 Gelen bir platform::Collections:: Vector oluşturabileceğiniz bir [std::vector](../standard-library/vector-class.md) ve [Platform::Collections](../cppcx/platform-collections-map-class.md) gelen bir [std::map](../standard-library/map-class.md).  
  
 Ayrıca, Platform::Collection ad alanı geri INSERT ve giriş yineleyiciler için destek sağlar ve `Vector` ve `VectorView` yineleyiciler.  
  
 Eklemeniz gerekir (`#include`) Platform::Collection ad alanında türleri kullanılacak collection.h üstbilgi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
#include <collection.h>  
using namespace Platform::Collection;  
```  
  
### <a name="members"></a>Üyeler  
 Bu ad alanı, aşağıdaki üyeleri içerir.  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Platform::Collections::BackInsertIterator sınıfı](../cppcx/platform-collections-backinsertiterator-class.md)|Bir koleksiyonun sonuna bir öğe ekler yineleyici temsil eder.|  
|[Platform::Collections::InputIterator sınıfı](../cppcx/platform-collections-inputiterator-class.md)|Bir koleksiyon başına bir öğe ekler yineleyici temsil eder.|  
|[Platform::Collections sınıfı](../cppcx/platform-collections-map-class.md)|Bir anahtar tarafından erişilen anahtar-değer çiftleri değiştirilebilir bir koleksiyonunu temsil eder. Benzer şekilde [std::map](../standard-library/map-class.md).|  
|[Platform::Collections::MapView sınıfı](../cppcx/platform-collections-mapview-class.md)|Bir anahtar tarafından erişilen anahtar-değer çiftleri salt okunur bir koleksiyonunu temsil eder.|  
|[Platform::Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md)|Öğeleri değiştirilebilir bir dizi temsil eder. Benzer şekilde [std::vector](../standard-library/vector-class.md).|  
|[Platform::Collections::VectorIterator sınıfı](../cppcx/platform-collections-vectoriterator-class.md)|Geçeceğini yineleyici temsil eden bir `Vector` koleksiyonu.|  
|[Platform::Collections::VectorView sınıfı](../cppcx/platform-collections-vectorview-class.md)|Öğe salt okunur bir dizi temsil eder.|  
|[Platform::Collections::VectorViewIterator sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)|Geçeceğini yineleyici temsil eden bir `VectorView` koleksiyonu.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)  
  
### <a name="requirements"></a>Gereksinimler  
 **Meta veriler:** platform.winmd  
  
 **Namespace:** Platform::Collections  
  
 **Derleyici seçeneği:** /ZW  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](../cppcx/platform-namespace-c-cx.md)