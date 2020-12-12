---
description: 'Daha fazla bilgi edinin: &lt; cstdlib&gt;'
title: '&lt;cstdlib&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdlib>
helpviewer_keywords:
- cstdlib header
ms.assetid: 0a6aaebf-84e9-4b60-ae90-17e11981cf54
ms.openlocfilehash: 8ab3ecc7a2db1d1cf90c69230c34a301587fc1e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324728"
---
# <a name="ltcstdlibgt"></a>&lt;cstdlib&gt;

C standart kitaplığı üst bilgisini içerir \<stdlib.h> ve ilgili adları `std` ad alanına ekler. Bu üst bilgiyi dahil etmek, C standart kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

> [!NOTE]
> \<stdlib.h> türü içermez **`wchar_t`** .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<cstdlib>

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
|[_Exit](#_exit)|Yıkıcıları veya kayıtlı işlevleri kullanmadan programı sonlandırır.|
|[durdur](#abort)|Yıkıcıları kullanmadan programı sonlandırır.|
|[atexit](#atexit)|Program sonlandırma için bir işlev kaydeder.|
|[çıkıp](#exit)|İş parçacığı ve statik depolama ile nesneleri yok eder ve ardından denetimi döndürür.|
|[at_quick_exit](#at_quick_exit)|Program sonlandırma için bağımsız değişken olmadan işlevi kaydeder.|
|[quick_exit](#quick_exit)|Program sonlandırma için korunan nesnelerle işlevi kaydeder.|
|[getenv](#getenv)|Bkz. C standart kitaplık başvurusu.|
|[sistem](#system)|Bkz. C standart kitaplık başvurusu.|

### <a name="_exit"></a><a name="_exit"></a> _Exit

```cpp
[[noreturn]] void _Exit(int status) noexcept;
```

#### <a name="remarks"></a>Açıklamalar

Program, otomatik, iş parçacığı veya statik depolama süresi nesneleri için yok ediciler yürütmeden ve geçirilen işlevleri çağırmadan sonlandırılır `atexit()` . İşlev, `_Exit` sinyal açısından güvenlidir.

### <a name="abort"></a><a name="abort"></a> durdurulmaya

```cpp
[[noreturn]] void abort() noexcept;
```

#### <a name="remarks"></a>Açıklamalar

Program, otomatik, iş parçacığı veya statik depolama süresi nesneleri için yok ediciler yürütmeden ve geçirilen işlevleri çağırmadan sonlandırılır `atexit()` . İşlev, `abort` sinyal açısından güvenlidir.

### <a name="at_quick_exit"></a><a name="at_quick_exit"></a> at_quick_exit

```cpp
int at_quick_exit(c-atexit-handler * func) noexcept;
int at_quick_exit(atexit-handler * func) noexcept;
```

#### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olursa sıfır olmayan, sıfır olmayan bir.

#### <a name="remarks"></a>Açıklamalar

`at_quick_exit()`İşlevler, çağrıldığında bağımsız değişken olmadan çağrılan işlev *Func* işlevini kaydeder `quick_exit` . ' A yapılan `at_quick_exit()` çağrılar başarısız olmadan önce `quick_exit` gerçekleşmeyecek bir çağrı başarısız olur. `at_quick_exit()`İşlevler bir veri yarış 'i sunmaz. Birden `at_quick_exit` fazla iş parçacığından çağrıldıysa kayıt sırası belirsiz olabilir. `at_quick_exit`Kayıtlar kayıtlardan farklı olduğundan `atexit` , uygulamaların aynı bağımsız değişkeni kullanarak her iki kayıt işlevini çağırması gerekebilir. MSVC, en az 32 işlev kaydını destekler.

### <a name="atexit"></a><a name="atexit"></a> atexit

```cpp
int atexit(c-atexit-handler * func) noexcept;
int atexit(atexit-handler * func) noexcept;
```

#### <a name="remarks"></a>Açıklamalar

`atexit()`İşlevler, normal program sonlandırmada bağımsız değişkenler olmadan çağrılması için *Func* tarafından işaret edilen işlevi kaydeder. ' A yapılan bir çağrı `atexit()` başarısız olmadan önce `exit()` gerçekleşmeyecek bir çağrı başarısız olabilir. `atexit()`İşlevler bir veri yarış 'i sunmaz.

#### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olduğunda sıfır, başarısız olursa sıfır değerini döndürür.

### <a name="exit"></a><a name="exit"></a> çıkıp

```cpp
[[noreturn]] void exit(int status);
```

#### <a name="remarks"></a>Açıklamalar

İlk olarak, iş parçacığı depolama süresi ve geçerli iş parçacığıyla ilişkili nesneler yok edilir.

Sonra, statik depolama süresine sahip nesneler yok edilir ve çağırarak kaydedilen işlevler `atexit` çağırılır. Çağrıldığında otomatik nesneler yok edilmez `exit()` . Eğer denetim `exit` , oluşturulan bir özel durum için bir işleyici sağlamadığından, denetimi tarafından çağrılan kayıtlı bir işlevi bırakırsa, `std::terminate()` çağrılır. Her kaydedildiğinde bir işlev bir kez çağrılır. Otomatik depolama süresine sahip nesneler, `main` işlevi otomatik nesne içermeyen ve çağrısını yürüten bir programda yok edilir `exit()` . Denetim, `main` içinde yakalanan bir özel durum oluşturarak doğrudan böyle bir işleve aktarılabilir `main` .

Daha sonra, tüm açık C akışları (' de belirtilen işlev imzaları tarafından belirtildiği gibi \<cstdio> ) yazılı arabelleğe alınmamış veriler silinir, tüm açık c akışları kapatılır ve çağırarak oluşturulan tüm dosyalar `tmpfile()` kaldırılır.

Son olarak, denetim konak ortamına döndürülür. *Durum* sıfır veya EXIT_SUCCESS olduğunda, başarıyla sonlandırma durumunun uygulama tanımlı bir formu döndürülür. MSVC değeri 0 döndürür. *Durum* EXIT_FAILURE Ise, MSVC 3 değerini döndürür. Aksi takdirde, MSVC *durum* parametre değerini döndürür.

### <a name="getenv"></a><a name="getenv"></a> getenv

```cpp
char* getenv(const char* name);
```

### <a name="quick_exit"></a><a name="quick_exit"></a> quick_exit

```cpp
[[noreturn]] void quick_exit(int status) noexcept;
```

#### <a name="remarks"></a>Açıklamalar

Genellikle, çağrıları tarafından kaydedilen işlevler `at_quick_exit` kayıtlarının ters sırasına göre çağırılır. Bu sipariş, diğer kayıtlı işlevler zaten çağrıldıktan sonra kayıtlı işlevlere uygulanmaz. Çağrıldığında hiçbir nesne yok edilmez `quick_exit` . Eğer denetim `quick_exit` , oluşturulan bir özel durum için bir işleyici sağlamadığından, denetimi tarafından çağrılan kayıtlı bir işlevi bırakırsa, `std::terminate()` çağrılır. Aracılığıyla kaydedilen bir işlev, `at_quick_exit` öğesini çağıran iş parçacığı tarafından çağrılır `quick_exit` ve bu, kaydolenden farklı bir iş parçacığı olabilir. Bu, kayıtlı işlevlerin iş parçacığı depolama süresi olan nesnelerin kimliğine dayanmaması anlamına gelir. Kayıtlı işlevleri çağırdıktan sonra `quick_exit` çağrılar `_Exit(status)` . Standart dosya arabellekleri boşaltılamadı. `quick_exit`İle kaydedilen işlevler olduğunda, işlevi sinyal güvenlidir `at_quick_exit` .

### <a name="system"></a><a name="system"></a> sistemin

```cpp
int system(const char* string);
```

## <a name="memory-allocation-functions"></a>Bellek ayırma işlevleri

```cpp
// void* aligned_alloc(size_t alignment, size_t size); // Unsupported in MSVC
void* calloc(size_t nmemb, size_t size);
void free(void* ptr);
void* malloc(size_t size);
void* realloc(void* ptr, size_t size);
```

### <a name="remarks"></a>Açıklamalar

Bu işlevler, C standart kitaplığı 'nda belirtilen semantiğe sahiptir. MSVC, işlevi desteklemiyor `aligned_alloc` . C11, `aligned_alloc()` `free()` `free()` yüksek oranda hizalanmış ayırmaları Işleyebilmelidir, yani Microsoft uygulamasıyla uyumsuz bir şekilde belirtilmiştir.

## <a name="numeric-string-conversions"></a>Sayısal dize dönüştürmeleri

```cpp
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

### <a name="remarks"></a>Açıklamalar

Bu işlevler, C standart kitaplığı 'nda belirtilen semantiğe sahiptir.

## <a name="multibyte--wide-string-and-character-conversion-functions"></a>Çok baytlı/geniş dize ve karakter dönüştürme işlevleri

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
```

### <a name="remarks"></a>Açıklamalar

Bu işlevler, C standart kitaplığı 'nda belirtilen semantiğe sahiptir.

## <a name="integer-division"></a>Tamsayı bölme

```cpp
div_t div(int numer, int denom);
ldiv_t div(long int numer, long int denom);
lldiv_t div(long long int numer, long long int denom);
ldiv_t ldiv(long int numer, long int denom);
lldiv_t lldiv(long long int numer, long long int denom);
```

### <a name="remarks"></a>Açıklamalar

Bu işlevler, C standart kitaplığı 'nda belirtilen semantiğe sahiptir.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
