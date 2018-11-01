---
title: C++ Kitaplığı Kuralları
ms.date: 11/04/2016
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
ms.openlocfilehash: f1790b75baea340d0b3ab1044290317055ac81d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524793"
---
# <a name="c-library-conventions"></a>C++ Kitaplığı Kuralları

C++ Kitaplık olarak standart C Kitaplığı çok aynı kuralları ilişkiden yanı sıra birkaç çok Burada özetlenen.

Uygulama türleri ve işlevleri C++ Kitaplığı'nda nasıl bildirir, belirli bir enlem sahiptir:

- Standart C Kitaplığı'nda işlevlerin adları extern #"C++" veya extern "C" bağlantısına sahip olabilir. Uygun standart C üstbilgisini yerine bir kitaplığı varlık satır içi bildirin.

- Bir kitaplık sınıfından bir üye işlev adı, bu belgede listelenen üzerinden ek işlev imzası olabilir. Burada açıklanan bir işlev çağrısı beklendiği gibi davranır, ancak güvenilir bir şekilde kitaplığı üye işlevin adresi alınamaz emin olabilirsiniz. (Tür, beklediğiniz olmayabilir.)

- Bir kitaplık sınıfından belgelenmemiş (sanal olmayan) temel sınıflar olabilir. Başka bir sınıftan türetildiği haliyle belgelenen türetilmiş bir sınıf aslında, bu sınıftan başka belgelenmemiş sınıflarıyla olabilir.

- Bazı tamsayı türünün eşanlamlısı olarak tanımlanan bir türü birkaç farklı tamsayı türleri biriyle aynı olabilir.

- Bir bit maskesi türünde bir tamsayı türü veya bir sabit listesi uygulanabilir. Her iki durumda da, bit düzeyinde işlemler gerçekleştirebilir (gibi `AND` ve `OR`) aynı bit maskesi türü değerleri. Öğeleri `A` ve `B` bir bit maskesi türü sıfır olmayan değerler sağlayacak şekilde `A`  &  `B` sıfırdır.

- Tanımı böyle bir olasılık NET bir şekilde kısıtlayan sürece hiçbir özel durum belirtimi var olan bir kitaplığı işlevi rastgele bir özel durum.

Öte yandan, bazı kısıtlamalar vardır:

- Standart C Kitaplığı hiçbir maskeleme makrolarını kullanır. Yalnızca belirli bir işlev imzaları ayrılmıştır, işlevlerin adları değil.

- Sınıf dışındaki bir kitaplık işlevi adı ek, belgelenmemiş, işlev imzaları yoktur. Güvenilir bir şekilde adresini alabilir.

- Temel sınıflar ve sanal olarak açıklanan üye işlevleri çalışırken assuredly sanal olarak sanal olmayan açıklanana assuredly sanal olmayan.

- Bu belge önerir açıkça Aksi takdirde iki C++ Kitaplığı tarafından tanımlanan her zaman farklıdır.

- Değiştirilebilir işlevlerin, varsayılan sürümleri dahil olmak üzere kitaplığı tarafından sağlanan işlevleri durum *en fazla* filtrenizin listelenen tüm özel durum belirtimi. Kitaplığı tarafından sağlanan hiçbir yok edicinin özel durumlar. Standart C Kitaplığı işlevleri olarak ne zaman bir özel durum yayma `qsort` karşılaştırma işlev çağrıları, bir özel durum oluşturur, ancak Aksi halde özel durumlar oluşturmayın.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
