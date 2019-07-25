---
title: C++ Standart Kitaplığında İş Parçacığı Güvenliği
ms.date: 11/04/2016
helpviewer_keywords:
- thread safety
- C++ Standard Library, thread safety
- thread safety, C++ Standard Library
ms.assetid: 9351c8fb-4539-4728-b0e9-226e2ac4284b
ms.openlocfilehash: 4ac029a119a77fa87c6cd004fece9c4e6b382026
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460058"
---
# <a name="thread-safety-in-the-c-standard-library"></a>C++ Standart Kitaplığında İş Parçacığı Güvenliği

Aşağıdaki iş parçacığı güvenlik kuralları, C++ standart kitaplıktaki tüm sınıflar için geçerlidir. Bu, aşağıda `shared_ptr`açıklandığı gibi dahildir.  Daha güçlü garantiler bazen, örneğin, aşağıda açıklandığı gibi standart iostream nesneleri ve [ \<atomik >](../standard-library/atomic.md)gibi çok iş parçacığı için tasarlanan türler gibi bazı durumlarda sağlanır.

Bir nesne birden çok iş parçacığından okumak için iş parçacığı güvenlidir. Örneğin, A nesnesi verildiğinde, bir iş parçacığı 1 ve iş parçacığı 2 ' den aynı anda okumak güvenlidir.

Bir nesne bir iş parçacığı tarafından yazılmışsa, bu nesneye aynı veya diğer iş parçacıklarında yapılan tüm okuma ve yazma işlemleri korunmuş olmalıdır. Örneğin, A nesnesi verildiğinde, iş parçacığı 1 öğesine yazuyorsa, iş parçacığının 2 ' den okunmasından veya bir öğesine yazmasını önlenmelidir.

Başka bir iş parçacığı aynı türden farklı bir örneğe okuma veya yazma olsa da, bir türün bir örneğini okumak ve yazmak güvenlidir. Örneğin, A ve B nesneleri aynı türde olduğunda, iş parçacığı 1 ' de yazıldığı ve B iş parçacığı 2 ' de okunduğunda bu güvenli bir seçenektir.

## <a name="sharedptr"></a>shared_ptr

Birden çok iş parçacığı aynı anda farklı [shared_ptr](../standard-library/shared-ptr-class.md) nesneleri okuyabilir ve yazabilir, ancak nesneler paylaşımın sahipliğini kopyalar.

## <a name="iostream"></a>iostream

Standart ıostream `cin`nesneleri, `cerr` `cout` ,`wcout` ,,`wclog` ,,, ve diğer sınıflarla aynı kuralları izler, bu özel durum: `clog` `wcin` `wcerr` birden çok iş parçacığından bir nesneye yazma. Örneğin, iş parçacığı 1, iş parçacığı 2 ile aynı anda [cout](../standard-library/iostream.md#cout) 'a yazabilir. Ancak, bu iki iş parçacığından çıkışın birbirine karışmasına neden olabilir.

> [!NOTE]
> Akış arabelleğinden okuma, okuma işlemi olarak kabul edilmez. Bunun yerine, sınıfın durumu değiştiğinden bir yazma işlemi olarak kabul edilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)
