---
description: 'Daha fazla bilgi edinin: C++ kitaplığı kuralları'
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
ms.openlocfilehash: 4426996b7420c056a964378655c72c43b99fcf97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233376"
---
# <a name="c-library-conventions"></a>C++ Kitaplığı Kuralları

C++ Kitaplığı, standart C Kitaplığı ile aynı kurallara ek olarak, burada daha fazla anahatlı bir şekilde ele geçer.

Uygulama, C++ kitaplığındaki türleri ve işlevleri nasıl bildirdiğinden belirli Enlem içerir:

- Standart C kitaplığındaki işlevlerin adları extern "C++" veya extern "C" bağlantısına sahip olabilir. Satır içi bir kitaplık varlığı bildirmek yerine uygun standart C üst bilgisini ekleyin.

- Bir kitaplık sınıfındaki üye işlev adı, bu belgede listelenenlerin üzerinde ek işlev imzaları içerebilir. Burada açıklanan bir işlev çağrısının beklenen şekilde davrandığından emin olabilirsiniz, ancak bir kitaplık üye işlevinin adresini güvenilir bir şekilde kullanamazsınız. (Tür, beklediğiniz gibi olmayabilir.)

- Bir kitaplık sınıfında belgelenmemiş (sanal olmayan) temel sınıflar olabilir. Başka bir sınıftan türetilmiş olarak belgelenmiş bir sınıf, aslında belgelenmemiş diğer sınıflar aracılığıyla bu sınıftan türetilebilir.

- Bazı tamsayı türleri için eş anlamlı olarak tanımlanan bir tür, birkaç farklı tamsayı türünden biriyle aynı olabilir.

- Bir bit maskesi türü, bir tamsayı türü veya bir numaralandırma olarak uygulanabilir. Her iki durumda da, `AND` `OR` aynı bit maskesi türünde değerler üzerinde bit düzeyinde işlemler (ve gibi) gerçekleştirebilirsiniz. `A` `B` Bir bit maskesi türü öğeleri ve sıfır olmayan değerlerdir `A`  &  `B` .

- Özel durum belirtimi olmayan bir kitaplık işlevi, tanımı açıkça böyle bir olasılıkla kısıtlanmadığı takdirde rastgele bir özel durum oluşturabilir.

Öte yandan, bazı kısıtlamalar vardır:

- Standart C Kitaplığı maskeleme makrosu kullanmaz. Yalnızca belirli işlev imzaları ayrılmıştır, işlevlerin kendilerine ait adları değildir.

- Sınıf dışında bir kitaplık işlevi adının ek, belgelenmemiş işlev imzaları olmayacaktır. Adresini güvenilir bir şekilde alabilirsiniz.

- Sanal olarak tanımlanan temel sınıflar ve üye işlevleri assuredly sanal, ancak sanal olmayan olarak açıklanan assuredly sanal değildir.

- C++ Kitaplığı tarafından tanımlanan iki tür bu belge açıkça belirtilmedikçe her zaman farklıdır.

- Değiştirilebilir işlevlerin varsayılan sürümleri de dahil olmak üzere, kitaplık tarafından sağlanan işlevler, herhangi bir özel durum belirtiminde listelenen özel durumların *çoğunu* oluşturabilir. Kitaplık tarafından sağlanan hiçbir yok edici özel durum oluşturmaz. Standart C kitaplığındaki işlevler, `qsort` özel durum oluşturan bir karşılaştırma işlevi çağırdığında olduğu gibi bir özel durum yayabilir, ancak Aksi takdirde özel durum oluşturmaz.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
