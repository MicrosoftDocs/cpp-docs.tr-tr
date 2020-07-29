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
ms.openlocfilehash: a73ebebb4fdde5dd72f148390d004c32b9f4dff7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215484"
---
# <a name="using-c-library-headers"></a>C++ Kitaplığı Üstbilgilerini Kullanma

Bir Include yönergesinde adlandırarak standart bir üstbilginin içeriğini dahil edersiniz.

```cpp
#include <iostream>// include I/O facilities
```

Standart üst bilgileri herhangi bir sıraya, standart bir üst bilgiye veya aynı makroyu ya da aynı türü tanımlayan iki ya da daha fazla standart üstbilgiye dahil edebilirsiniz. Bir bildirime standart üst bilgi eklemeyin. Standart bir üst bilgi eklemeden önce, anahtar sözcüklerle aynı ada sahip makroları tanımlamayın.

C++ Kitaplığı üst bilgisi, gereken türleri tanımlamak için gereken diğer C++ Kitaplığı üstbilgilerini içerir. (Bir çeviri biriminde gereken tüm C++ Kitaplığı üstbilgilerini her zaman ekleyin, ancak gerçek bağımlılıklarıyla ilgili olarak yanlış tahmin edersiniz.) Standart bir C üst bilgisi hiçbir şekilde başka bir standart üstbilgi dahil değildir. Standart üst bilgi, yalnızca bu belgede açıklanan varlıkları bildirir veya tanımlar.

Kitaplıktaki her işlev standart bir üst bilgide bildirilmiştir. Standart C 'nin aksine, standart üst bilgi, işlev bildirimini maskelerden ve aynı etkiye sahip olan işlevle aynı ada sahip bir maskeleme makrosu sağlamaz. Maskeleme makroları hakkında daha fazla bilgi için bkz. [C++ kitaplık kuralları](../standard-library/cpp-library-conventions.md).

C++ Kitaplığı başlıklarındaki **Delete** ve **New işleci** dışındaki tüm adlar `std` ad alanında veya ad alanı içinde iç içe yerleştirilmiş bir ad alanında tanımlanır `std` . Adına ( `cin` Örneğin,) başvurabilirsiniz `std::cin` . Ancak, makro adları ad alanı niteleyiciye tabi olmadığından, her zaman `__STD_COMPLEX` bir ad alanı niteleyicisi olmadan yazmanız gerektiğini unutmayın.

Bazı çeviri ortamlarında, bir C++ Kitaplığı üst bilgisi de dahil olmak üzere ad alanında belirtilen dış adları `std` genel ad alanına ve **`using`** her bir ad için tek tek bildirimlerle birlikte barındırmayabilir. Aksi takdirde, üst bilgi geçerli ad alanına herhangi bir kitaplık *adı sunmaz.*

C++ standardı, C standart üstbilgilerinin ad alanındaki tüm dış adları belirtmesini `std` ve sonra bunları **`using`** her bir ad için bireysel bildirimlerle genel ad alanına geri bildirmelerini gerektirir. Ancak bazı çeviri ortamlarında, tüm adları doğrudan genel ad alanında bildiren C standart üstbilgileri ad alanı bildirimleri içermez. Bu nedenle, ad alanları ile başa çıkmak için en taşınabilir yol iki kurala uymalıdır:

- Ad alanı içinde,, `std` Örneğin, içinde içinde bildirildiği bir dış ad ad alanında bildirmek için, \<stdlib.h> başlığını ekleyin \<cstdlib> . Adın genel ad alanında da bildirilebilecek olduğunu öğrenin.

- Genel ad alanında, içinde bildirildiği bir dış adın assuredly bildirmek için \<stdlib.h> , üstbilgiyi doğrudan ekleyin \<stdlib.h> . Adın ad alanında da bildirilebilecek olabileceğini öğrenin `std` .

Bu nedenle, `std::abort` olağan dışı sonlandırmanın nedenini çağırmak isterseniz, dahil etmelisiniz \<cstdlib> . Çağırmak isterseniz `abort` , dahil etmelisiniz \<stdlib.h> .

Alternatif olarak, bildirimini de yazabilirsiniz:

```cpp
using namespace std;
```

Tüm kitaplık adlarını geçerli ad alanına getiren. Bu bildirimi tüm dahil etme yönergelerinden hemen sonra yazarsanız, adları genel ad alanına barındırın. Daha sonra, çeviri biriminin geri kalanında ad alanı konularını yoksayabilirsiniz. Ayrıca, farklı çeviri ortamlarında birçok farkı önleyin.

Özellikle belirtilmedikçe, `std` ad alanında veya ad alanı içinde iç içe yerleştirilmiş bir ad alanında, `std` programınızın içinden ad tanımlayamazsınız.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
