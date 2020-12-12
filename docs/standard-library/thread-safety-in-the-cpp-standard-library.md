---
description: Daha fazla bilgi için bkz. C++ standart kitaplığı 'nda Iş parçacığı güvenliği
title: C++ Standart Kitaplığında İş Parçacığı Güvenliği
ms.date: 11/04/2016
helpviewer_keywords:
- thread safety
- C++ Standard Library, thread safety
- thread safety, C++ Standard Library
ms.assetid: 9351c8fb-4539-4728-b0e9-226e2ac4284b
ms.openlocfilehash: ff5d8960b2fc8a79acbfb4fc1d0be508865714e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289640"
---
# <a name="thread-safety-in-the-c-standard-library"></a>C++ Standart Kitaplığında İş Parçacığı Güvenliği

Aşağıdaki iş parçacığı güvenlik kuralları, C++ standart kitaplığı 'ndaki tüm sınıflar için geçerlidir. Bu, `shared_ptr` aşağıda açıklandığı gibi dahildir.  Daha güçlü garantiler bazen verilmiştir — Örneğin, aşağıda açıklandığı gibi standart iostream nesneleri ve ' de olduğu gibi, çoklu iş parçacığı için tasarlanan türler [\<atomic>](../standard-library/atomic.md) .

Bir nesne birden çok iş parçacığından okumak için iş parçacığı güvenlidir. Örneğin, A nesnesi verildiğinde, bir iş parçacığı 1 ve iş parçacığı 2 ' den aynı anda okumak güvenlidir.

Bir nesne bir iş parçacığı tarafından yazılmışsa, bu nesneye aynı veya diğer iş parçacıklarında yapılan tüm okuma ve yazma işlemleri korunmuş olmalıdır. Örneğin, A nesnesi verildiğinde, iş parçacığı 1 öğesine yazuyorsa, iş parçacığının 2 ' den okunmasından veya bir öğesine yazmasını önlenmelidir.

Başka bir iş parçacığı aynı türden farklı bir örneğe okuma veya yazma olsa da, bir türün bir örneğini okumak ve yazmak güvenlidir. Örneğin, A ve B nesneleri aynı türde olduğunda, iş parçacığı 1 ' de yazıldığı ve B iş parçacığı 2 ' de okunduğunda bu güvenli bir seçenektir.

## <a name="shared_ptr"></a>shared_ptr

Birden çok iş parçacığı, nesneler paylaşımın sahipliğini kopyaladığında bile farklı [shared_ptr](../standard-library/shared-ptr-class.md) nesneleri aynı anda okuyabilir ve yazabilir.

## <a name="iostream"></a>iostream

Standart iostream nesneleri,,,,,, `cin` `cout` `cerr` `clog` `wcin` `wcout` `wcerr` ve `wclog` diğer sınıflarla aynı kurallara uyar, bu özel durum: bir nesneye birden çok iş parçacığından yazmak güvenlidir. Örneğin, iş parçacığı 1, iş parçacığı 2 ile aynı anda [cout](../standard-library/iostream.md#cout) 'a yazabilir. Ancak, bu iki iş parçacığından çıkışın birbirine karışmasına neden olabilir.

> [!NOTE]
> Akış arabelleğinden okuma, okuma işlemi olarak kabul edilmez. Bunun yerine, sınıfın durumu değiştiğinden bir yazma işlemi olarak kabul edilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)
