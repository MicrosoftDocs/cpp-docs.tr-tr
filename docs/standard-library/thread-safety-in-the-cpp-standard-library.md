---
title: C++ Standart Kitaplığında İş Parçacığı Güvenliği
ms.date: 11/04/2016
helpviewer_keywords:
- thread safety
- C++ Standard Library, thread safety
- thread safety, C++ Standard Library
ms.assetid: 9351c8fb-4539-4728-b0e9-226e2ac4284b
ms.openlocfilehash: 27ac930e567521b12dfc35e2f8c4c389c35ae47d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607642"
---
# <a name="thread-safety-in-the-c-standard-library"></a>C++ Standart Kitaplığında İş Parçacığı Güvenliği

C++ Standart Kitaplığı'ndaki tüm sınıflar aşağıdaki iş parçacığı güvenliği kurallar uygulanır; Bu içerir `shared_ptr`, aşağıda açıklandığı gibi.  Daha güçlü garanti bazen sağlanan — Örneğin, standart iostream aşağıda açıklandığı gibi nesneleri ve özellikle yönelik türleri çoklu iş parçacığı kullanımı, ister de [ \<atomik >](../standard-library/atomic.md).

İş parçacığı açısından güvenli bir nesnedir birden çok iş parçacığından okuma için. Örneğin, bir nesneyi göz önünde bulundurulduğunda, bir iş parçacığından 1 ve 2 iş parçacığından aynı anda okuma sakınca yoktur.

Bir nesne üzerine yazılan, tek bir iş parçacığı tarafından sonra tüm okur ve bu nesneyi aynı yazar veya diğer iş parçacıklarını korunması gerekir. Örneğin, A-1 iş parçacığı yazıyorsanız, bir nesneyi göz önünde bulundurulduğunda, ardından iş parçacığı 2 okuma veya yazma A'ya çözümleyebilmeleri

Okumak ve başka bir iş parçacığı okuma veya yazma farklı bir örneğine aynı türde olsa bile, bir türün bir örneğini yazmak güvenlidir. Örneğin, A ve B aynı türde nesneleri göz önünde bulundurulduğunda, 1 iş parçacığında yazılan A ve B 2 iş parçacığında okunan güvenlidir.

## <a name="sharedptr"></a>shared_ptr

Birden çok iş parçacığı, aynı anda okuma ve yazma farklı [shared_ptr](../standard-library/shared-ptr-class.md) nesneler bu paylaşım sahipliğinin kopyası olsa bile nesneleri.

## <a name="iostream"></a>iostream

Standart iostream nesneleri `cin`, `cout`, `cerr`, `clog`, `wcin`, `wcout`, `wcerr`, ve `wclog` bu durumla diğer sınıflar olarak aynı kurallara uymanız: Güvenli bir nesneye birden fazla iş parçacığından yazın. Örneğin, 1 iş parçacığı için yazabilirsiniz [cout](../standard-library/iostream.md#cout) aynı anda farklı iş parçacığı 2. Ancak, bu Çıktıyı karıştırılmış için iki iş parçacıklarından neden olabilir.

> [!NOTE]
> Bir akış arabelleğinin Okuma okuma işlemi olarak dikkate alınmaz. Bunun yerine bu sınıfı durumunu değiştiğinden bir yazma işlemi olarak değerlendirilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
