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
ms.openlocfilehash: b9841d1045a6d2d1126414f1ce4cfc93f9667eef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362376"
---
# <a name="using-c-library-headers"></a>C++ Kitaplığı Üstbilgilerini Kullanma

Standart üst bilgi içeriği, yönergesinde adlandırarak içerir.

```cpp
#include <iostream>// include I/O facilities
```

Herhangi bir sırada, birden fazla kez standart üst bilgi veya aynı makrosu veya aynı türü tanımlayan iki veya daha fazla standart üstbilgileri, standart üstbilgi ekleyebilirsiniz. Bir bildirimi içinde standart bir başlık dahil değildir. Standart bir başlık dahil etmeden önce aynı adları olarak anahtar sözcükler makroları tanımlamaz.

C++ Kitaplığı üstbilgi gereken türleri tanımlamak için gerekli herhangi diğer C++ Kitaplığı üstbilgilerini içerir. (Gerçek bağımlılıkları hakkında yanlış tahmin ekleyin her zaman bir çeviri biriminde, ancak gerekli açıkça bir C++ Kitaplığı üst bilgileri ekleyin.) Standart C üstbilgi hiçbir zaman başka bir standart üst bilgi içerir. Standart üst bilgi bildirir veya yalnızca kendisi için bu belgede açıklanan varlıklar tanımlayan.

Standart bir üst bilgisinde her işlev Kitaplığı'nda bildirilir. Farklı olarak standart C, standart üstbilgi hiçbir işlev bildirimi maskeleri ve aynı etkiyi elde işlevi olarak aynı ada sahip bir maskeleme makrosu sağlar. Makrolar maskeleme daha fazla bilgi için bkz: [C++ Kitaplık kuralları](../standard-library/cpp-library-conventions.md).

Dışındaki tüm adları **delete işleci** ve **new işleci** üstbilgileri tanımlanan C++ Kitaplığı'nda `std` ad veya içinde iç içe geçmiş ad alanında `std` ad alanı. Adına başvurmak `cin`, örneğin, olarak `std::cin`. , Ancak her zaman yazmak için makro adları ad niteliği tabi değildir `__STD_COMPLEX` ad alanı niteleyicisi olmayan.

Bazı çeviri ortamlarda, bir C++ Kitaplığı üst bilgisi dahil olmak üzere bildirilen dış adların çekmek `std` ad da genel ad alanına kişi ile **kullanarak** her adları bildirimleri. Aksi takdirde, üst bilgi vermez *değil* herhangi bir kitaplık adı geçerli bir ad alanına tanıtır.

C++ Standart C Standart üstbilgi tüm dış adların ad alanında bildirilmesini gerektirir `std`, kişi ile küresel ad alanına çekmek **kullanarak** her adları bildirimleri. Ancak, bazı standart C çeviri ortamlar doğrudan genel ad alanındaki tüm adları bildirme hiçbir ad alanı bildirimi, üst bilgileri ekleyin. Bu nedenle, ad alanları ile dağıtılacak en taşınabilir yolu iki kural takip etmektir:

- Ad alanında assuredly bildirmek için `std` , geleneksel olarak bildirilen bir dış ad \<stdlib.h >, örneğin üstbilgisini \<cstdlib >. Adı aynı zamanda genel ad alanında bildirilmesini bildirin.

- Genel ad alanında bildirilen bir dış ad assuredly bildirmek için \<stdlib.h >, üstbilgisini \<stdlib.h > doğrudan. Ad ayrıca ad alanında bildirilmesini bilmeniz `std`.

Bu nedenle, arama istiyorsanız `std::abort` olağan dışı sonlandırma neden olmak için içermelidir \<cstdlib >. Çağrı istiyorsanız `abort`, içermesi gerekir \<stdlib.h >.

Alternatif olarak, bildirimi yazabilirsiniz:

```cpp
using namespace std;
```

Bu geçerli bir ad alanına tüm kitaplık adlarını getirir. Bu bildirim yazarsanız hemen sonra yönergelerinde, adları genel ad alanına çekmek. Daha sonra çeviri biriminin geri kalanında ad alanı konuları yoksayabilirsiniz. Ayrıca farklı çeviri ortamlar genelinde çoğu farklılığın kaçının.

Özellikle belirtilmedikçe adlarında tanımlayamaz `std` ad veya içinde iç içe geçmiş ad alanında `std` programınızdan ad alanı.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
