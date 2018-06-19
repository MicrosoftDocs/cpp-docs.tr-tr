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
ms.openlocfilehash: d8fbcf91b2b863312374fad96239a9585bb3b38c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846915"
---
# <a name="enableif-class"></a>enable_if Sınıfı

Koşullu SFINAE için bir tür örneği aşırı yükleme çözümü sağlar. İç içe geçmiş typedef `enable_if<Condition,Type>::type` var — ve eşanlamlısı `Type`— yalnızca ve yalnızca, `Condition` olan `true`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <bool B, class T = void>
struct enable_if;
```

### <a name="parameters"></a>Parametreler

`B` Elde edilen türü varlığını belirleyen değeri.

`T` Varsa örneği oluşturmak için türü `B` doğrudur.

## <a name="remarks"></a>Açıklamalar

Varsa `B` doğrudur `enable_if<B, T>` sahip eşanlamlısı olan "tür" adlı bir iç içe geçmiş typedef `T`.

Varsa `B` false, `enable_if<B, T>` "type" adlı bir iç içe geçmiş typedef sahip değil.

Bu diğer ad şablon sağlanır:

```cpp
template <bool B, class T = void>
using enable_if_t = typename enable_if<B,T>::type;
```

C++'da, şablon parametre değiştirme hatası kendi içinde bir hata değildir — bu olarak adlandırılır *SFINAE* (değiştirme hatası bir hata değildir). Genellikle, `enable_if` aşırı resolution adayları kaldırmak için kullanılan — diğer bir deyişle, aşırı kümesi culls — böylece bir tanım başka lehinde reddedilebilir. Bu SFINAE davranışı için uygundur. SFINAE hakkında daha fazla bilgi için bkz: [değiştirme hatası bir hata değildir](http://go.microsoft.com/fwlink/p/?linkid=394798) wikipedia'da.

Dört örnek senaryolar verilmiştir:

- Senaryo 1: bir işlevin dönüş türü kaydırma:

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

- Senaryo 2: varsayılan bağımsız bir işlev parametresi ekleme:

```cpp
    template <your_stuff>
your_return_type_if_present
    yourfunction(args, enable_if_t<your condition, FOO> = BAR) {// ...
 }
```

- Senaryo 3: varsayılan bağımsız bir şablon parametresi ekleme:

```cpp
    template <your_stuff, typename Dummy = enable_if_t<your_condition>>
rest_of_function_declaration_goes_here
```

- Senaryo 4: işlevinizi şablonlu olmayan bir bağımsız değişkeni varsa, kendi türü kayabilir:

```cpp
    template <typename T>
void your_function(const T& t,
    enable_if_t<is_something<T>::value, const string&>
s) {// ...
 }
```

Dönüş türleri olmadığından Senaryo 1 oluşturucular ve dönüştürme işleçleri ile çalışmaz.

Senaryo 2 adlandırılmamış parametre bırakır. Diyebilirsiniz `::type Dummy = BAR`, ancak adı `Dummy` ilgisiz, olduğundan ve bir ad verip "başvurulmayan parametre" uyarı tetiklemek büyük olasılıkla. Seçmeniz gerekir bir `FOO` işlev parametre türü ve `BAR` varsayılan bağımsız değişkeni.  Diyebilirsiniz `int` ve `0`, ancak ardından kodunuzu kullanıcılarının yanlışlıkla işleve yok sayılırdı fazladan bir tamsayı geçirebilirdiniz. Bunun yerine, kullanmanızı öneririz `void **` ve her iki `0` veya `nullptr` neredeyse hiçbir şey dönüştürülebilir olduğundan `void **`:

```cpp
template <your_stuff>
your_return_type_if_present
yourfunction(args, typename enable_if<your_condition, void **>::type = nullptr) {// ...
}
```

Senaryo 2 sıradan oluşturucuları için de çalışır.  Ancak, ek parametreleri alamıyor çünkü dönüşüm işleçleri için işe yaramaz.  Ayrıca için işe yaramaz [variadic](../cpp/ellipses-and-variadic-templates.md) oluşturucular anlaşılan olmayan bir içerik paketi işlev parametresi yapar ve böylece, uramayacak ek parametreler eklemek için `enable_if`.

Senaryo 3 kullanan adı `Dummy`, ancak isteğe bağlıdır. Yalnızca " `typename = typename`" çalışır, ancak bu tuhaf arar düşünüyorsanız, bir "kukla" adı kullanabilirsiniz — yalnızca bir işlev tanımı'nda da kullanılabilir kullanmayın. Bir türe vermeyin varsa `enable_if`hükümsüz kılmak için varsayılan olarak ve mükemmel olan ne önemli değil çünkü makul `Dummy` olduğu. Bu her şeyi için dönüşüm işleçleri dahil olmak üzere çalışır ve [variadic](../cpp/ellipses-and-variadic-templates.md) oluşturucular.

Senaryo 4 dönüş türleri yok kurucularda çalışır ve böylece kaydırma sınırlama senaryosu 1 çözer.  Bununla birlikte, her zaman kullanılabilir olmayan şablonlu olmayan işlevi bağımsız için Senaryo 4 sınırlıdır.  (Senaryo 4 bir şablonlu işlevi bağımsız değişken kullanarak şablon bağımsız değişken kesintisi üzerinde çalışmasını önler.)

`enable_if` güçlü, ancak bunu yanlış olmadığını da tehlikeli olur.  Amacı yanlış, aşırı yükleme çözünürlüğü önce kaybolur aday olun çünkü etkileri çok kafa karıştırıcı olabilir.  Bazı öneriler şunlardır:

- Kullanmayın `enable_if` derleme zamanında uygulamaları arasındaki seçin. Şimdiye kadar bir yazmayın `enable_if` için `CONDITION` için başka bir `!CONDITION`.  Bunun yerine, bir *etiketi gönderme* düzeni — yineleyiciler gücü bağlı olarak uygulamaları seçen bir algoritma, örneğin, verilir.

- Kullanmayın `enable_if` gereksinimleri zorlamak için.  Şablon parametreleri doğrulamak istiyorsanız ve doğrulama başarısız olursa, başka bir uygulama seçmek yerine bir hata neden, kullanma [static_assert](../cpp/static-assert.md).

- Kullanım `enable_if` aksi iyi yapar bir aşırı yüklemesini kümesi olduğunda, kod belirsiz.  Çoğu zaman oluşturucular örtük dönüştürme içinde gerçekleşir.

## <a name="example"></a>Örnek

Bu örnekte açıklanmıştır nasıl C++ Standart kitaplığı şablon işlevi [std::make_pair()](../standard-library/utility-functions.md#make_pair) avantajlarından yararlanır `enable_if`.

```cpp
void func(const pair<int, int>&);

void func(const pair<string, string>&);

func(make_pair("foo", "bar"));
```

Bu örnekte, `make_pair("foo", "bar")` döndürür `pair<const char *, const char *>`. Aşırı yükleme çözümü vardır, belirlemek `func()` istiyor. `pair<A, B>` örtük dönüştürme oluşturucudan sahip `pair<X, Y>`.  Bu yeni değildir — C ++ 98 oluştu. Olsa bile ancak, C ++ 98/03, örtük dönüştürme Oluşturucusu ait imza her zaman, mevcut `pair<int, int>(const pair<const char *, const char *>&)`.  Aşırı yükleme çözümü değil verdiğiniz bu oluşturucu örneği girişimi nedeniyle horribly dağıtır `const char *` örtük olarak dönüştürülebilir değil `int`; imzaları yalnızca arıyor, önce işlev tanımları oluşturulur.  İmzaları dönüştürmek için olduğundan bu nedenle, örnek kod, belirsiz `pair<const char *, const char *>` her ikisine de `pair<int, int>` ve `pair<string, string>`.

C ++ 11 kullanarak bu belirsizlik Çözüldü `enable_if` emin olmak için `pair<A, B>(const pair<X, Y>&)` var. **yalnızca** zaman `const X&` örtük olarak parametresinin `A` ve `const Y&` içinörtükolarakparametresinin`B`.  Bu, belirlemek aşırı yükleme çözümü sağlar `pair<const char *, const char *>` parametresinin `pair<int, int>` ve aşırı alan `pair<string, string>` kurtarılamaz.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
