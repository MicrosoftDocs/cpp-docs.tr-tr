---
title: Kitaplık içeriklerindeki bağımlılıklarınızı düzeltme | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- library internals in an upgraded Visual C++ project
- _Hash_seq in an upgraded Visual C++ project
ms.assetid: 493e0452-6ecb-4edc-ae20-b6fce2d7d3c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dc9ef70eb2cf93ee92e32514681ae1a80810eb2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069809"
---
# <a name="fix-your-dependencies-on-library-internals"></a>Kitaplık içeriklerindeki bağımlılıklarınızı düzeltme

Microsoft, standart kitaplık, C çalışma zamanı kitaplığı ve diğer birçok Visual Studio sürümlerinde Microsoft kitaplıkları çoğu için kaynak kodu yayımladı. Amaç, kitaplığı davranışı anlamanıza yardımcı olması için ve kodunuzda hata ayıklamayı ' dir. Bunlar kitaplık arabiriminin bir parçası değildir ancak bir yan-kitaplığı kaynak kodunu yayımlama bazı iç değerler, veri yapılarını ve işlevleri gösterildiğinden emin, etkisidir. Bunlar genellikle iki alt çizgi ile başlayan adları vardır ve bir büyük harf, uygulamaları için C++ standardındaki ayırır adları alt çizgi ardından. Bu değerler, yapılar ve İşlevler kitaplıkları zamanla değiştikçe ve tüm bağımlılıklar üzerinde alma karşı önerilir değiştirebilir uygulamasını ayrıntıları var. Bunu yaparsanız, kitaplıklarının yeni sürümleri için kodunuzu geçirme çalıştığınızda, taşınabilir olmayan kod ve sorunları riski oluşur.

Çoğu durumda, yenilikleri veya değişiklikleri kitaplığı iç işlevleri için Visual Studio'nun her sürümü için bozucu değişiklikler belge bahsetmek değil. Sonuçta, bu uygulama ayrıntılarını tarafından etkilendiği geç olduğunuz değil. Ancak, bazen dürtüsüne gördüğünüz bazı kod kitaplığı içinde kullanmak için çok büyük olabilir. Bu konu, CRT veya standart kitaplığı iç üzerinde yararlandı ve kodunuzun daha taşınabilir yapmak veya Kitaplığı'nın yeni sürümüne geçirmek üzere bu bağımlılıkları kaldırmak için güncelleştirme bağımlılıklarını açıklar.

## <a name="hashseq"></a>_Hash_seq

İç karma işlevi `std::_Hash_seq(const unsigned char *, size_t)`uygulamak için kullanılan `std::hash` bazı dize türleri üzerinde standart Kitaplığı'nın en son sürümlerde görünür oldu. Bu işlev, uygulanan bir [FNV 1a karma]( https://en.wikipedia.org/wiki/Fowler%E2%80%93Noll%E2%80%93Vo_hash_function) üzerinde bir karakter dizisi.

Bu bağımlılığı kaldırmak için birkaç seçenek vardır.

- Amacınız koymak için ise bir `const char *` dizisi olarak aynı karma kodu makineler kullanarak bir sırasız kapsayıcısına `basic_string`, kullanarak bunu yapabilirsiniz `std::hash` alan şablon aşırı yüklemesini bir `std::string_view`, bu karma kodu döndürür bir Taşınabilir yolu. Dize kitaplık kodu olabilir veya bu belirli karma algoritması bir bağımlılığı önlemek için en iyi yolu, bu nedenle FNV 1a karma kullanımını gelecekte ihtiyaç duyabilir değil.

- Amacınız, rastgele bir bellek FNV 1a karma oluşturmak için ise, bu kodu kullanılabilir içinde github'daki yaptık [VCSamples]( https://github.com/Microsoft/vcsamples) tek başına bir başlık dosyası, depoda [fnv1a.hpp](https://github.com/Microsoft/VCSamples/tree/master/VC2015Samples/_Hash_seq), altında bir [MIT lisansı](https://github.com/Microsoft/VCSamples/blob/master/license.txt). Bir kopyasını buradan size kolaylık sağlamak için de ekledik. Bu kod bir üstbilgi dosyasına kopyalayabilir, etkilenen herhangi bir kod için üst bilgi Ekle Bul ve Değiştir `_Hash_seq` tarafından `fnv1a_hash_bytes`. İçinde iç uygulama için aynı davranışı elde edecekleriniz `_Hash_seq`.

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
    {
        // fold in another byte
        result ^= (size_t)first[next];
        result *= fnv_prime;
    }
    return (result);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Kodunuzu Evrensel CRT’ye Yükseltme](upgrade-your-code-to-the-universal-crt.md)