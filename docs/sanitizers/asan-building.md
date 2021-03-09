---
title: Addresstemizleme dili, derleme ve hata ayıklama başvurusu
description: Addresstemizleme için oluşturmanın teknik açıklaması
ms.date: 03/02/2021
f1_keywords:
- __SANITIZE_ADDRESS__
- ASAN_VCASAN_DEBUGGING
helpviewer_keywords:
- ASan reference
- AddressSanitizer reference
- Address Sanitizer reference
ms.openlocfilehash: f2f173da6d39b460098afe123a7537e36cbdf6a7
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470730"
---
# <a name="addresssanitizer-language-build-and-debugging-reference"></a>Addresstemizleme dili, derleme ve hata ayıklama başvurusu

Bu makaledeki bölümler, Addresstemizleme dil belirtimini, derleyici seçeneklerini ve bağlayıcı seçeneklerini anlatmaktadır. Ayrıca, Addresstemizleme için özel Visual Studio hata ayıklayıcı tümleştirmesini denetleyen seçenekleri de tanımlarlar.

Addresstemizleyiciler çalışma zamanı, ele alma işlevleri ve özel ayırıcıları bağlama hakkında daha fazla bilgi için bkz. [çalışma zamanı başvurusu](./asan-runtime.md). Adres Temizleme hatalarından kilitlenme dökümlerini kaydetme hakkında daha fazla bilgi için [kilitlenme bilgi döküm başvurusuna](./asan-offline-crash-dumps.md)bakın.

## <a name="language-specification"></a>Dil belirtimi

### `__SANITIZE_ADDRESS__`

`__SANITIZE_ADDRESS__`Önişlemci makrosu ayarlandığı gibi tanımlanır `1` [`/fsanitize=address`](../build/reference/fsanitize.md) . Bu makro, gelişmiş kullanıcıların, Addresstemizme çalışma zamanının varlığı için kaynak kodu koşullu olarak belirtmesini sağlar.

```cpp
#include <cstdio>

int main() {
    #ifdef __SANITIZE_ADDRESS__
        printf("Address sanitizer enabled");
    #else
        printf("Address sanitizer not enabled");
    #endif
    return 1;
}
```

### `__declspec(no_sanitize_address)`

[`__declspec(no_sanitize_address)`](../cpp/no-sanitize-address.md)Belirtici, işlevlerde, yerel değişkenlerde veya genel değişkenlerde Temizleme özelliğini seçmeli olarak devre dışı bırakmak için kullanılabilir. Bu `__declspec` , _çalışma zamanı_ davranışını değil _derleyici_ davranışını etkiler.

```cpp
__declspec(no_sanitize_address)
void test1() {
    int x[100];
    x[100] = 5; // ASan exception not caught
}

void test2() {
    __declspec(no_sanitize_address) int x[100];
    x[100] = 5; // ASan exception not caught
}

__declspec(no_sanitize_address) int g[100];
void test3() {
    g[100] = 5; // ASan exception not caught
}
```

## <a name="compiler"></a>Derleyici

### <a name="fsanitizeaddress-compiler-option"></a>`/fsanitize=address` derleyici seçeneği

[`/fsanitize=address`](../build/reference/fsanitize.md)Derleyici seçeneği, çalışma zamanında bellek güvenliği hatalarını yakalamak için kodunuzda bellek başvurularını araçlar. İzleme kancaları, depolar, kapsamlar, alloca ve CRT işlevleri yükler. Bu, sınırların dışında, bu yana kullanım dışı, kullanım öncesi kapsam gibi gizli hataları tespit edebilir. Çalışma zamanında algılanan ayrıntılı olmayan hata listesi için bkz. [Addresstemizleme hatası örnekleri](./asan-error-examples.md).

**`/fsanitize=address`** , var olan tüm C++ veya C optimizasyon düzeyleriyle uyumludur (örneğin,,,, **`/Od`** **`/O1`** **`/O2`** **`/O2 /GL`** ve profil temelli iyileştirme). Bu seçenekle oluşturulan kod statik ve dinamik CRTS (örneğin,,, ve) ile birlikte kullanılır **`/MD`** **`/MDd`** **`/MT`** **`/MTd`** . Bu derleyici seçeneği, oluşturmak için kullanılabilir. EXE veya. X86 veya x64 için hedeflenen DLL. Çağrı yığınlarının en iyi şekilde biçimlendirilmesi için hata ayıklama bilgileri gereklidir.

Çeşitli hata algılama türlerini gösteren kod örnekleri için bkz. [Addresstemizleme hatası örnekleri](asan-error-examples.md).

### <a name="fsanitize-address-use-after-return-compiler-option-experimental"></a>`/fsanitize-address-use-after-return` derleyici seçeneği (deneysel)

Varsayılan olarak, MSVC derleyicisi (Clang 'den farklı olarak), RETURN-RETURN-RETURN hatalarını yakalamak için yığında kare ayırmak üzere kod oluşturmaz. Addresstemizleme kullanarak bu hataları yakalamak için şunları yapmanız gerekir:

1. Seçeneğini kullanarak derleyin [`/fsanitize-address-use-after-return`](../build/reference/fsanitize.md) .
2. Programınızı yürütmeden önce, `set ASAN_OPTIONS=detect_stack_use_after_return=1` çalışma zamanı denetim seçeneğini ayarlamak için öğesini çalıştırın.

**`/fsanitize-address-use-after-return`** Seçeneği derleyicinin, Yereller "adres çekildi" olarak kabul edildiğinde yığında çift yığın çerçevesini kullanmak üzere kod oluşturmasına neden olur. Bu kod yalnızca tek başına kullanmaktan *çok daha yavaştır* **`/fsanitize=address`** . Daha fazla bilgi ve bir örnek için bkz. [hata `stack-use-after-return` : ](error-stack-use-after-return.md).

Yığındaki çift yığın çerçevesi, onu oluşturan işlevden geri dönüşten sonra kalır. Dönüşten sonra, yığındaki bir yuvaya ayrılan yerel adresin adresinin kullanıldığı bir örnek düşünün. Sahte yığın çerçevesiyle ilişkili gölge baytlar, 0xF9 değerini içerir. Bu 0xF9, çalışma zamanı hata bildirdiğinde bir yığın-Return-Return hatası olduğunu gösterir.

Yığın çerçeveleri yığında ayrılır ve işlevler döndürülmeden sonra kalır. Çalışma zamanı, belirli bir zaman aralığından sonra bu sahte çağrı çerçevesi nesnelerini zaman uyumsuz olarak serbest bırakmak için çöp toplamayı kullanır. Yerellerinin adresleri yığında kalıcı çerçevelere aktarıldı. Tanımlama işlevi çağrıldıktan sonra, sistemin herhangi bir yerelin ne zaman kullanıldığını tespit edebilir. Daha fazla bilgi için bkz. Google tarafından belgelendiği gibi [döndürmeden önce yığın kullanımı algoritması](https://github.com/google/sanitizers/wiki/AddressSanitizerUseAfterReturn) .

## <a name="linker"></a><a name="linker"></a> Bağlayıcı

### <a name="inferasanlibsno-linker-option"></a>`/INFERASANLIBS[:NO]` bağlayıcı seçeneği

**`/fsanitize=address`** Derleyici seçeneği, çalıştırılabilire bağlanacak Addresstemizleme kitaplığını belirtmek için nesneleri işaretler. Kitaplıklar ile başlayan adlara sahiptir *`clang_rt.asan*`* . [`/INFERASANLIBS`](../build/reference/inferasanlibs.md)Bağlayıcı seçeneği (varsayılan olarak açık), bu kitaplıkları varsayılan konumlarından otomatik olarak bağlar. Seçilen ve otomatik olarak bağlanan kitaplıklar aşağıda verilmiştir:

| CRT seçeneği | DLL veya EXE | H? | Addresstemizleme çalışma zamanı kitaplıkları |
|--|--|--|--|
| MT | EXE | NO | *`clang_rt.asan-{arch}`*, *`clang_rt.asan_cxx-{arch}`* |
| MT | DLL | NO | *`clang_rt.asan_dll_thunk-{arch}`* |
| MD | KULLANABILIR | NO | *`clang_rt.asan_dynamic-{arch}`*, *`clang_rt.asan_dynamic_runtime_thunk-{arch}`* |
| MT | EXE | EVET | *`clang_rt.asan_dbg-{arch}`*, *`clang_rt.asan_dbg_cxx-{arch}`* |
| MT | DLL | EVET | *`clang_rt.asan_dbg_dll_thunk-{arch}`* |
| MD | KULLANABILIR | EVET | *`clang_rt.asan_dbg_dynamic-{arch}`*, *`clang_rt.asan_dbg_dynamic_runtime_thunk-{arch}`* |

Bağlayıcı seçeneği [`/INFERASANLIBS:NO`](../build/reference/inferasanlibs.md) , bağlayıcının bir *`clang_rt.asan*`* kitaplık dosyasını varsayılan konumdan bağlamasını engeller. Bu seçeneği kullanırsanız, derleme betiklerinizde kitaplık yolunu ekleyin. Aksi halde, bağlayıcı çözümlenmemiş bir dış sembol hatası bildiriyor.

## <a name="visual-studio-integration"></a>Visual Studio tümleştirmesi

### <a name="fno-sanitize-address-vcasan-lib-compiler-option"></a>`/fno-sanitize-address-vcasan-lib` derleyici seçeneği

**`/fsanitize=address`** Bir Addresstemizsel cihaz özel durumu oluştuğunda gelişmiş bir Visual Studio hata ayıklama deneyimi için ek kitaplıklarda bağlantı sağlar. Bu kitaplıklara **Vcasan** adı verilir. Kitaplıklar, Visual Studio 'Nun kaynak kodunuzda Addresstemizleme hatalarını görüntülemesini sağlar. Ayrıca, bir Addresstemizleme hata raporu oluşturulduğunda yürütülebilir dosyayı kilitlenme dökümleri oluşturacak şekilde etkinleştirir. Daha fazla bilgi için bkz. [Visual Studio Addresstemizleme genişletilmiş işlevsellik kitaplığı](./asan-debugger-integration.md).

Seçilen kitaplık, derleyici seçeneklerine bağlıdır ve ' de otomatik olarak bağlanır.

| Çalışma zamanı seçeneği | VCAsan sürümü |
|--------------|----------------|
| **`/MT`**        | *`libvcasan.lib`*  |
| **`/MD`**        | *`vcasan.lib`*     |
| **`/MTd`**       | *`libvcasand.lib`* |
| **`/MDd`**       | *`vcasand.lib`*    |

Ancak, **`/Zl`** (varsayılan kitaplık adını atla) kullanarak derlerseniz, kitaplığı el ile belirtmeniz gerekir. Bunu yapmazsanız, çözümlenmemiş bir dış sembol bağlantı hatası alırsınız. Bazı tipik örnekler aşağıda verilmiştir:

```Output
error LNK2001: unresolved external symbol __you_must_link_with_VCAsan_lib
error LNK2001: unresolved external symbol ___you_must_link_with_VCAsan_lib
```

Gelişmiş hata ayıklama, seçeneği kullanılarak derleme zamanında devre dışı bırakılabilir [`/fno-sanitize-address-vcasan-lib`](../build/reference/fsanitize.md) .

### <a name="asan_vcasan_debugging-environment-variable"></a>`ASAN_VCASAN_DEBUGGING` ortam değişkeni

**`/fsanitize=address`** Derleyici seçeneği, çalışma zamanında bellek güvenliği hatalarını ortaya çıkaran bir ikili üretir. İkili komut satırından başlatıldığında ve çalışma zamanı bir hata bildirdiğinde, hata ayrıntılarını yazdırır. Ardından işlemden çıkar. `ASAN_VCASAN_DEBUGGING`Ortam değişkeni, çalışma zamanı bir hata bildirdiğinde, Visual STUDIO IDE 'yi hemen başlatmak üzere ayarlanabilir. Bu derleyici seçeneği, hataya neden olan kesin bir satırda ve sütunda, kaynak kodunuz üzerinde üst üste gelen hatayı görüntülemenize olanak sağlar.

Bu davranışı etkinleştirmek için, uygulamanızı çalıştırmadan önce komutunu çalıştırın `set ASAN_VCASAN_DEBUGGING=1` . ' İ çalıştırarak gelişmiş hata ayıklama deneyimini devre dışı bırakabilirsiniz `set ASAN_VCASAN_DEBUGGING=0` .

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
