---
title: C++ Kitaplığı Üstbilgilerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- headers, naming in C++ include directive
- standard header in C++
- headers
- INCLUDE directive
- headers, C++ Standard Library
- library headers
- C++ Standard Library, headers
ms.assetid: a36e889e-1af2-4cd9-a211-bfc7a3fd8e85
ms.openlocfilehash: 9cc0bb51b159f6668adad05ebd2d386364ae2f81
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450069"
---
# <a name="using-c-library-headers"></a>C++ Kitaplığı Üstbilgilerini Kullanma

Bir Include yönergesinde adlandırarak standart bir üstbilginin içeriğini dahil edersiniz.

```cpp
#include <iostream>// include I/O facilities
```

Standart üst bilgileri herhangi bir sıraya, standart bir üst bilgiye veya aynı makroyu ya da aynı türü tanımlayan iki ya da daha fazla standart üstbilgiye dahil edebilirsiniz. Bir bildirime standart üst bilgi eklemeyin. Standart bir üst bilgi eklemeden önce, anahtar sözcüklerle aynı ada sahip makroları tanımlamayın.

C++ Kitaplık üst bilgisi, gereken türleri C++ tanımlamak için gereken diğer kitaplık üstbilgilerini içerir. (Bir çeviri biriminde gereken C++ tüm kitaplık üstbilgilerini her zaman ekleyin, ancak gerçek bağımlılıklarıyla ilgili olarak yanlış tahmin edersiniz.) Standart bir C üst bilgisi hiçbir şekilde başka bir standart üstbilgi dahil değildir. Standart üst bilgi, yalnızca bu belgede açıklanan varlıkları bildirir veya tanımlar.

Kitaplıktaki her işlev standart bir üst bilgide bildirilmiştir. Standart C 'nin aksine, standart üst bilgi, işlev bildirimini maskelerden ve aynı etkiye sahip olan işlevle aynı ada sahip bir maskeleme makrosu sağlamaz. Maskeleme makroları hakkında daha fazla bilgi için bkz [ C++ . kitaplık kuralları](../standard-library/cpp-library-conventions.md).

C++ Kitaplık`std` başlıklarındaki **işleç Delete** ve **New işleci** dışındaki tüm adlar ad alanında veya ad `std` alanı içinde iç içe yerleştirilmiş bir ad alanında tanımlanır. Adına `cin`(örneğin `std::cin`,) başvurabilirsiniz. Ancak, makro adları ad alanı niteleyiciye tabi olmadığından, her zaman bir ad alanı niteleyicisi olmadan `__STD_COMPLEX` yazmanız gerektiğini unutmayın.

Bazı çeviri ortamlarında, bir C++ kitaplık üstbilgisi de dahil olmak üzere `std` ad alanında belirtilen dış adları genel ad alanına ve her bir ada ait bildirimleri **kullanarak** barındırmayabilir. Aksi takdirde, üst bilgi geçerli ad alanına herhangi bir kitaplık *adı sunmaz.*

Standart C++ , C standart üstbilgilerinin ad alanındaki `std`tüm dış adları belirtmesini ve sonra her bir ad için bildirimleri **kullanarak** genel ad alanına barındırmasını gerektirir. Ancak bazı çeviri ortamlarında, tüm adları doğrudan genel ad alanında bildiren C standart üstbilgileri ad alanı bildirimleri içermez. Bu nedenle, ad alanları ile başa çıkmak için en taşınabilir yol iki kurala uymalıdır:

- Ad alanına `std` assuredly bildirmek için, \<Stdlib. h >, örneğin, cstdlib > üstbilgisini \<içeren bir dış addır. Adın genel ad alanında da bildirilebilecek olduğunu öğrenin.

- Genel ad alanında assuredly bildirmek için Stdlib. h > içinde \<belirtilen bir dış ad, doğrudan Stdlib. \<h > üstbilgisini ekleyin. Adın ad alanında `std`da bildirilebilecek olabileceğini öğrenin.

Bu nedenle, olağan dışı sonlandırmanın `std::abort` nedenini çağırmak istiyorsanız cstdlib > dahil \<etmelisiniz. Çağırmak `abort`istiyorsanız, Stdlib. h > dahil \<etmelisiniz.

Alternatif olarak, bildirimini de yazabilirsiniz:

```cpp
using namespace std;
```

Tüm kitaplık adlarını geçerli ad alanına getiren. Bu bildirimi tüm dahil etme yönergelerinden hemen sonra yazarsanız, adları genel ad alanına barındırın. Daha sonra, çeviri biriminin geri kalanında ad alanı konularını yoksayabilirsiniz. Ayrıca, farklı çeviri ortamlarında birçok farkı önleyin.

Özellikle belirtilmedikçe, `std` ad alanında veya ad alanı `std` içinde iç içe yerleştirilmiş bir ad alanında, programınızın içinden ad tanımlayamazsınız.

## <a name="see-also"></a>Ayrıca bkz.

[C++Standart kitaplığa genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
