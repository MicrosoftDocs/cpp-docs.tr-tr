---
title: '&lt;cstdlib&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdlib>
helpviewer_keywords:
- cstdlib header
ms.assetid: 0a6aaebf-84e9-4b60-ae90-17e11981cf54
ms.openlocfilehash: 298d6a512b2863a326bda0670f33fe8f1bda0688
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449402"
---
# <a name="ltcstdlibgt"></a>&lt;cstdlib&gt;

, Stdlib. h > \<C standart kitaplığı üst bilgisini içerir ve ilişkili adları `std` ad alanına ekler. Bu üst bilgiyi dahil etmek, C standart kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

> [!NOTE]
> \<Stdlib. h > **wchar_t**türünü içermez.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: \<cstdlib >

**Ad alanı:** std

## <a name="namespace-and-macros"></a>Ad alanı ve makrolar

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

## <a name="exposition-only-functions"></a>Yalnızca Exposition işlevleri

```cpp
extern "C" using c-atexit-handler = void();
extern "C++" using atexit-handler = void();
extern "C" using c-compare-pred = int(const void*, const void*);
extern "C++" using compare-pred = int(const void*, const void*);
```

## <a name="start-and-termination-functions"></a>Başlatma ve sonlandırma işlevleri

|İşlev|Açıklama|
|-|-|
|[_Çıkış](#_exit)|Yıkıcıları veya kayıtlı işlevleri kullanmadan programı sonlandırır.|
|[abort](#abort)|Yıkıcıları kullanmadan programı sonlandırır.|
|[atexit](#atexit)|Program sonlandırma için bir işlev kaydeder.|
|[çıkıp](#exit)|İş parçacığı ve statik depolama ile nesneleri yok eder ve ardından denetimi döndürür.|
|[at_quick_exit](#at_quick_exit)|Program sonlandırma için bağımsız değişken olmadan işlevi kaydeder.|
|[quick_exit](#quick_exit)|Program sonlandırma için korunan nesnelerle işlevi kaydeder.|
|[getenv](#getenv)|Bkz. C standart kitaplık başvurusu.|
|[sistemin](#system)|Bkz. C standart kitaplık başvurusu.|

### <a name="_exit"></a>_Çıkış

```cpp
[[noreturn]] void _Exit(int status) noexcept;
```

#### <a name="remarks"></a>Açıklamalar

Program, otomatik, iş parçacığı veya statik depolama süresi nesneleri için yok ediciler yürütmeden ve geçirilen `atexit()`işlevleri çağırmadan sonlandırılır. İşlev `_Exit` , sinyal açısından güvenlidir.

### <a name="abort"></a>durdurulmaya

```cpp
[[noreturn]] void abort() noexcept;
```

#### <a name="remarks"></a>Açıklamalar

Program, otomatik, iş parçacığı veya statik depolama süresi nesneleri için yok ediciler yürütmeden ve geçirilen `atexit()`işlevleri çağırmadan sonlandırılır. İşlev `abort` , sinyal açısından güvenlidir.

### <a name="at_quick_exit"></a>at_quick_exit

```cpp
int at_quick_exit(c-atexit-handler * func) noexcept;
int at_quick_exit(atexit-handler * func) noexcept;
```

#### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olursa sıfır olmayan, sıfır olmayan bir.

#### <a name="remarks"></a>Açıklamalar

İşlevleri çağrıldığında işlev *işaret eden işlevine* işaret eden `quick_exit` işlevi kaydeder. `at_quick_exit()` Tüm `at_quick_exit()` `at_quick_exit()` çağrıları başarılı olmayacak ve işlevler bir veri yarış durumu oluşturmadığında, bu çağrıya yönelik çağrının gerçekleşmemesi belirtilmemiş. `quick_exit` Kayıt `at_quick_exit` sırası, birden fazla iş parçacığından çağrılırsa ve `atexit` kayıtlar kayıtlardan farklı olduğundan `at_quick_exit` , uygulamaların her ikisi de ile kayıt işlevlerini çağırması gerekebilir. aynı bağımsız değişken. Uygulama, en az 32 işlev kaydını destekleyecektir.

### <a name="atexit"></a>atexit

```cpp
int atexit(c-atexit-handler * func) noexcept;
int atexit(atexit-handler * func) noexcept;
```

#### <a name="remarks"></a>Açıklamalar

İşlevler `atexit()` , normal program sonlandırmada bağımsız değişkenler olmadan çağrılması için *Func* tarafından işaret edilen işlevi kaydeder. Bir `atexit()` `atexit()` çağrının başarılı olabilmesi için bir çağrının gerçekleşmeyeceğini ve işlevlerin bir veri yarış durumu almaması belirtilmemiş. `exit()` Uygulama, en az 32 işlev kaydını destekleyecektir.

#### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olduğunda sıfır, başarısız olursa sıfır değerini döndürür.

### <a name="exit"></a>çıkıp

```cpp
[[noreturn]] void exit(int status);
```

#### <a name="remarks"></a>Açıklamalar

İlk olarak, iş parçacığı depolama süresi ve geçerli iş parçacığıyla ilişkili nesneler yok edilir.

Sonra, statik depolama süresine sahip nesneler yok edilir ve çağırarak `atexit` kaydedilen işlevler çağırılır. Çağırma `exit()`sonucu olarak otomatik nesneler yok edilmez. Denetim, oluşturulan bir özel durum için bir `exit` işleyici sağlamadığından, denetimi tarafından çağrılan kayıtlı bir işlevi bırakırsa, `std::terminate()` çağırılır. Her kaydedildiği sırada bir işlev çağırılır. Otomatik depolama süresine sahip nesneler, ana işlevi otomatik nesne içermeyen ve çağrısını `exit()`yürüten bir programda yok edilir. Denetim, Main içinde yakalanan bir özel durum çalıştırılarak doğrudan böyle bir ana işleve aktarılabilir.

Daha sonra, tüm açık c akışları (' de <cstdio>belirtilen işlev imzaları tarafından belirtildiği gibi) yazılı arabelleğe alınmamış veriler silinir, tüm açık c akışları kapatılır ve çağırarak `tmpfile()` oluşturulan tüm dosyalar kaldırılır.

Son olarak, denetim konak ortamına döndürülür. Durum sıfır veya EXIT_SUCCESS ise, başarıyla sonlandırma durumundaki uygulama tanımlı bir form döndürülür. Durum EXIT_FAILURE ise, başarısız sonlandırma durumu için uygulama tanımlı bir form döndürülür. Aksi takdirde döndürülen durum uygulama tanımlı ' dır.

### <a name="getenv"></a>getenv

```cpp
char* getenv(const char* name);
```

### <a name="quick_exit"></a>quick_exit

```cpp
[[noreturn]] void quick_exit(int status) noexcept;
```

#### <a name="remarks"></a>Açıklamalar

Çağrıları `at_quick_exit` tarafından kaydedilen işlevler, kaydın ters sıralaması olarak çağrılır, çünkü bir işlev, kaydedildiği sırada zaten çağrılmış olan önceden kaydedilmiş işlevlerden sonra çağrılabilir. Çağırma `quick_exit`sonucu olarak nesneler yok edilmez. Denetim, oluşturulan bir özel durum için bir `quick_exit` işleyici sağlamadığından, denetimi tarafından çağrılan kayıtlı bir işlevi bırakırsa, `std::terminate()` çağırılır. Kullanılarak `at_quick_exit` kaydedilen bir işlev, kaydeden iş parçacığı `quick_exit`tarafından çağrılır, bu, kaydolenden farklı bir iş parçacığı olabilir, bu nedenle kayıtlı işlevler iş parçacığı depolama süresine sahip nesnelerin kimliğine dayanmamalıdır. Kayıtlı işlevleri `quick_exit` çağırdıktan sonra çağrı `_Exit(status)`yapılır. Standart dosya arabellekleri boşaltılamadı. `quick_exit` İle`at_quick_exit` kaydedilen işlevler olduğunda, işlevi sinyal güvenlidir.

### <a name="system"></a>sistemin

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

Bu işlevler, C standart kitaplığı 'nda belirtilen semantiğe sahiptir.

##  <a name="multibyte--wide-string-and-character-conversion-functions"></a>Çok baytlı/geniş dize ve karakter dönüştürme işlevleri

```cpp
int mblen(const char* s, size_t n);
int mbtowc(wchar_t* pwc, const char* s, size_t n);
int wctomb(char* s, wchar_t wchar);
size_t mbstowcs(wchar_t* pwcs, const char* s, size_t n);
size_t wcstombs(char* s, const wchar_t* pwcs, size_t n);
```

### <a name="remarks"></a>Açıklamalar

Bu işlevler, C standart kitaplığı 'nda belirtilen semantiğe sahiptir.

## <a name="algorithm-functions"></a>Algoritma işlevleri

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

### <a name="remarks"></a>Açıklamalar

Bu işlevler, C standart kitaplığı 'nda belirtilen semantiğe sahiptir.

## <a name="low-quality-random-number-generation-functions"></a>Düşük kaliteli rastgele sayı oluşturma işlevleri

```cpp
int rand();
void srand(unsigned int seed);
```

### <a name="remarks"></a>Açıklamalar

Bu işlevler, C standart kitaplığı 'nda belirtilen semantiğe sahiptir.

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

Bu işlevler, C standart kitaplığı 'nda belirtilen semantiğe sahiptir.

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

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++Standart kitaplığa genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
