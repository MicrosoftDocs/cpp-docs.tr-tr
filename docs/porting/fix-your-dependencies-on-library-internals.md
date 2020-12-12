---
description: 'Hakkında daha fazla bilgi edinin: C++ Kitaplığı iç işlevleri üzerinde bağımlılıklarınızı çözme'
title: C++ Kitaplığı iç yapıları üzerinde bağımlılıklarınızı çözme
ms.date: 05/24/2017
helpviewer_keywords:
- library internals in an upgraded Visual Studio C++ project
- _Hash_seq in an upgraded Visual Studio C++ project
ms.assetid: 493e0452-6ecb-4edc-ae20-b6fce2d7d3c5
ms.openlocfilehash: 5d9cbcdd039786c3f1bb637e6a59bcfce43bc883
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341548"
---
# <a name="fix-your-dependencies-on-c-library-internals"></a>C++ Kitaplığı iç yapıları üzerinde bağımlılıklarınızı çözme

Microsoft, Visual Studio 'nun birçok sürümündeki standart kitaplık, C çalışma zamanı kitaplığı ve diğer Microsoft kitaplıklarını için kaynak kodu yayımlamıştır. Amaç, kitaplık davranışını anlamanıza ve kodunuzda hata ayıklamanıza yardımcı olur. Kitaplık kaynak kodunu yayımlamanın bir yan etkisi, kitaplık arabiriminin bir parçası olmasalar bile bazı iç değerler, veri yapıları ve işlevlerin açığa çıkmasıdır. Genellikle iki alt çizgi ile başlayan adlara sahiptir veya bir alt çizgi ve ardından büyük harfle gelir, C++ standardının uygulamalar için ayırdıkları adlar vardır. Bu değerler, yapılar ve işlevler, kitaplıklar zaman içinde geliştikçe değişebilir ve bu nedenle bunlar üzerinde herhangi bir bağımlılık yapmanız önemle önerilir. Bunu yaparsanız, kodunuzu kitaplıkların yeni sürümlerine geçirmeye çalıştığınızda taşınabilir olmayan kod ve sorunlarla karşılaşırsınız.

Çoğu durumda, Visual Studio 'nun her sürümü için yeni veya Son değişiklik belgesi, kitaplık iç yapıları üzerinde değişiklik yapmaz. Bunların ardından, bu uygulama ayrıntılarından etkilenmezsiniz. Ancak, bazen kitaplığın içinde görebileceğiniz bazı kodları kullanmak çok büyük olabilir. Bu konu, CRT veya standart kitaplık iç işlevleri üzerindeki bağımlılıkları ve bu bağımlılıkları kaldırmak için kodunuzu nasıl güncelleşreceğinizi, böylece daha taşınabilir hale getirebilirsiniz veya yeni bir kitaplık sürümüne geçiş yapabilirsiniz.

## <a name="_hash_seq"></a>_Hash_seq

`std::_Hash_seq(const unsigned char *, size_t)`Bazı dize türlerinde uygulamak için kullanılan iç karma işlevi `std::hash` , standart kitaplığın son sürümlerinde görünür. Bu işlev bir karakter dizisinde bir [FNV-1a karması]( https://en.wikipedia.org/wiki/Fowler%E2%80%93Noll%E2%80%93Vo_hash_function) uyguladık.

Bu bağımlılığı kaldırmak için birkaç seçeneğiniz vardır.

- Amacınızda `const char *` aynı karma kod makineleriyle sıralanmamış bir kapsayıcıya bir sıra koymak istiyorsanız `basic_string` , bu `std::hash` `std::string_view` karma kodu taşınabilir bir şekilde döndüren bir olan şablon aşırı yüklemesini kullanarak yapabilirsiniz. Dize kitaplığı kodu, gelecekte bir FNV-1a karmasının kullanılmasına yol açabilir veya bu nedenle, belirli bir karma algoritmadan bağımlılığı önlemenin en iyi yoludur.

- Amacınızı rastgele bellek üzerinde bir FNV-1a karması oluşturmak istiyorsanız, bu kodu, bir [MIT Lisansı](https://github.com/Microsoft/VCSamples/blob/master/license.txt)altında [fnv1a. hpp](https://github.com/Microsoft/VCSamples/tree/master/VC2015Samples/_Hash_seq)olan tek başına bir üstbilgi dosyasında bulunan [vcsamples]( https://github.com/Microsoft/vcsamples) deposunda GitHub 'da kullanılabilir hale geçirdik. Size kolaylık sağlamak için buraya bir kopya de ekledik. Bu kodu bir başlık dosyasına kopyalayabilir, üstbilgiyi etkilenen herhangi bir koda ekleyebilir ve sonra bulabilir ve değiştirebilirsiniz `_Hash_seq` `fnv1a_hash_bytes` . ' De iç uygulamayla aynı davranışı alacaksınız `_Hash_seq` .

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

[Visual C++ önceki sürümlerinden projeleri yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Kodunuzu Evrensel CRT’ye yükseltme](upgrade-your-code-to-the-universal-crt.md)
