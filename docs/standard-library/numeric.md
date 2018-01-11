---
title: "&lt;Sayısal&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <numeric>
dev_langs: C++
helpviewer_keywords: <numeric> header
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2fae023ad0750e150c326ab094e2a89e48d2a39f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltnumericgt"></a>&lt;sayısal&gt;
Sayısal işlemeler için algoritmalar gerçekleştiren kapsayıcı şablon işlevini tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <numeric>  
```  
  
## <a name="remarks"></a>Açıklamalar  
C++ Standart Kitaplığı algoritmalara sayısal algoritmaları benzer [ \<algoritması >](algorithm.md)ve veri yapıları çeşitli üzerinde çalışabilir. Bu standart kitaplığı kapsayıcı sınıfları içerir — örneğin, [vektör](../standard-library/vector-class.md) ve [listesi](../standard-library/list-class.md)ve program tarafından tanımlanan veri yapılarını ve de belirli bir algoritma gereksinimlerini öğeleri dizileri. Algoritmalar dolaylı olarak yineleyiciler üzerinden bir kapsayıcının öğelerine erişerek ve geçiş yaparak bu genellik düzeyine erişir. Algoritmalar genellikle kendi başlangıç veya bitiş konumları tarafından belirtilen yineleyici aralıklarını işler. Aralıklardaki tüm işaretçilerin tekrar başvurulabilir olması ve her aralığın dizisinde olması gerekliliği bakımından, başvurulan aralıkların geçerli olması gerekir; son konum da artış yoluyla birinciden erişilebilir olmalıdır.  
  
 Algoritmalar işlemleri ve her bir C++ Standart Kitaplığı kapsayıcı üye işlevleri tarafından desteklenir ve kapsayıcı nesneleri farklı türde bir etkileşim aynı anda etkinleştirmek eylemleri genişletir.  
  
### <a name="functions"></a>İşlevler  
  
|||  
|-|-|  
|[accumulate](../standard-library/numeric-functions.md#accumulate)|Art arda gelen kısmi toplamları ya da toplama işlemi yerine belirtilmiş bir ikili işlem kullanılarak elde edilen art arda gelen kısmi sonuçların sonucunu hesaplayarak belirtilen aralıktaki tüm öğelerin, bazı başlangıç değerleri de dahil olmak üzere, toplamını hesaplar.|  
|[adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)|Her bir öğe arasındaki art arda gelen farkları ve bir giriş aralığındaki kendi öncellerini hesaplar ve bir hedef aralığında sonuçların çıktısını alır veya fark işleminin başka bir belirtilen bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.|  
|[inner_product](../standard-library/numeric-functions.md#inner_product)|İki aralığın öğe düzeyinde çarpımının toplamını hesaplar ve bunu belirtilen başlangıç değerine ekler veya ürün işlemlerinin başka bir belirtilen ikili işlem tarafından değiştirildiği toplamın ve ürün işlemlerinin genelleştirilmiş bir sonucunu hesaplar.|  
|[iota](../standard-library/numeric-functions.md#iota)|Başlangıç değeri ilk öğe ile başlayan ve değerin ardışık artışlarla ile doldurma depolar (`value++`) her zaman aralığını öğeleri `[first, last)`.|  
|[partial_sum](../standard-library/numeric-functions.md#partial_sum)|SUM'ları ilk öğe ile bir giriş aralığında bir dizi hesaplar *ı*th öğesi ve her toplamda sonucunu depolar *ı*th öğesi bir hedef aralığının veya bir genelleştirilmiş sonucu hesaplar Toplam işlem tarafından başka bir yere değiştirilir yordamı ikili işlem belirtildi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

