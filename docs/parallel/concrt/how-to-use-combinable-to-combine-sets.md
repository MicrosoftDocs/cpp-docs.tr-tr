---
title: "Nasıl yapılır: kümeleri birleştirmek için combinable kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8bbd36e9536707bc639e8f80cc019b7fda18f793
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-combinable-to-combine-sets"></a>Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma
Bu konuda nasıl kullanılacağını gösterir [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) asal sayılar kümesi işlem sınıfı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, iki kez asal sayılar kümesi hesaplar. Her hesaplama sonucunda depolayan bir [std::bitset](../../standard-library/bitset-class.md) nesnesi. Örnek ilk kümesi seri olarak hesaplar ve paralel kümesinde hesaplar. Örnek, ayrıca her iki hesaplamalar gerçekleştirmek için gereken süreyi konsola yazdırır.  
  
 Bu örnekte [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması ve `combinable` iş parçacığı yerel kümeleri oluşturmak için nesne. Daha sonra kullanır [concurrency::combinable::combine_each](reference/combinable-class.md#combine_each) iş parçacığı yerel kümeleri son küme halinde birleştirmek için yöntem.  

  
 [!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]  
  
 Aşağıdaki örnek çıkış dört işlemciye sahip bir bilgisayar için ' dir.  
  
```Output  
serial time: 312 ms  
 
parallel time: 78 ms  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `parallel-combine-primes.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc paralel-birleştirme-primes.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable sınıfı](../../parallel/concrt/reference/combinable-class.md)   
 [combinable::combine_each yöntemi](reference/combinable-class.md#combine_each)


