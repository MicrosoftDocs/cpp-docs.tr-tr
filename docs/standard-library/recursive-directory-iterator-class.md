---
title: recursive_directory_iterator Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: 52e6f738aa226dba26bae0cf6e97cd18d107d677
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370138"
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator Sınıfı

Büyük olasılıkla alt dizinleri yinelemeli olarak azalan bir dizin adlarında aracılığıyla dizilerinin bir giriş yineleyici açıklar. Bir yineleyici için `X`, ifade `*X` sınıfın nesne olarak değerlendirilen `directory_entry` dosya adını ve durumunu hakkında bilinen herhangi bir şey sarmalar.

Daha fazla bilgi ve kod örnekleri için bkz. [dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı depolar:

1. bir nesne türü `stack<pair<directory_iterator, path>>`adlı `mystack` burada exposition amacı doğrultusunda, temsil eden sıralı için dizinlerinin iç içe geçirme

1. bir nesne türü `directory_entry` adlı `myentry` burada olan geçerli dosya dizini dizideki temsil eder

1. bir nesne türü **bool**adlı `no_push` burada olan alt dizinler halinde özyinelemeli iniş devre dışı bırakılıp bırakılmadığını kaydeder

1. bir nesne türü `directory_options`adlı `myoptions` burada olan yapım sırasında belirlenen seçenekleri kaydeder

Varsayılan oluşturulan nesnenin türü `recursive_directory_entry` dizisi bitiş yineleyici sahip `mystack.top().first` dizisi son yineleyiciyi temsil eder. Örneğin, dizin verilen `abc` girişlerle `def` (dizin) `def/ghi`, ve `jkl`, kod:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

Çağrı bağımsız değişkenlerle ziyaret edin `path("abc/def/ghi")` ve `path("abc/jkl")`. Sıralama aracılığıyla podstrom iki yolla belirtebilirsiniz:

1. Bir dizin sembolik bağlantısını yalnızca oluşturursanız taranacak bir `recursive_directory_iterator` ile bir `directory_options` bağımsız değişken değeri `directory_options::follow_directory_symlink`.

1. Eğer `disable_recursion_pending` taranan yinelemeli olarak bir artırma sırasında karşılaşılan bir sonraki dizin olmaz.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|Oluşturur bir `recursive_directory_iterator`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Derinliği](#depth)|Döndürür `mystack.size() - 1`, bu nedenle `pval` sıfır derinliğidir.|
|[disable_recursion_pending](#disable_recursion_pending)|Depoları **true** içinde `no_push`.|
|[Artırma](#increment)|Dizideki sonraki filename ilerler.|
|[Seçenekler](#options)|Döndürür `myoptions`.|
|[POP](#pop)|Sonraki nesneyi döndürür.|
|[recursion_pending](#recursion_pending)|Döndürür `!no_push`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Döndürür `!(*this == right)`.|
|[operator=](#op_as)|Varsayılan haline getirilen üye atama işleçleri, beklendiği gibi davranır.|
|[operator==](#op_eq)|Döndürür **true** yalnızca her iki `*this` ve *doğru* dizisi son yineleyiciler veya her ikisi de değil son-ın-dizisi-yineleyiciler şunlardır.|
|[operator *](#op_multiply)|Döndürür `myentry`.|
|[-> işleci](#op_cast)|Döndürür `&**this`.|
|[operator ++](#op_increment)|Artışlarla `recursive_directory_iterator`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<filesystem >

**Namespace:** Std::tr2:: sys

## <a name="depth"></a> recursive_directory_iterator::Depth

Döndürür `mystack.size() - 1`, bu nedenle `pval` sıfır derinliğidir.

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a> recursive_directory_iterator::disable_recursion_pending

Depoları **true** içinde `no_push`.

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a> recursive_directory_iterator::increment

Dizideki sonraki filename ilerler.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>Parametreler

*EC*<br/>
Belirtilen hata kodu.

### <a name="remarks"></a>Açıklamalar

İşlev, iç içe geçmiş dizideki sonraki filename ilerleyin dener. Başarılı, bu dosya adını depolar, `myentry`; Aksi takdirde bu dizisi bitiş yineleyici üretir.

## <a name="op_neq"></a> recursive_directory_iterator::operator! =

Döndürür `!(*this == right)`.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) karşılaştırma için.

## <a name="op_as"></a> recursive_directory_iterator::operator =

Varsayılan haline getirilen üye atama işleçleri, beklendiği gibi davranır.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*recursive_directory_iterator*<br/>
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) içine kopyalanan `recursive_directory_iterator`.

## <a name="op_eq"></a> recursive_directory_iterator::operator ==

Döndürür **true** yalnızca her iki `*this` ve *doğru* dizisi son yineleyiciler veya her ikisi de değil son-ın-dizisi-yineleyiciler şunlardır.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) karşılaştırma için.

## <a name="op_multiply"></a> recursive_directory_iterator::operator *

Döndürür `myentry`.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> recursive_directory_iterator::operator ->

Döndürür `&**this`.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> recursive_directory_iterator::operator ++

Artışlarla `recursive_directory_iterator`.

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parametreler

*int*<br/>
Belirtilen artırma.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev çağrıları `increment()`, ardından döndürür `*this`. İkinci üye işlevi çağrıları nesnesinin bir kopyasını getirir `increment()`, daha sonra kopyayı döndürür.

## <a name="options"></a> recursive_directory_iterator::Options

Döndürür `myoptions`.

```cpp
directory_options options() const;
```

## <a name="pop"></a> recursive_directory_iterator::POP

Sonraki nesneyi döndürür.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Varsa `depth() == 0` nesne dizisi bitiş yineleyici haline gelir. Aksi takdirde, üye işlevi, geçerli (en derin) dizinini tarama sonlandırır ve sonraki alt derinliğinde sürdürür.

## <a name="recursion_pending"></a> recursive_directory_iterator::recursion_pending

Döndürür `!no_push`.

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iterator"></a> recursive_directory_iterator::recursive_directory_iterator

Oluşturur bir `recursive_directory_iterator`.

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

*pval*<br/>
Belirtilen yol.

*error_code*<br/>
Belirtilen hata kodu.

*kabul eder*<br/>
Belirtilen dizin seçenekleri.

*recursive_directory_iterator*<br/>
`recursive_directory_iterator` Biri oluşturulmuş `recursive_directory_iterator` bir kopyası olacak.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir dizisi bitiş yineleyici oluşturur. İkinci ve üçüncü oluşturucular deponun **false** içinde `no_push` ve `directory_options::none` içinde `myoptions`, ardından açmak ve okumak deneme *pval* dizini olarak. Başarılı, bunlar başlatmak, `mystack` ve `myentry` ilk dizini olmayan dosya adı iç içe geçmiş sıradaki belirlemek için son dizi yineleyici ürettikleri Aksi takdirde.

İlk Depolama dışında dördüncü ve beşinci oluşturucular aynı ikinci ve üçüncü olarak davranır *bölgedeyse* içinde `myoptions`. Varsayılan haline getirilen construtors beklendiği gibi davranır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<FileSystem >](../standard-library/filesystem.md)<br/>
[Dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md)<br/>
