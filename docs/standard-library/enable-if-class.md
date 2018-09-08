---
title: enable_if sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::enable_if
dev_langs:
- C++
helpviewer_keywords:
- enable_if class
- enable_if
ms.assetid: c6b8d41c-a18f-4e30-a39e-b3aa0e8fd926
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4cdc26c66c05cda821b43367b806ecc2a2a8168
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100812"
---
# <a name="enableif-class"></a>enable_if Sınıfı

Koşullu olarak aşırı yükleme çözümlemesi SFINAE için bir türün bir örneğini sağlar. İç içe geçmiş tür tanımı `enable_if<Condition,Type>::type` var — ve eşanlamlıdır `Type`— ve yalnızca, `Condition` olduğu **true**.

## <a name="syntax"></a>Sözdizimi

```cpp
template <bool B, class T = void>
struct enable_if;
```

### <a name="parameters"></a>Parametreler

*B*<br/>
Sonuç türü varlığını belirleyen değeri.

*T*<br/>
Varsa örneklemek için tür *B* geçerlidir.

## <a name="remarks"></a>Açıklamalar

Varsa *B* true ise `enable_if<B, T>` sahip eşanlamlıdır "tür" adlı bir iç içe geçmiş typedef *T*.

Varsa *B* false ise `enable_if<B, T>` "türü" adlı iç içe geçmiş bir tür tanımı yok.

Bu diğer ad şablonu sağlanır:

```cpp
template <bool B, class T = void>
using enable_if_t = typename enable_if<B,T>::type;
```

C++'da, şablon parametre değiştirme hatası kendi içinde bir hata değildir — bu olarak adlandırılır *SFINAE* (değiştirme hatası bir hata değildir). Genellikle, `enable_if` adayları aşırı yükleme çözünürlüğü kaldırmak için kullanılır — diğer bir deyişle, aşırı yükleme kümesi ayırmasından — böylece bir tanım yerine başka bir reddedilemiyor. Bu, SFINAE davranışı için uygundur. SFINAE hakkında daha fazla bilgi için bkz: [değiştirme hatası bir hata değil](http://go.microsoft.com/fwlink/p/?linkid=394798) wikipedia.

Dört örnek senaryolar şunlardır:

- 1. Senaryo: bir işlevin dönüş türünü kaydırma:

```cpp
    template <your_stuff>
typename enable_if<your_condition, your_return_type>::type
    yourfunction(args) {// ...
}
// The alias template makes it more concise:
    template <your_stuff>
enable_if_t<your_condition, your_return_type>
yourfunction(args) {// ...
}
```

- Senaryo 2: varsayılan bir bağımsız değişkene sahip bir işlev parametresi ekleme:

```cpp
    template <your_stuff>
your_return_type_if_present
    yourfunction(args, enable_if_t<your condition, FOO> = BAR) {// ...
}
```

- Senaryo 3: varsayılan bir bağımsız değişkene sahip bir şablon parametresi ekleme:

```cpp
    template <your_stuff, typename Dummy = enable_if_t<your_condition>>
rest_of_function_declaration_goes_here
```

- Senaryo 4: işlevinizi şablonlu olmayan bir bağımsız değişken varsa, onun türü kayabilir:

```cpp
    template <typename T>
void your_function(const T& t,
    enable_if_t<is_something<T>::value, const string&>
s) {// ...
}
```

Senaryo 1, dönüş türleri olmadığından taşıma oluşturucuları ve dönüştürme işleçleri ile çalışmaz.

Senaryo 2 adlandırılmamış parametre bırakır. Söyleyin `::type Dummy = BAR`, ancak ad `Dummy` ilgisizdir, ve bir ad verin "başvurulmayan parametre" uyarı tetiklemek büyük olasılıkla. Seçim yapmak zorunda değilsiniz bir `FOO` işlevi parametre türüne ve `BAR` varsayılan bağımsız değişken.  Söyleyin **int** ve `0`, ancak daha sonra kullanıcılar, kodunuzun yanlışlıkla işleve yok ek bir tamsayı geçirebiliriz. Bunun yerine kullanmanızı öneriyoruz `void **` ve her iki `0` veya **nullptr** neredeyse hiçbir şey dönüştürülebilir olduğundan `void **`:

```cpp
template <your_stuff>
your_return_type_if_present
yourfunction(args, typename enable_if<your_condition, void **>::type = nullptr) {// ...
}
```

Senaryo 2 için sıradan oluşturucular da çalışır.  Ancak, bunlar ek parametreler alınamıyor çünkü dönüştürme işleçleri için çalışmaz.  Ayrıca için işe yaramaz [variadic](../cpp/ellipses-and-variadic-templates.md) oluşturucular ek parametreler ekleyerek atanan olmayan bir içerik paketi işlevi parametre yapar ve böylece amacını boşa çıkarır çünkü `enable_if`.

Senaryo 3 kullanan ad `Dummy`, ancak isteğe bağlıdır. Yalnızca " `typename = typename`" işe yarar, ancak bu tuhaf görünüyor düşünüyorsanız, "kukla" bir adı kullanabilirsiniz — yalnızca bir işlev tanımında ayrıca kullanılabilir kullanmayın. Bir türe vermediyseniz `enable_if`hükümsüz kılmak için varsayılan olarak ve mükemmel olan ne umursamaz çünkü makul `Dummy` olduğu. Bu dahil her şeyi için dönüştürme işleçleri çalışır ve [variadic](../cpp/ellipses-and-variadic-templates.md) oluşturucular.

Senaryo 4 dönüş türlerine sahip olmayan oluşturucular çalışır ve böylece Senaryo 1 sarmalama SORUMLULUĞUN çözer.  Bununla birlikte, her zaman kullanılabilir olmayan şablonlu olmayan işlev bağımsız için Senaryo 4 sınırlıdır.  (Senaryo 4 bir şablonlu işlevinin bağımsız değişkenine kullanarak şablon bağımsız değişkeni kesintisi üzerinde çalışmasını engeller.)

`enable_if` güçlü, ancak bu yanlış olursa da tehlikeli değildir.  Amacı, yanlış olduğunda aşırı yükleme çözünürlüğü önce kaybolur aday olmak için olduğundan, etkilerini çok kafa karıştırıcı olabilir.  Bazı öneriler şunlardır:

- Kullanmayın `enable_if` derleme zamanında uygulamaları arasındaki seçin. Şimdiye kadar bir yazmayın `enable_if` için `CONDITION` diğeri `!CONDITION`.  Bunun yerine, bir *gönderme etiketi* deseni — Yineleyicilerin uygulamaları güçlü bağlı olarak seçen bir algoritma, örneğin, verilir.

- Kullanmayın `enable_if` gereksinimlerinizi uygulamaktır.  Şablon parametreleri doğrulamak istiyorsanız ve doğrulama başarısız olursa başka bir uygulama seçmek yerine bir hataya neden, kullanın [static_assert](../cpp/static-assert.md).

- Kullanım `enable_if` aksi iyi yaptığı bir aşırı yükleme kümesi olduğunda, kod belirsiz.  Çoğunlukla, oluşturucu örtük olarak dönüştürürken gerçekleşir.

## <a name="example"></a>Örnek

Bu örnekte açıklar nasıl şablon işlevi C++ Standart Kitaplığı [std::make_pair()](../standard-library/utility-functions.md#make_pair) sağladığı avantajlardan yararlanarak `enable_if`.

```cpp
void func(const pair<int, int>&);

void func(const pair<string, string>&);

func(make_pair("foo", "bar"));
```

Bu örnekte, `make_pair("foo", "bar")` döndürür `pair<const char *, const char *>`. Aşırı yükleme çözünürlüğü sahip olduğu belirlemek `func()` istediğiniz. `pair<A, B>` örtük dönüştürme bir oluşturucudan sahip `pair<X, Y>`.  Bu yeni değildir — C ++ 98'de olduğu. Bunu olsa bile, ancak C ++ 98/03, imzası örtük dönüştürme oluşturucunun her zaman, mevcut `pair<int, int>(const pair<const char *, const char *>&)`.  Aşırı yükleme çözünürlüğü değil dikkatli olun, oluşturucu örneği girişimi nedeniyle horribly dağıtır `const char *` örtük olarak dönüştürülebilir değil **int**; imzalar yalnızca arıyor, önce işlev tanımları örneği.  İmzaları dönüştürmek için mevcut olduğundan bu nedenle, örnek kod, belirsiz `pair<const char *, const char *>` hem `pair<int, int>` ve `pair<string, string>`.

C ++ 11 kullanarak bu belirsizlik işlemler sırasında Çözüldü `enable_if` emin olmak için `pair<A, B>(const pair<X, Y>&)` var. **yalnızca** olduğunda `const X&` örtük olarak dönüştürülebilir `A` ve `const Y&` içinörtükolarakdönüştürülebilir`B`.  Bu, belirlemek aşırı yükleme çözünürlüğü sağlar `pair<const char *, const char *>` öğesine dönüştürülebilir değildir `pair<int, int>` ve aşırı yükleme alan `pair<string, string>` kurtarılamaz.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
