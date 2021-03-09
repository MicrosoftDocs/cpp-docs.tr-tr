---
title: Addresstemizleme hatası örnekleri
description: Addresstemizleme hatalarının ve Microsoft C/C++ ' daki örneklerin en üst düzey açıklaması.
ms.date: 03/01/2021
helpviewer_keywords:
- ASan error examples
- AddressSanitizer error examples
- Address Sanitizer error examples
- Error examples for AddressSanitizer
ms.openlocfilehash: 6f8036139c48b03fb8300f799fbdf05e5006aa4a
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470822"
---
# <a name="addresssanitizer-error-examples"></a>Addresstemizleme hatası örnekleri

Bu bölümdeki Microsoft C/C++ (MSVC) içinde Addresstemizleyerek desteklenen hataların bir alt kümesini listeliyoruz. Bu liste kapsamlı bir hata listesi değil. Addresstemizme içinde göreceğiniz çeşitli hata türlerini göstermek için tasarlanmıştır. Her makalede, hata ayıklayıcıda hata ayıklayıcının derleme yönergeleri ve ekran görüntüleri ile örnek kod ekledik. Kodunuzda MSVC tarafından desteklenen Addresstemizleme özelliklerini kullanmayı öğrenmenize yardımcı olur. Tüm ekran görüntüleri kullanılarak oluşturulmuştur **`devenv.exe /debugexe example.exe`** . Bu örneklerden bazıları [LLVM derleyici-RT test paketindeki](https://github.com/llvm/llvm-project/tree/main/compiler-rt/test/asan/TestCases)örnek kodu temel alır.

## <a name="build-the-error-examples"></a>Hata örneklerini oluşturma

Her hata örneği, bir komut satırı derlemesi için kaynak kodu ve derleme yönergeleri sağlar. Her örneği oluşturmak için bir [Geliştirici komut istemi](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)açın. Örnek projeniz için bir klasör oluşturun ve geçerli dizin yapın. Ardından örnek kodu, gibi uygun ada sahip bir kaynak dosyasına kopyalayın *`example1.cpp`* . Hata ayıklayıcıda belgelenmiş kodu oluşturmak ve çalıştırmak için yapı yönergelerini izleyin.

## <a name="errors-with-examples"></a>Örneklerle ilgili hatalar

- [Hatayla `alloc-dealloc-mismatch`](./error-alloc-dealloc-mismatch.md)

- [Hatayla `allocation-size-too-big`](./error-allocation-size-too-big.md)

- [Hatayla `calloc-overflow`](./error-calloc-overflow.md)

- [Hatayla `double-free`](./error-double-free.md)

- [Hatayla `dynamic-stack-buffer-overflow`](./error-dynamic-stack-buffer-overflow.md)

- [Hatayla `global-overflow`](./error-global-buffer-overflow.md)

- [Hatayla `heap-buffer-overflow`](./error-heap-buffer-overflow.md)

- [Hatayla `heap-use-after-free`](./error-heap-use-after-free.md)

- [Hatayla `invalid-allocation-alignment`](./error-invalid-allocation-alignment.md)

- [Hatayla `memcpy-param-overlap`](./error-memcpy-param-overlap.md)

- [Hatayla `new-delete-type-mismatch`](./error-new-delete-type-mismatch.md)

- [Hatayla `stack-buffer-overflow`](./error-stack-buffer-overflow.md)

- [Hatayla `stack-buffer-underflow`](./error-stack-buffer-underflow.md)

- [Hatayla `stack-use-after-return`](./error-stack-use-after-return.md)

- [Hatayla `stack-use-after-scope`](./error-stack-use-after-scope.md)

- [Hatayla `strncat-param-overlap`](./error-strncat-param-overlap.md)

- [Hatayla `use-after-poison`](./error-use-after-poison.md)

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)
