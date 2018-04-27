---
title: C++ Kitaplık kuralları | Microsoft Docs
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
- C++ Standard Library, conventions
- classes [C++]
- functions [C++], library naming conventions
- naming conventions [C++], C++ Standard Library
- conventions [C++], C++ Standard Library
- function names [C++]
- coding conventions, C++ Standard Library
- naming conventions [C++], C++ library
ms.assetid: bf41b79a-2d53-4f46-8d05-779358335146
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7a43c250ef660257b62afb02ba6759d572c60a69
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="c-library-conventions"></a>C++ Kitaplığı Kuralları

C++ Kitaplığı standart C kitaplığı ile çok aynı kuralları obeys artı birkaç daha Burada özetlenen.

Bir uygulamaya nasıl türler ve İşlevler C++ Kitaplığı'nda bildirir, belirli enlem sahiptir:

- Standart C Kitaplığı'nda işlevlerin adları extern #"C++" veya "C" bağlantı extern olabilir. Uygun standart C üstbilgisini yerine bir kitaplık varlık satır içi bildirin.

- Bir kitaplık sınıfından bir üye işlev adı, bu belgede listelenenler üzerinden ek işlevi imzaları olabilir. Burada açıklanan bir işlev çağrısı beklendiği gibi davranır, ancak kitaplığı üye işlevi adresini güvenilir bir şekilde alamıyor emin olabilirsiniz. (Türü, beklediğiniz olmayabilir.)

- Bir kitaplık sınıfından belgelenmemiş (sanal olmayan) temel sınıflar olabilir. Başka bir sınıftan türetildiği gibi belgelenen türetilmiş bir sınıf aslında, bu sınıftan başka belgelenmemiş sınıflarıyla olabilir.

- Bazı tamsayı türü eşanlamlısı olarak tanımlanan bir türü birkaç farklı tamsayı türlerinden biri ile aynı olabilir.

- Bir bit maskesi türü, bir tamsayı yazın veya bir sabit listesi uygulanabilir. Her iki durumda da bit düzeyinde işlemler gerçekleştirebilirsiniz (gibi `AND` ve `OR`) aynı bit maskesi türü değerleri. Öğeleri `A` ve `B` bir bit maskesi türü sıfır olmayan değerler şekilde `A`  &  `B` sıfırdır.

- Tanımına açıkça böyle bir olasılık kısıtlayan sürece hiçbir özel durum belirtimi olan bir kitaplık işlev rasgele bir özel durum.

Diğer taraftan, bazı sınırlamalar vardır:

- Standart C Kitaplığı maskeleme makroları kullanır. Yalnızca belirli işlev imzaları ayrılmış, adları işlevlerin kendilerini değil.

- Bir sınıf dışında bir kitaplık işlevi adı ek, belgelenmemiş, işlevi imzaları sahip olmaz. Adresini güvenilir bir şekilde alabilir.

- Temel sınıflar ve sanal olarak açıklanan üye işlevleri sırasında assuredly sanal olarak sanal olmayan açıklanan assuredly sanal olmayan olanlardır.

- Aksi takdirde bu belgeyi açıkça öneren sürece C++ Kitaplık tarafından tanımlanan iki tür her zaman farklıdır.

- Değiştirilebilir İşlevler, varsayılan sürümleri dahil olmak üzere kitaplığı tarafından sağlanan işlevleri throw *en fazla* filtrenizin listelenen tüm özel durum belirtimi. Kitaplığı tarafından sağlanan hiçbir Yıkıcılar özel durumlar oluşturma. İşlevler standart C Kitaplığı'nda bir özel durum olarak ne zaman yayılması `qsort` bir karşılaştırma işlev çağrıları bir özel durum oluşturur, ancak Aksi durumda özel durumlar oluşturmayın.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
