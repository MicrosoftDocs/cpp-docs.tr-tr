---
title: recursive_directory_iterator Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: a5200c030986ebbcfccb1eba2963e8317c879eb6
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72686799"
---
# <a name="recursive_directory_iterator-class"></a>recursive_directory_iterator Sınıfı

Bir dizindeki dosya adlarıyla sıralı olabilecek, muhtemelen alt dizinlere yinelemeli olarak azalan bir giriş yineleyicisini açıklar. Bir yineleyici `X` için ifade `*X`, dosya adını ve durumu hakkında bilinen her şeyi sarmalayan sınıf `directory_entry` bir nesne olarak değerlendirilir.

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi gezintisiC++()](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu şunları depolar:

1. `stack<pair<directory_iterator, path>>` türünde bir nesne, bu, sıralanacak dizinlerin iç içe geçme amacını temsil eden Exposition amaçları doğrultusunda `mystack` olarak adlandırılır

1. Burada `myentry` çağrılan `directory_entry` bir nesne, Dizin dizisindeki geçerli dosya adını temsil eder.

1. Burada `no_push` adlı **bool**türünde bir nesne, alt dizinlere özyinelemeli olarak, yinelenen olarak devre dışı bırakılıp bırakılmadığını kaydeder

1. Burada `myoptions` çağrılan `directory_options` türünde bir nesne, oluşturma sırasında belirlenen seçenekleri kaydeder

@No__t_0 türündeki varsayılan oluşturulmuş bir nesne `mystack.top().first` bir sıra sonu yineleyicisini içerir ve dizi son yineleyicisini temsil eder. Örneğin, Dizin `abc` `def` (bir dizin), `def/ghi` ve `jkl`, kod:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

`path("abc/def/ghi")` ve `path("abc/jkl")` bağımsız değişkenlerle ziyaret eder. Sıralamayı bir dizin alt ağacı aracılığıyla iki şekilde niteleyebilirsiniz:

1. Bir dizin oluşturmaksızın, yalnızca değeri `directory_options::follow_directory_symlink` olan bir `directory_options` bağımsız değişkeni olan bir `recursive_directory_iterator` oluşturursanız taranır.

1. @No__t_0 çağırırsanız, bir artış sırasında daha sonra karşılaşılan bir dizin özyinelemeli olarak taranmaz.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|Bir `recursive_directory_iterator` oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[derinliğini](#depth)|@No__t_0 döndürür, bu nedenle `pval` derinlik sıfırdır.|
|[disable_recursion_pending](#disable_recursion_pending)|@No__t_1 ' de **true** depolar.|
|[ılamadı](#increment)|Sıradaki dosya adına ilerler.|
|[Seçenekler](#options)|@No__t_0 döndürür.|
|[cağımız](#pop)|Sonraki nesneyi döndürür.|
|[recursion_pending](#recursion_pending)|@No__t_0 döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|@No__t_0 döndürür.|
|[işleç =](#op_as)|Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.|
|[işleç = =](#op_eq)|Yalnızca `*this` ve *sağ* sıralı yineleyiciler ise veya her ikisi de dizi sırası yineleyiciler değilse **true** değerini döndürür.|
|[işlecinde](#op_multiply)|@No__t_0 döndürür.|
|[operator->](#op_cast)|@No__t_0 döndürür.|
|[işleç + +](#op_increment)|@No__t_0 artırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<filesystem >

**Ad alanı:** std:: TR2:: sys

## <a name="depth"></a>recursive_directory_iterator::d epth

@No__t_0 döndürür, bu nedenle `pval` derinlik sıfırdır.

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a>recursive_directory_iterator::d isable_recursion_pending

@No__t_1 ' de **true** depolar.

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a>recursive_directory_iterator:: Increment

Sıradaki dosya adına ilerler.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>Parametreler

*ec* \
Belirtilen hata kodu.

### <a name="remarks"></a>Açıklamalar

İşlev, iç içe dizideki bir sonraki dosya adına ilerle çalışır. Başarılı olursa, bu dosya adını `myentry` depolar; Aksi takdirde, dizi sonu Yineleyici oluşturur.

## <a name="op_neq"></a>recursive_directory_iterator:: operator! =

@No__t_0 döndürür.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ* \
Karşılaştırma için [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) .

## <a name="op_as"></a>recursive_directory_iterator:: operator =

Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*recursive_directory_iterator* \
@No__t_1 Kopyalanmakta olan [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) .

## <a name="op_eq"></a>recursive_directory_iterator:: operator = =

Yalnızca `*this` ve *sağ* sıralı yineleyiciler ise veya her ikisi de dizi sırası yineleyiciler değilse **true** değerini döndürür.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ* \
Karşılaştırma için [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) .

## <a name="op_multiply"></a>recursive_directory_iterator:: operator *

@No__t_0 döndürür.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a>recursive_directory_iterator:: operator->

@No__t_0 döndürür.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a>recursive_directory_iterator:: operator + +

@No__t_0 artırır.

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parametreler

*int* \
Belirtilen artış.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi `increment()` çağırır ve sonra `*this` döndürür. İkinci üye işlevi nesnenin bir kopyasını yapar, `increment()` çağırır ve sonra kopyayı döndürür.

## <a name="options"></a>recursive_directory_iterator:: Options

@No__t_0 döndürür.

```cpp
directory_options options() const;
```

## <a name="pop"></a>recursive_directory_iterator::p op

Sonraki nesneyi döndürür.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

@No__t_0 nesne bir sıra sonu yineleyicisi haline gelir. Aksi takdirde, üye işlevi geçerli (ayrıntılı) dizinin taranmasını sonlandırır ve bir sonraki daha düşük derinlikte devam eder.

## <a name="recursion_pending"></a>recursive_directory_iterator::recursion_pending

@No__t_0 döndürür.

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iterator"></a>recursive_directory_iterator::recursive_directory_iterator

Bir `recursive_directory_iterator` oluşturur.

```cpp
recursive_directory_iterator() noexcept;
explicit recursive_directory_iterator(const path& pval);

recursive_directory_iterator(const path& pval,
    error_code& ec) noexcept;
recursive_directory_iterator(const path& pval,
    directory_options opts);

recursive_directory_iterator(const path& pval,
    directory_options opts,
    error_code& ec) noexcept;
recursive_directory_iterator(const recursive_directory_iterator&) = default;
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*Pval* \
Belirtilen yol.

*error_code* \
Belirtilen hata kodu.

*OptIn* \
Belirtilen dizin seçenekleri.

*recursive_directory_iterator* \
Oluşturulan `recursive_directory_iterator` bir kopya olduğu `recursive_directory_iterator`.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir dizi sonu yineleyiciyi üretir. İkinci ve üçüncü oluşturucular `myoptions` `no_push` ve **`directory_options::none` depolar,** sonra da bir dizin olarak *Pval* 'yi açmayı ve okumayı dener. Başarılı olursa, iç içe dizideki ilk dizin olmayan dosya adını belirlemek için `mystack` ve `myentry` başlatır; Aksi takdirde, bir dizi son yineleyicisi üretir.

Dördüncü ve beşinci oluşturucular, ikinci ve üçüncü ile aynı şekilde davranır, ancak `myoptions` *ilk olarak onları depolarlar* . Varsayılan olarak construtors beklendiği gibi davranır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[\<filesystem >](../standard-library/filesystem.md) \
[Dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md)
