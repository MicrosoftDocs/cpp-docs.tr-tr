---
title: '&lt;cstdlib&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdlib>
helpviewer_keywords:
- cstdlib header
ms.assetid: 0a6aaebf-84e9-4b60-ae90-17e11981cf54
ms.openlocfilehash: 70e05ad734fa49ba8cb96e4bf83bc05b99c5f55c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246523"
---
# <a name="ltcstdlibgt"></a>&lt;cstdlib&gt;

Standart C Kitaplığı üstbilgisi içerir \<stdlib.h > ve ilişkili adlar ekler `std` ad alanı. Bu üstbilginin dahil sağlar C Standart Kitaplığı üstbilgisinde harici bağlantı kullanılarak bildirilen adların bildirilir `std` ad alanı.

> [!NOTE]
> \<stdlib.h > türü içermez **wchar_t**.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<cstdlib >

**Namespace:** std

## <a name="namespace-and-macros"></a>Namespace ve makroları

```cpp
namespace std {
    using size_t = see definition;
    using div_t = see definition;
    using ldiv_t = see definition;
    using lldiv_t = see definition;
}

#define NULL
#define EXIT_FAILURE
#define EXIT_SUCCESS
#define RAND_MAX
#define MB_CUR_MAX
```

## <a name="exposition-only-functions"></a>Exposition yalnızca İşlevler

```cpp
extern "C" using c-atexit-handler = void();
extern "C++" using atexit-handler = void();
extern "C" using c-compare-pred = int(const void*, const void*);
extern "C++" using compare-pred = int(const void*, const void*);
```

## <a name="start-and-termination-functions"></a>Başlangıç ve sonlandırma işlevleri

|İşlev|Açıklama|
|-|-|
|[_Exit](#_exit)|Program, Yıkıcılar veya kayıtlı işlevleri kullanmadan sonlandırır.|
|[abort](#abort)|Yıkıcıları kullanma olmadan programını sonlandırır.|
|[atexit](#atexit)|Program sonlandırma için kayıtları işlevi.|
|[Çıkış](#exit)|İş parçacığı ve statik depolama, ardından döndürür denetimi nesnelerini yok eder.|
|[at_quick_exit](#at_quick_exit)|Program sonlandırma için bağımsız değişkenler olmadan kayıtları işlevi.|
|[quick_exit](#quick_exit)|Program sonlandırma için korunan nesneler işleviyle kaydeder.|
|[GETENV](#getenv)|C Standart Kitaplığı Başvurusu bakın.|
|[Sistem](#system)|C Standart Kitaplığı Başvurusu bakın.|

### <a name="_exit"></a> _Exit

```cpp
[[noreturn]] void _Exit(int status) noexcept;
```

#### <a name="remarks"></a>Açıklamalar

Otomatik nesnelerin, iş parçacığı veya statik depolama süresi yok ediciler yürütme için geçen işlevler çağırma olmadan ve program sonlandırılır `atexit()`. İşlev `_Exit` sinyal güvenlidir.

### <a name="abort"></a> Durdurma

```cpp
[[noreturn]] void abort() noexcept;
```

#### <a name="remarks"></a>Açıklamalar

Otomatik nesnelerin, iş parçacığı veya statik depolama süresi yok ediciler yürütme için geçen işlevler çağırma olmadan ve program sonlandırılır `atexit()`. İşlev `abort` sinyal güvenlidir.

### <a name="at_quick_exit"></a> at_quick_exit

```cpp
int at_quick_exit(c-atexit-handler * func) noexcept;
int at_quick_exit(atexit-handler * func) noexcept;
```

#### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olursa sıfır, sıfır olmayan Eğer başarısız olur.

#### <a name="remarks"></a>Açıklamalar

`at_quick_exit()` İşlevleri kaydetme işaret ettiği işlevi *func* bağımsız değişken çağrılabilir olduğunda `quick_exit` çağrılır. Belirtilmemiş bir çağrı olmadığını `at_quick_exit()` tüm çağrıları önce gerçekleşen değil `quick_exit` başarılı olur ve `at_quick_exit()` işlevleri veri yarış tanıtmak değil. Kayıt sırasını belirsiz olabilir, `at_quick_exit` fazla tek iş parçacığı ve sonrasında çağrıldı `at_quick_exit` kayıtları kodundan `atexit` kayıtları, uygulamalar ile her iki kayıt işlevleri çağırmak gerekebilir aynı bağımsız değişkeni. Uygulama, en az 32 işlevleri kaydını desteklemek.

### <a name="atexit"></a> atexit

```cpp
int atexit(c-atexit-handler * func) noexcept;
int atexit(atexit-handler * func) noexcept;
```

#### <a name="remarks"></a>Açıklamalar

`atexit()` İşlevleri kaydetme işaret ettiği işlevi *func* normal program sonlandırma sırasında bağımsız değişken olmadan çağrılabilir. Belirtilmemiş bir çağrı olmadığını `atexit()` çağrısı önce gerçekleşen olmayan `exit()` başarılı olur ve `atexit()` işlevleri veri yarış tanıtmak değil. Uygulama, en az 32 işlevleri kaydını desteklemek.

#### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı, başarısız olursa sıfır olursa döndürür sıfır.

### <a name="exit"></a> Çıkış

```cpp
[[noreturn]] void exit(int status);
```

#### <a name="remarks"></a>Açıklamalar

İlk olarak, iş parçacığı depolama süresine nesneleri ve ilişkili geçerli iş parçacığı yok edilir.

Ardından, statik depolama süresine sahip nesneler yok edilir ve işlevleri çağırarak kayıtlı `atexit` olarak adlandırılır. Çağırma sonucunda otomatik nesnelerin yok olmayan `exit()`. Kayıtlı işlevi çağıran denetimi terk ederse `exit` işlevi oluşan bir özel durum için bir işleyici sağlamadığından `std::terminate()` çağrılması. Her kaydedildiğinde bir işlev için çağrılır. Nesneleri otomatik depolama süresine sahip tüm yok, ana işlevi yok otomatik nesneler içerir ve çağrısı yürütür programında `exit()`. Denetim, ana yakalanan bir özel durum tarafından doğrudan bu tür bir ana işlevini aktarılabilir.

C akışları tüm açık ardından, (tarafından bildirilen işlev imzası cout gibi <cstdio>) temizlenmiş, tüm açık olan C akışları kapatılır ve tüm dosyaları yazılı arabelleğe alınan verilerle oluşturulan çağırarak `tmpfile()` kaldırılır.

Son olarak, denetimi için ana bilgisayar ortamının döndürülür. Durum sıfır ya da exıt_success ise, durumu başarılı sonlandırma uygulama tanımlı bir tür döndürülür. Durum exıt_faılure ise, durumu başarısız sonlandırma uygulama tanımlı bir tür döndürülür. Aksi takdirde uygulama tanımlı durumu döndürülür.

### <a name="getenv"></a> GETENV

```cpp
char* getenv(const char* name);
```

### <a name="quick_exit"></a> quick_exit

```cpp
[[noreturn]] void quick_exit(int status) noexcept;
```

#### <a name="remarks"></a>Açıklamalar

İşlevleri kayıtlı yapılan çağrılar tarafından `at_quick_exit` herhangi kayıtlı anda çağıran işlevler daha önce kaydetmiş sonra bir işlev adı dışında kendi kayıt ters sırada denir. Nesneler yok edilmez çağırma sonucunda `quick_exit`. Kayıtlı işlevi çağıran denetimi terk ederse `quick_exit` işlevi oluşan bir özel durum için bir işleyici sağlamadığından `std::terminate()` çağrılması. Bir işlev aracılığıyla kaydedilen `at_quick_exit` çağıran iş parçacığı tarafından çağrılan `quick_exit`, bu nedenle, kayıtlı bir kayıtlı daha işlevleri farklı bir iş parçacığına olabilen iş parçacığı depolama süresine sahip nesne kimliğini güvenmemelisiniz. Kayıtlı işlev, çağrıldıktan sonra `quick_exit` çağrı `_Exit(status)`. Standart dosya arabellekler Temizlenen değildir. İşlev `quick_exit` işlevleri ile kaydettiğinizde, sinyal güvenli olmayandır `at_quick_exit` olan.

### <a name="system"></a> Sistem

```cpp
int system(const char* string);
```

## <a name="memory-allocation-functions"></a>Bellek ayırma işlevleri

```cpp
void* aligned_alloc(size_t alignment, size_t size);
void* calloc(size_t nmemb, size_t size);
void free(void* ptr);
void* malloc(size_t size);
void* realloc(void* ptr, size_t size);
double atof(const char* nptr);
int atoi(const char* nptr);
long int atol(const char* nptr);
long long int atoll(const char* nptr);
double strtod(const char* nptr, char** endptr);
float strtof(const char* nptr, char** endptr);
long double strtold(const char* nptr, char** endptr);
long int strtol(const char* nptr, char** endptr, int base);
long long int strtoll(const char* nptr, char** endptr, int base);
unsigned long int strtoul(const char* nptr, char** endptr, int base);
unsigned long long int strtoull(const char* nptr, char** endptr, int base);
```

#### <a name="remarks"></a>Açıklamalar

Bu işlevler standart C Kitaplığı'nda belirtilen semantiği vardır.

##  <a name="multibyte--wide-string-and-character-conversion-functions"></a>Çok baytlı / geniş dize ve karakter dönüştürme işlevleri

```cpp
int mblen(const char* s, size_t n);
int mbtowc(wchar_t* pwc, const char* s, size_t n);
int wctomb(char* s, wchar_t wchar);
size_t mbstowcs(wchar_t* pwcs, const char* s, size_t n);
size_t wcstombs(char* s, const wchar_t* pwcs, size_t n);
```

### <a name="remarks"></a>Açıklamalar

Bu işlevler standart C Kitaplığı'nda belirtilen semantiği vardır.

## <a name="algorithm-functions"></a>Algoritma işlevleri

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

### <a name="remarks"></a>Açıklamalar

Bu işlevler standart C Kitaplığı'nda belirtilen semantiği vardır.

## <a name="low-quality-random-number-generation-functions"></a>Düşük kaliteli rastgele sayı üretimi işlevleri

```cpp
int rand();
void srand(unsigned int seed);
```

### <a name="remarks"></a>Açıklamalar

Bu işlevler standart C Kitaplığı'nda belirtilen semantiği vardır.

## <a name="absolute-values"></a>Mutlak değerler

```cpp
int abs(int j);
long int abs(long int j);
long long int abs(long long int j);
float abs(float j);
double abs(double j);
long double abs(long double j);
long int labs(long int j);
long long int llabs(long long int j);
div_t div(int numer, int denom);
ldiv_t div(long int numer, long int denom);
lldiv_t div(long long int numer, long long int denom);
ldiv_t ldiv(long int numer, long int denom);
lldiv_t lldiv(long long int numer, long long int denom);
```

### <a name="remarks"></a>Açıklamalar

Bu işlevler standart C Kitaplığı'nda belirtilen semantiği vardır.

## <a name="functions"></a>İşlevler

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
