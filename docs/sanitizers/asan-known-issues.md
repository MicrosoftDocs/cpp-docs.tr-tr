---
title: Adrestemizleme bilinen sorunlar
description: Microsoft C/C++ bilinen sorunları için Addresstemizleme 'nin teknik açıklaması.
ms.date: 03/02/2021
helpviewer_keywords:
- AddressSanitizer known issues
ms.openlocfilehash: 7db8b06a96eababbd6a48e337cff7155f248fb34
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470721"
---
# <a name="addresssanitizer-known-issues"></a>Adrestemizleme bilinen sorunlar

> [!NOTE]
> Gelecek sürümlerde görmek istediğiniz gibi bize [geri bildirim](https://aka.ms/vsfeedback/browsecpp) gönderin ve sorunlarla karşılaşırsanız [hataları bildirin](https://aka.ms/feedback/report?space=62) .

## <a name="incompatible-options-and-functionality"></a><a name="incompatible-options"></a> Uyumsuz seçenekler ve işlevler

Bu seçenekler ve işlevler ile uyumsuzdur [`/fsanitize=address`](../build/reference/fsanitize.md) ve devre dışı bırakılmalıdır ya da kaçınılmalıdır.

- [`/RTC`](../build/reference/rtc-run-time-error-checks.md)Seçenekler Addresstemizleme ile uyumlu değil ve devre dışı bırakılmalıdır.
- [Artımlı bağlama](../build/reference/incremental-link-incrementally.md) desteklenmez ve devre dışı bırakılmalıdır.
- [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue-visual-cpp) desteklenmez ve devre dışı bırakılmalıdır.
- [Coroutines](https://devblogs.microsoft.com/cppblog/category/coroutine/) , addresstemizleme ile uyumlu değildir ve sürdürülebilir işlevleri, izleme 'den muaf tutulur.
- [OpenMP](../build/reference/openmp-enable-openmp-2-0-support.md) desteklenmez ve devre dışı bırakılmalıdır.
- [Yönetilen C++](../build/reference/clr-common-language-runtime-compilation.md) desteklenmez ve devre dışı bırakılmalıdır.
- [C++ amp](../parallel/amp/cpp-amp-overview.md) desteklenmez ve devre dışı bırakılmalıdır.
- [Özel durum listesi](https://clang.llvm.org/docs/SanitizerSpecialCaseList.html) dosyaları desteklenmez.

## <a name="standard-library-support"></a>Standart Kitaplık desteği

MSVC standart kitaplığı (STL), Addresstemizleme 'nin anlaşılmasına yönelik değildir. STL kodunda oluşturulan Addresstemizleme özel durumları, doğru hataları tespit ediyor. Ancak, bunlar, olabilecekleri kadar kesin değildir.

Bu örnekte duyarlık olmaması gösterilmektedir:

```cpp
// Compile with: cl /fsanitize=address /Zi
#include <vector>

int main() {   
    // Create a vector of size 10, but with a capacity of 20.    
    std::vector<int> v(10);
    v.reserve(20);

    // Currently, MSVC ASan does NOT raise an exception here.
    // While this is an out-of-bounds write to 'v', MSVC ASan
    // ensures the write is within the heap allocation size (20).
    v[10] = 1;

    // MSVC ASan DOES raise an exception here, as this write
    // is out of bounds from the heap allocation.
    v[20] = 1;
}
```

## <a name="windows-versions"></a>Windows sürümleri

Belirli Windows sürümleriyle bağımlılıklar olduğundan, destek Windows 10 ' a odaklanır. MSVC Addresstemizleyebilir, 10.0.14393 (RS1) ve 10.0.21323 (ön sürüm Insider Build) üzerinde sınanmıştır. Sorunlarla karşılaşırsanız [bir hata bildirin](https://aka.ms/feedback/report?space=62) .

## <a name="memory-usage"></a>Bellek kullanımı

Addresstemizleyemeyen çalışma zamanı, yürütme sırasında yeniden işletim sistemine bellek serbest bırakmıyor. İşletim sisteminin görünüm noktasından bir bellek sızıntısı gibi görünebilir. Bu tasarım kararı bilerek yapılır, bu nedenle tüm gerekli bellek ön tahsisi gerekmez.

## <a name="addresssanitizer-runtime-dll-locations"></a>Addresstemizleme çalışma zamanı DLL konumları

*`clang_rt.asan*.dll`* Çalışma zamanı dosyaları içindeki derleyicilerin yanına yüklenir *`%VSINSTALLDIR%\VC\Tools\MSVC\<version>\bin\<host-arch>\<target-arch>\`* . Bu konumlar, hata ayıklama oturumlarındaki yoldur ve Visual Studio Geliştirici komut istemleri ' nde bulunur. Bu dosyalar hiçbir şekilde veya içine yerleştirilmez *`C:\Windows\System32`* *`C:\Windows\SysWOW64`* .

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
