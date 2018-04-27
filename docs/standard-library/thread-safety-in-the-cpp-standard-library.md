---
title: C++ Standart kitaplığında iş parçacığı güvenliği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- thread safety
- C++ Standard Library, thread safety
- thread safety, C++ Standard Library
ms.assetid: 9351c8fb-4539-4728-b0e9-226e2ac4284b
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bad79ad237e388167a747d6af662fff3d9d05497
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="thread-safety-in-the-c-standard-library"></a>C++ Standart Kitaplığında İş Parçacığı Güvenliği

C++ Standart Kitaplığı'ndaki tüm sınıflar aşağıdaki iş parçacığı güvenliği kurallar geçerlidir — bu içerir `shared_ptr`, aşağıda açıklandığı gibi.  Daha güçlü garanti bazen sağlanan — Örneğin, standart iostream, aşağıda açıklandığı gibi nesneleri, özellikle yönelik türlerini ve çoklu iş parçacığı kullanımı, ister de [ \<atomik >](../standard-library/atomic.md).

İş parçacığı bir nesne için birden çok iş parçacığı okuma. Örneğin, bir nesne A göz önüne alındığında, bir iş parçacığı 1 ve 2 iş parçacığı aynı anda okumak güvenli değildir.

Bir nesnenin üzerine yazılan, tek bir iş parçacığı tarafından sonra tüm okur ve bu nesneye aynı yazar veya başka bir iş parçacığı korunması gerekir. Örneğin, iş parçacığı 1 yazma işlemi için bir nesne A, verilen, sonra iş parçacığı 2 okuma veya yazma A'ya engellenmelidir

Okuma ve başka bir iş parçacığı okuma ya da aynı türde başka bir örneğine yazma olsa bile bir türünün bir örneği yazma güvenlidir. Örneğin, A ve B aynı türde nesneler belirtilen, onu 1 iş parçacığında yazılmış A ve B 2 iş parçacığında okuma güvenlidir.

## <a name="sharedptr"></a>shared_ptr

Birden çok iş parçacığı, aynı anda okuma ve yazma farklı [shared_ptr](../standard-library/shared-ptr-class.md) nesnelerin sahipliği paylaşmak kopyaları olduğunda bile nesneleri.

## <a name="iostream"></a>iostream

Standart iostream nesneleri `cin`, `cout`, `cerr`, `clog`, `wcin`, `wcout`, `wcerr`, ve `wclog` bu durumla diğer sınıflar olarak aynı kurallarına: için güvenlidir bir nesne için birden çok iş parçacığından yazma. Örneğin, iş parçacığı 1 üzerine yazabilirler [cout](../standard-library/iostream.md#cout) aynı anda farklı iş parçacığı 2. Ancak, bu çıkış iki parçacıklarından intermixed neden olabilir.

> [!NOTE]
> Bir Akış Arabellek Okuma okuma işlemi olarak kabul değil. Bunun yerine, sınıfının durumu değiştiğinden bir yazma işlemi olarak kabul edilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
