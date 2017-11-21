---
title: "Kitaplık iç üzerinde bağımlılıklarınızı düzeltme | Microsoft Docs"
ms.custom: 
ms.date: 05/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- library internals in an upgraded Visual C++ project
- _Hash_seq in an upgraded Visual C++ project
ms.assetid: 493e0452-6ecb-4edc-ae20-b6fce2d7d3c5
caps.latest.revision: "1"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c356e5f7a8bdd9441e506c9ca30c34fa3c8d5144
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fix-your-dependencies-on-library-internals"></a>Kitaplık iç üzerinde bağımlılıklarınızı Düzelt

Microsoft, standart kitaplığı, C çalışma zamanı kitaplığı ve diğer Microsoft kitaplıkları birçok Visual Studio sürümlerinde çoğu için kaynak kodunu yayımladı. Amaç kitaplığı davranışı anlamanıza yardımcı olması için ve kodunuzun hatalarını ayıklamak için ' dir. Bunlar kitaplık arabiriminin parçası olmasa da bir yan-kitaplık kaynak kodu yayımlama bazı iç değerleri, veri yapılarını ve İşlevler sunulur olduğunu, etkisidir. Genellikle sahip oldukları iki alt çizgi ile başlayan adları veya alt çizgi uygulamaları için C++ Standart ayırır adları bir büyük harf ve ardından. Bu değerleri, yapılar ve işlevleri kitaplıklar zaman içerisinde geliştikçe ve bağımlılıkları üzerlerinde alma karşı önerilir şekilde değişebilir uygulama ayrıntılarını verilebilir. Bunu yaparsanız, kodunuzu kitaplıklarının yeni sürümlerini geçirmek çalıştığınızda, taşınabilir olmayan kod ve sorunları riski oluşur.  

Çoğu durumda, yenilikler veya Visual Studio her sürüm için yeni değişiklikler belge kitaplığı iç değişiklikler Bahsediyor değil. Sonuçta, bu uygulama ayrıntılarını tarafından etkilenen olması olduğunuz değil. Ancak, bazen gördüğünüz bazı kod kitaplığı içinde kullanmak için buradaki eðilim çok fazla olabilir. Bu konu, üzerinde dayanıyordu CRT veya standart kitaplığı iç Ayrıntılar ve daha taşınabilir olmasını ya da kitaplık yeni sürümlerini geçirmek bu bağımlılıkları kaldırmak için kodunuzu güncelleştirin nasıl bağımlılıklarını açıklamaktadır.

## <a name="hashseq"></a>_Hash_seq  

İç karma işlevi `std::_Hash_seq(const unsigned char *, size_t)`uygulamak için kullanılan `std::hash` bazı dize türleri üzerinde standart kitaplığı en güncel sürümlerini görünür oluştu. Uygulanan bu işlev bir [FNV 1a karma]( https://en.wikipedia.org/wiki/Fowler%E2%80%93Noll%E2%80%93Vo_hash_function) üzerinde bir karakter dizisi.  
  
Bu bağımlılığı kaldırmak için birkaç seçeneğiniz vardır.  

-   Maksadınızı koymak için ise bir `const char *` dizisi olarak aynı karma kodu makineler kullanarak sırasız bir kapsayıcı halinde `basic_string`, bunu kullanarak yapabilirsiniz `std::hash` geçen şablon aşırı bir `std::string_view`, bu karma kodu döndürür bir Taşınabilir yolu. Dize kitaplık kodu olabilir veya belirli karma algoritma bir bağımlılığı önlemek için en iyi yolu budur şekilde FNV 1a karma kullanımı gelecekte kalmamanız. 
  
-   Maksadınızı rasgele bellek bir FNV 1a karma değeri üretmek için ise, bu kodu kullanılabilir Github'da üzerinde yaptık [VCSamples]( https://github.com/Microsoft/vcsamples) bir tek başına üstbilgi dosyası deposunda [fnv1a.hpp](https://github.com/Microsoft/VCSamples/tree/master/VC2015Samples/_Hash_seq), bir altında[MIT lisansı](https://github.com/Microsoft/VCSamples/blob/master/license.txt). Biz de bir kopyasını burada size kolaylık sağlamak için dahil ettiğiniz. Etkilenen tüm kodu eklemek üstbilgi üstbilgi dosyası bu kodu kopyalayabilir ve sonra bulma ve değiştirme `_Hash_seq` tarafından `fnv1a_hash_bytes`. İç uygulamasında aynı davranışı elde edersiniz `_Hash_seq`. 

```cpp  
/*
VCSamples
Copyright (c) Microsoft Corporation
All rights reserved. 
MIT License
Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED *AS IS*, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
*/
#include <stddef.h>

inline size_t fnv1a_hash_bytes(const unsigned char * first, size_t count) {
#if defined(_WIN64)
    static_assert(sizeof(size_t) == 8, "This code is for 64-bit size_t.");
    const size_t fnv_offset_basis = 14695981039346656037ULL;
    const size_t fnv_prime = 1099511628211ULL;

#else /* defined(_WIN64) */
    static_assert(sizeof(size_t) == 4, "This code is for 32-bit size_t.");
    const size_t fnv_offset_basis = 2166136261U;
    const size_t fnv_prime = 16777619U;
#endif /* defined(_WIN64) */

    size_t result = fnv_offset_basis;
    for (size_t next = 0; next < count; ++next)
        {   // fold in another byte
        result ^= (size_t)first[next];
        result *= fnv_prime;
        }
    return (result);
}
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
  
[Visual C++'ın önceki sürümlerinden yükseltme projeleri](upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
[Olası yükseltme sorunlarını (Visual C++) genel bakış](overview-of-potential-upgrade-issues-visual-cpp.md)  
[Evrensel CRT kodunuzu yükseltme](upgrade-your-code-to-the-universal-crt.md)  
