---
title: "C++ Kitaplığı üstbilgilerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- headers, naming in C++ include directive
- standard header in C++
- headers
- INCLUDE directive
- headers, C++ Standard Library
- library headers
- C++ Standard Library, headers
ms.assetid: a36e889e-1af2-4cd9-a211-bfc7a3fd8e85
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a90218b8cfc0dcc23475bb5e9fb531b2cebe4078
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-c-library-headers"></a>C++ Kitaplığı Üstbilgilerini Kullanma
Standart üstbilginin içeriği, bir içerme yönergesi adlandırılmasıyla içerir.  
  
```  
#include <iostream>// include I/O facilities  
```  
  
 Herhangi bir sırada, birden fazla kez standart üstbilgi veya aynı makrosu veya aynı türde tanımlayan iki veya daha fazla standart üstbilgileri standart üstbilgileri dahil edebilirsiniz. Bir bildirimi içinde standart üstbilgi içermez. Anahtar sözcükler aynı adları standart üstbilgi dahil etmeden önce olan makroları tanımlamayın.  
  
 C++ Kitaplık üstbilgi gerekli türlerini tanımlamak için gereken tüm diğer C++ Kitaplığı üstbilgilerini içerir. (Gerçek bağımlılıklarını hakkında yanlış tahmin ekleyin her zaman bir çeviri biriminde, ancak gerekli açıkça tüm C++ Kitaplığı üstbilgilerini ekleyin.) Bir standart C üstbilgisi hiçbir zaman başka bir standart üstbilgi içerir. Standart üstbilgi bildirir veya yalnızca kendisi için bu belgede açıklanan varlıklar tanımlar.  
  
 Her işlev Kitaplığı'nda da standart üstbilgi bildirildi. Aksine standart C'de standart üstbilgi hiçbir zaman işlevi bildirimi maskeleri ve aynı etkiye başarır işlev aynı ada sahip bir maskeleme makro sağlar. Makrolar maskeleme daha fazla bilgi için bkz: [C++ Kitaplık kuralları](../standard-library/cpp-library-conventions.md).  
  
 Dışındaki tüm adlar `operator delete` ve `operator new` C++ Kitaplığı'nda üstbilgileri tanımlanan `std` ad alanı, veya içinde iç içe bir ad alanındaki `std` ad alanı. Adına başvuran `cin`, örneğin, olarak `std::cin`. Ancak, her zaman yazma şekilde makrosu adlarının ad niteliği tabi olmadığını unutmayın `__STD_COMPLEX` ad alanı niteleyicisi olmadan.  
  
 Bazı çeviri ortamlarda C++ Kitaplık üstbilgi dahil dış adlar bildirilen vinç `std` ad alanına genel ad alanı de, tek tek ile `using` adlarının her biri için bildirimleri. Aksi takdirde, üstbilgi mu *değil* tüm kitaplık adları geçerli ad alanına tanıtır.  
  
 C Standart üstbilgi ad alanındaki tüm dış adların bildirme C++ Standart gerektirir `std`, tek tek ile genel ad alanı içine vinç `using` adlarının her biri için bildirimleri. Ancak bazı çeviri ortamlarda C Standart üst bilgiler tüm adlarında doğrudan genel ad alanı bildirme hiçbir ad alanı bildirimi içerir. Bu nedenle, ad alanları ile mücadele etmek için en taşınabilir yolu iki kural izlemektir:  
  
-   Ad alanında assuredly bildirmek için `std` geleneksel içinde bildirilen harici bir ad \<stdlib.h >, örneğin, üstbilgisini \<cstdlib >. Adı da genel ad alanında bildirilmesi gereken bilirsiniz.  
  
-   Genel ad alanında bildirilen dış adı assuredly bildirmek için \<stdlib.h >, üstbilgisini \<stdlib.h > doğrudan. Adı da ad alanında bildirilmesi gereken bilmeniz `std`.  
  
 Bu nedenle, çağrı istiyorsanız `std::abort` anormal sonlandırma neden olmak için içermelidir \<cstdlib >. Çağrı istiyorsanız `abort`, içermesi gerekir \<stdlib.h >.  
  
 Alternatif olarak, bildirim yazabilirsiniz:  
  
```  
using namespace std;  
```  
  
 hangi tüm kitaplık adları geçerli ad alanına getirir. Bu bildirim yazarsanız genel ad alanına adları vinç, hemen sonra tüm yönergeleri içerir. Daha sonra geri kalan ad alanı konuları çeviri biriminin yoksayabilirsiniz. Ayrıca farklı çeviri ortamlar genelinde çoğu farklar kaçının.  
  
 Özellikle belirtilmedikçe adlarında tanımlayamaz `std` ad alanı, veya içinde iç içe bir ad alanındaki `std` programınızdan ad alanı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

