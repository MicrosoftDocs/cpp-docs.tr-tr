---
title: Addresstemizleme çalışma zamanı
description: Microsoft C/C++ için Addresstemizleme çalışma zamanının teknik açıklaması.
ms.date: 03/02/2021
helpviewer_keywords:
- AddressSanitizer runtime
- Address Sanitizer runtime
- clang_rt.asan
- Clang runtime
- ASan runtime
ms.openlocfilehash: 6ab27365ba6841dd5314f1eac65abd71b7d4170d
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470714"
---
# <a name="addresssanitizer-runtime"></a>Addresstemizleme çalışma zamanı

Addresstemizleme çalışma zamanı kitaplığı, bellek erişimlerinin denetlemesini etkinleştirmek için ortak bellek ayırma işlevlerini ve işlemlerini karşılar. Derleyicinin oluşturabileceği çeşitli yürütülebilir türleri destekleyen birkaç farklı çalışma zamanı kitaplığı vardır. Derleyici ve bağlayıcı, derleme zamanında seçeneği geçirdiğiniz sürece uygun çalışma zamanı kitaplıklarını otomatik olarak bağlar [`/fsanitize=address`](../build/reference/fsanitize.md) . Bağlantı sırasında seçeneğini kullanarak varsayılan davranışı geçersiz kılabilirsiniz **`/NODEFAULTLIB`** . Daha fazla bilgi için, [addresstemizleyebilir dil, derleme ve hata ayıklama başvurusu](./asan-building.md)' nda [bağlama](./asan-building.md#linker) konusunun bölümüne bakın.

Aşağıda, ya da olan Addresstemizleme çalışma zamanına bağlanmak için çalışma zamanı kitaplıklarının bir envanteri verilmiştir *`{arch}`* *`i386`* *`x86_64`* .

> [!NOTE]
> Bu kitaplıklar, mimari adları için Clang kurallarını saklar. MSVC kuralları, i386 ve x86_64 değil, normalde x86 ve x64 ' dür. Aynı mimarilere başvurur.

| CRT seçeneği | DLL veya EXE | H? | Addresstemizleme çalışma zamanı ikili kitaplıkları |
|--|--|--|--|
| MT | EXE | NO | *`clang_rt.asan-{arch}`*, *`clang_rt.asan_cxx-{arch}`* |
| MT | DLL | NO | *`clang_rt.asan_dll_thunk-{arch}`* |
| MD | KULLANABILIR | NO | *`clang_rt.asan_dynamic-{arch}`*, *`clang_rt.asan_dynamic_runtime_thunk-{arch}`* |
| MT | EXE | EVET | *`clang_rt.asan_dbg-{arch}`*, *`clang_rt.asan_dbg_cxx-{arch}`* |
| MT | DLL | EVET | *`clang_rt.asan_dbg_dll_thunk-{arch}`* |
| MD | KULLANABILIR | EVET | *`clang_rt.asan_dbg_dynamic-{arch}`*, *`clang_rt.asan_dbg_dynamic_runtime_thunk-{arch}`* |

İle derlerken `cl /fsanitize=address` , derleyici [Gölge baytları](./asan-shadow-bytes.md)yönetmek ve denetlemek için yönergeler oluşturur. Programınız yığında, yığında veya genel kapsamda bellek erişimlerini denetlemek için bu araçları kullanır. Derleyici Ayrıca yığın ve genel değişkenleri açıklayan meta veriler üretir. Bu meta veriler, çalışma zamanının kesin hata tanılama oluşturmasına olanak sağlar: kaynak kodunuzda işlev adları, satırlar ve sütunlar. , Derleyici denetimleri ve çalışma zamanı kitaplıkları, çalışma zamanında karşılaşılırsa birçok türdeki [bellek güvenliği](./asan-error-examples.md) hatasını tam olarak tanılayabilir.

## <a name="function-interception"></a>İşlev yakalaşmayı

Addresstemizleme, çok sayıda sık düzeltme eki uygulama tekniği aracılığıyla işlev yakalaşmayı elde eder. Bu teknikler [, kaynak kodun kendisi içinde en iyi şekilde belgelenmiştir](https://github.com/llvm/llvm-project/blob/1a2eaebc09c6a200f93b8beb37130c8b8aab3934/compiler-rt/lib/interception/interception_win.cpp#L11).

Çalışma zamanı kitaplıkları birçok yaygın bellek yönetimi ve bellek işleme işlevini ele geçirebilir. Bir liste için bkz. [ele geçirilebilecek Işlevlerin Adrestemizleme listesi](#intercepted_functions). Ayırma yakalayıcılar, her bir ayırma çağrısıyla ilgili meta verileri ve gölge baytları yönetir. Ya da gibi bir CRT işlevi `malloc` `delete` çağrıldığında, bu yığın konumlarının Şu anda erişilebilir olup olmadığını ve ayırma sınırlarının ne olduğunu göstermek için, bu yığın, addresstemizleme gölge bellek bölgesinde belirli değerleri ayarlar. Bu gölge baytlar, bir yükün veya deponun geçerli olup olmadığını belirlemede [Gölge baytlara](./asan-shadow-bytes.md) yönelik derleyici tarafından oluşturulan denetimleri sağlar.

Ele alma işleminin başarılı olması garanti edilmez. Bir işlev için bir işlev yazılması için çok kısaysa `jmp` , ele geçirme başarısız olabilir. Bir yakalamasyon hatası oluşursa, program bir ve bir `debugbreak` durdurur. Bir hata ayıklayıcı eklerseniz, bu durum, ele geçirme sorununun nedenini açık hale getirir. Bu sorunla karşılaşırsanız [bir hata bildirin](https://aka.ms/feedback/report?space=62).

> [!NOTE]
> Kullanıcılar isteğe bağlı olarak, ortam değişkenini herhangi bir değere ayarlayarak başarısız bir yakalaşmayı denemeye devam edebilir `ASAN_WIN_CONTINUE_ON_INTERCEPTION_FAILURE` . Bir döküm hatasının sona amaması, bu işlev için eksik hata raporlarının oluşmasına neden olabilir.

## <a name="custom-allocators-and-the-addresssanitizer-runtime"></a>Özel ayırıcılar ve Addresstemizleyiciler çalışma zamanı

Addresstemizleyiciler çalışma zamanı, ortak ayırıcı arabirimleri, `malloc` / `free` , `new` / `delete` , `HeapAlloc` / `HeapFree` (aracılığıyla `RtlAllocateHeap` / `RtlFreeHeap` ) için dinleyici sağlar. Birçok program, bir neden veya başka bir nedenden dolayı özel ayırıcıları kullanır; bir örnek, kullanan herhangi bir program `dlmalloc` ya da arabirimini kullanan bir çözüm olabilir `std::allocator` `VirtualAlloc()` . Derleyici, özel bir ayırıcıya gölge bellek yönetimi çağrılarını otomatik olarak ekleyemiyor. Bu, Kullanıcı tarafından [sunulan el ile Kirme arabirimini](#poisoning)kullanma sorumluluğudur. Bu API, bu ayırıcıların mevcut Addresstemizleyiciler çalışma zamanı ve [Gölge bayt](./asan-shadow-bytes.md) kuralları ile düzgün şekilde çalışmasını sağlar.

## <a name="manual-addresssanitizer-poisoning-interface"></a><a name="poisoning"></a> El ile Adrestemizleme Kirleme arabirimi

Enaçıklaştırıcı için arabirim basittir, ancak kullanıcıya hizalama kısıtlamalarını uygular. Kullanıcılar içeri aktararak bu Prototiplerde yer alabilir [`sanitizer/asan_interface.h`](https://github.com/llvm/llvm-project/blob/main/compiler-rt/include/sanitizer/asan_interface.h) . Arabirim işlevi prototiptürleri şunlardır:

```cpp
void __asan_poison_memory_region(void const volatile *addr, size_t size);
void __asan_unpoison_memory_region(void const volatile *addr, size_t size);
```

Kolaylık sağlaması için, [Addresstemizleme arabirimi üstbilgi dosyası](https://github.com/llvm/llvm-project/blob/main/compiler-rt/include/sanitizer/asan_interface.h) sarmalayıcı makrolar sağlar. Bu makrolar, derleme sırasında Addresstemizleme işlevinin etkinleştirilip etkinleştirilmediğini denetler. Bunlar, gerek duyulmadığında kaynak kodunuzun Kirme işlev çağrılarını atmasını sağlar. Bu makroların yukarıdaki işlevleri doğrudan çağırmak yerine kullanılması gerekir:

```cpp
#define ASAN_POISON_MEMORY_REGION(addr, size)
#define ASAN_UNPOISON_MEMORY_REGION(addr, size)
```

## <a name="alignment-requirements-for-addresssanitizer-poisoning"></a>Addresstemizleme kirlenmesi için hizalama gereksinimleri

Gölge baytların el ile kirlenmesi, hizalama gereksinimlerini dikkate almalıdır. Gölge baytları gölge bellekteki bayt sınırında sona erdirmek için gerekirse Kullanıcı doldurma eklemesi gerekir. Addresstemizleme gölge belleği 'ndaki her bir bit, uygulamanın belleğindeki Tek bir baytın durumunu kodlar. Bu kodlama, her ayırmanın da dahil olduğu her bir ayırmanın toplam boyutunun 8 baytlık bir sınıra hizalanması anlamına gelir. Hizalama gereksinimi karşılanmazsa, yanlış hata bildirimine yol açabilir. Yanlış raporlama eksik raporlar (yanlış negatifler) veya hata olmayan raporlar (yanlış pozitif sonuçlar) olarak bildirimde olabilir.

Hizalama gereksiniminin ve olası sorunların bir gösterimi için bkz. sunulan [asan hizalama örnekleri](https://github.com/mcgov/asan_alignment_example). Bunlardan biri, el ile gölge bellek kirlenmesi ile neyin yanlış gidebileceklerini gösteren küçük bir programdır. İkincisi, arabirimi kullanarak el ile kirlama kullanmanın örnek bir uygulamasıdır `std::allocator` .

## <a name="run-time-options"></a>Çalışma zamanı seçenekleri

Microsoft C/C++ (MSVC) [, LLVM-proje deposundan Clang Addresstemizleme çalışma zamanına](https://github.com/llvm/llvm-project)dayalı bir çalışma zamanı kullanır. Bu nedenle, çoğu çalışma zamanı seçeneği iki sürüm arasında paylaşılır. [Genel Clang çalışma zamanı seçeneklerinin tüm listesi burada bulunabilir](https://github.com/google/sanitizers/wiki/SanitizerCommonFlags). İzleyen bölümlerde bazı farklılıklar belgeliyoruz. Beklenen şekilde işlev gösteren seçenekleri keşfettiğinizde [bir hata bildirin](https://aka.ms/feedback/report?space=62).

### <a name="unsupported-addresssanitizer-options"></a>Desteklenmeyen Addresstemizleme seçenekleri

- detect_container_overflow
- unmap_shadow_on_exit

> [!NOTE]
> Addresstemizleme çalışma zamanı seçeneği, `halt_on_error` bekleneceğiniz şekilde çalışmaz. Hem Clang hem de MSVC çalışma zamanı kitaplıklarında, çoğu bellek bozulması hataları da dahil olmak üzere birçok hata türü **devamsız** olarak değerlendirilir.

Daha fazla bilgi için [Clang 12,0 Ile farklılıklar](./asan.md#differences) bölümüne bakın.

### <a name="msvc-specific-addresssanitizer-runtime-options"></a>MSVC-özel Addresstemizleme çalışma zamanı seçenekleri

- `windows_hook_legacy_allocators` Boolean, `true` [`GlobalAlloc`](/windows/win32/api/winbase/nf-winbase-globalalloc) ve ayırıcıların ele geçirilmesini sağlamak için olarak ayarlanır [`LocalAlloc`](/windows/win32/api/winbase/nf-winbase-localalloc) .

> [!NOTE]
> `windows_hook_legacy_allocators`Bu makale yazıldığında, bu seçenek public LLVM-proje çalışma zamanı 'nda kullanılamaz. Bu seçenek sonunda genel projeye geri katkıda bulunabilir; Ancak, kod incelemeye ve topluluk kabulüne bağımlıdır.
>
> `windows_hook_rtl_allocators`Daha önce, addresstemizleyerek bir kabul etme özelliği deneysel olan seçenek, artık varsayılan olarak etkinleştirilmiştir.

## <a name="addresssanitizer-list-of-intercepted-functions-windows"></a><a name="intercepted_functions"></a> Adrestemizleme ele geçirilebilecek işlevlerin listesi (Windows)

Addresstemizli çalışma zamanı, çalışma zamanında bellek güvenliği denetimlerini etkinleştirmek için çok sayıda işlevi etkin-Düzeltme Eki. Addresstemizleyicilerin çalışma zamanının izlediği işlevlerin ayrıntılı olmayan bir listesi aşağıda verilmiştir.

### <a name="default-interceptors"></a>Varsayılan yakalayıcılar

- [`__C_specific_handler` (yalnızca x64)](/windows/win32/devnotes/--c-specific-handler2)
- [`_aligned_free`](../c-runtime-library/reference/aligned-free.md)
- [`_aligned_malloc`](../c-runtime-library/reference/aligned-malloc.md)
- [`_aligned_msize`](../c-runtime-library/reference/aligned-msize.md)
- [`_aligned_realloc`](../c-runtime-library/reference/aligned-realloc.md)
- [`_calloc_base`](../c-runtime-library/reference/calloc.md)
- [`_calloc_crt`](../c-runtime-library/reference/calloc.md)
- [`_calloc_dbg` (yalnızca hata ayıklama çalışma zamanı)](../c-runtime-library/reference/calloc-dbg.md)
- [`_except_handler3` (yalnızca x86)](../c-runtime-library/except-handler3.md)
- [ `_except_handler4` (yalnızca x86)](../c-runtime-library/internal-crt-globals-and-functions.md) (açıklanmamıştır)
- [`_expand`](../c-runtime-library/reference/expand.md)
- `_expand_base` belgelenmemiş
- [`_expand_dbg` (yalnızca hata ayıklama çalışma zamanı)](../c-runtime-library/reference/expand-dbg.md)
- [`_free_base`](../c-runtime-library/internal-crt-globals-and-functions.md) belgelenmemiş
- [`_free_dbg` (yalnızca hata ayıklama çalışma zamanı)](../c-runtime-library/reference/free-dbg.md)
- [`_malloc_base`](../c-runtime-library/internal-crt-globals-and-functions.md) belgelenmemiş
- `_malloc_crt` belgelenmemiş
- [`_malloc_dbg` (yalnızca hata ayıklama çalışma zamanı)](../c-runtime-library/reference/malloc-dbg.md)
- [`_msize`](../c-runtime-library/reference/msize.md)
- `_msize_base` belgelenmemiş
- [`_msize_dbg` (yalnızca hata ayıklama çalışma zamanı)](../c-runtime-library/reference/msize-dbg.md)
- [`_realloc_base`](../c-runtime-library/internal-crt-globals-and-functions.md) belgelenmemiş
- `_realloc_crt` belgelenmemiş
- [`_realloc_dbg` (yalnızca hata ayıklama çalışma zamanı)](../c-runtime-library/reference/realloc-dbg.md)
- [`_recalloc`](../c-runtime-library/reference/recalloc.md)
- `_recalloc_base` belgelenmemiş
- `_recalloc_crt` belgelenmemiş
- [`_recalloc_dbg` (yalnızca hata ayıklama çalışma zamanı)](../c-runtime-library/reference/recalloc-dbg.md)
- [`_strdup`](../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)
- [`atoi`](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)
- [`atol`](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)
- [`calloc`](../c-runtime-library/reference/calloc.md)
- [`CreateThread`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread)
- [`free`](../c-runtime-library/reference/free.md)
- [`frexp`](../c-runtime-library/reference/frexp.md)
- [`longjmp`](../c-runtime-library/reference/longjmp.md)
- [`malloc`](../c-runtime-library/reference/malloc.md)
- [`memchr`](../c-runtime-library/reference/memchr-wmemchr.md)
- [`memcmp`](../c-runtime-library/reference/memcmp-wmemcmp.md)
- [`memcpy`](../c-runtime-library/reference/memcpy-wmemcpy.md)
- [`memmove`](../c-runtime-library/reference/memmove-wmemmove.md)
- [`memset`](../c-runtime-library/reference/memset-wmemset.md)
- [`RaiseException`](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception)
- [`realloc`](../c-runtime-library/reference/realloc.md)
- [`RtlAllocateHeap`](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap)
- [`RtlCreateHeap`](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateheap)
- [`RtlDestroyHeap`](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateheap)
- [`RtlFreeHeap`](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlfreeheap)
- [`RtlRaiseException`](/windows/win32/api/rtlsupportapi/nf-rtlsupportapi-rtlraiseexception)
- `RtlReAllocateHeap` belgelenmemiş
- `RtlSizeHeap` belgelenmemiş
- [`SetUnhandledExceptionFilter`](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setunhandledexceptionfilter)
- [`strcat`](../c-runtime-library/reference/strcat-wcscat-mbscat.md)
- [`strchr`](../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)
- [`strcmp`](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)
- [`strcpy`](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)
- [`strcspn`](../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)
- [`strdup`](../c-runtime-library/reference/strdup-wcsdup.md)
- [`strlen`](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
- [`strncat`](../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)
- [`strncmp`](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)
- [`strncpy`](../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)
- [`strnlen`](../c-runtime-library/reference/strnlen-strnlen-s.md)
- [`strpbrk`](../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)
- [`strspn`](../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
- [`strstr`](../c-runtime-library/reference/strstr-wcsstr-mbsstr-mbsstr-l.md)
- [`strtok`](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md)
- [`strtol`](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)
- [`wcslen`](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
- [`wcsnlen`](../c-runtime-library/reference/strnlen-strnlen-s.md)

### <a name="optional-interceptors"></a>İsteğe bağlı yakalayıcılar

Burada listelenen yakalayıcılar yalnızca bir Addresstemizleme çalışma zamanı seçeneği etkinken yüklenir. `windows_hook_legacy_allocators` `true` Eski ayırıcı yakalaşmayı etkinleştirmek için olarak ayarlayın.
`set ASAN_OPTIONS=windows_hook_legacy_allocators=true`

- [`GlobalAlloc`](/windows/win32/api/winbase/nf-winbase-globalalloc)
- [`GlobalFree`](/windows/win32/api/winbase/nf-winbase-GlobalFree)
- [`GlobalHandle`](/windows/win32/api/winbase/nf-winbase-GlobalHandle)
- [`GlobalLock`](/windows/win32/api/winbase/nf-winbase-GlobalLock)
- [`GlobalReAlloc`](/windows/win32/api/winbase/nf-winbase-GlobalReAlloc)
- [`GlobalSize`](/windows/win32/api/winbase/nf-winbase-GlobalSize)
- [`GlobalUnlock`](/windows/win32/api/winbase/nf-winbase-GlobalUnlock)
- [`LocalAlloc`](/windows/win32/api/winbase/nf-winbase-LocalAlloc)
- [`LocalFree`](/windows/win32/api/winbase/nf-winbase-LocalFree)
- [`LocalHandle`](/windows/win32/api/winbase/nf-winbase-LocalHandle)
- [`LocalLock`](/windows/win32/api/winbase/nf-winbase-LocalLock)
- [`LocalReAlloc`](/windows/win32/api/winbase/nf-winbase-LocalReAlloc)
- [`LocalSize`](/windows/win32/api/winbase/nf-winbase-LocalSize)
- [`LocalUnlock`](/windows/win32/api/winbase/nf-winbase-LocalUnlock)

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
