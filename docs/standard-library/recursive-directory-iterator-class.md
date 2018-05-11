---
title: recursive_directory_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
dev_langs:
- C++
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd876ec21379d59445b88bdc08a1c7b831cb94fa
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator Sınıfı

büyük olasılıkla içinde alt dizinler yinelemeli olarak azalan bir dizin adlarında aracılığıyla dizilerinin bir giriş yineleyici açıklar. Yineleyici X, ifade için * X hesaplar için dosya adını ve durumunu hakkında bilinen herhangi bir şey sarmalar sınıfı directory_entry bir nesne.

Daha fazla bilgi ve kod örnekleri için bkz: [dosya sistemi Gezinti (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı depolar:

1. bir nesne türü yığınının < çifti\<directory_iterator, yol >>, burada mystack sıralı için dizinler nest temsil eden exposition amaçları doğrultusunda çağrılır

1. bir nesne türü directory_entry dizin dizisi geçerli dosya adını temsil eden myentry burada çağrılır

1. özyinelemeli düşüşü alt dizinleri içine devre dışı bırakılıp bırakılmadığını kaydeden bir nesnenin türü bool, no_push burada çağrılır

1. oluşturma sırasında belirlenen seçenekleri kaydeden bir nesnenin türü directory_options, myoptions burada çağrılır

Türü recursive_directory_entry oluşturulan varsayılan nesnesinin mystack.top () .first bitiş dizisi yineleyici sahiptir ve bitiş dizisi yineleyici temsil eder. Örneğin, dizin verilen abc girişleri def (dizin), def/GHI ve jkl, kodu ile:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

Çağrı bağımsız değişkenlerle ziyaret edin `path("abc/def/ghi") and path("abc/jkl").`dizin alt ağacı iki yolla aracılığıyla sıralama nitelemek:

1. Yalnızca bir recursive_directory_iterator directory_options::follow_directory_symlink değeri olan bir directory_options bağımsız değişkeniyle oluşturursanız dizin simgesel taranacak.

1. Disable_recursion_pending çağırırsanız artışı sırasında karşılaşılan bir sonraki dizin taranan yinelemeli olmaz.

## <a name="recursivedirectoryiteratordepth"></a>recursive_directory_iterator::depth

```cpp
int depth() const;
```

Sıfır derinliğinde pval olacak şekilde mystack.size() - 1 döndürür.

## <a name="recursivedirectoryiteratordisablerecursionpending"></a>recursive_directory_iterator::disable_recursion_pending

```cpp
void disable_recursion_pending();
```

Üye işlevi true no_push içinde depolar.

## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator! =

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

Üye işleci verir! (* Bu sağ ==).

## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator=

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

Varsayılan üye atama işleçleri beklendiği gibi davranır.

## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator ==

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

Üye işleci yalnızca her iki, true döndürür * bu ve bitiş dizisi yineleyiciler veya her ikisini de doğru olan değil end-in-sırası-yineleyiciler.

## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator*

```cpp
const directory_entry& operator*() const;
```

Üye işleci myentry döndürür.

## <a name="recursivedirectoryiteratoroperator-"></a>recursive_directory_iterator::operator->

```cpp
const directory_entry * operator->() const;
```

Döndürür & ** Bu.

## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator++

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

İlk üye işlevi increment() çağırır ve ardından döndürür * bu. İkinci üye işlevi nesne bir kopyasını oluşturur, increment() çağırır ve ardından kopya döndürür.

## <a name="recursivedirectoryiteratoroptions"></a>recursive_directory_iterator::Options

```cpp
directory_options options() const;
```

Myoptions döndürür.

## <a name="recursivedirectoryiteratorpop"></a>recursive_directory_iterator::POP

```cpp
void pop();
```

Varsa depth() == 0 nesne dizisi son yineleyici haline gelir. Aksi takdirde, üye işlevi geçerli (derin) dizin tarama sonlandırır ve sonraki alt derinliğinde sürdürür.

## <a name="recursivedirectoryiteratorrecursionpending"></a>recursive_directory_iterator::recursion_pending

```cpp
bool recursion_pending() const;
```

Verir! no_push.

## <a name="recursivedirectoryiteratorrecursivedirectoryiterator"></a>recursive_directory_iterator::recursive_directory_iterator

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

Bitiş dizisi yineleyici ilk Oluşturucusu oluşturur. İkinci ve üçüncü oluşturucular no_push ve myoptions directory_options::none false depolamak ve ardından açın ve dizin olarak pval okuma girişimi. Başarılı olursa, mystack ve iç içe geçmiş sırası ilk dizin olmayan dosya adını belirlemek için myentry başlatılamadı; Aksi takdirde bitiş dizisi yineleyici üretir.

Dördüncü ve beşinci oluşturucular ikinci olarak aynı şekilde davranır ve üçüncü ilk depoladıkları dışında myoptions kabul eder. Varsayılan construtors beklendiği gibi davranır.

## <a name="recursivedirectoryiteratorincrement"></a>recursive_directory_iterator::increment

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

İç içe geçmiş dizisindeki sonraki filename ilerletmek işlevi çalışır. Başarılı olursa, o filename myentry içinde depolar; Aksi takdirde bitiş dizisi yineleyici üretir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<filesystem >

**Namespace:** std::tr2::sys

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<FileSystem >](../standard-library/filesystem.md)<br/>
[Dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md)<br/>
