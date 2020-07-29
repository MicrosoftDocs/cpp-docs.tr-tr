---
title: enable_if Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::enable_if
helpviewer_keywords:
- enable_if class
- enable_if
ms.assetid: c6b8d41c-a18f-4e30-a39e-b3aa0e8fd926
ms.openlocfilehash: 1017fc315a4440350a0190cf4b40e644cda16876
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230045"
---
# <a name="enable_if-class"></a>enable_if Sınıfı

SFıNAE aşırı yükleme çözümlemesi için bir türün örneğini koşullu olarak oluşturur. İç içe geçmiş typedef bulunur `enable_if<Condition,Type>::type` — ve yalnızca ise, için bir eş anlamlı olur `Type` `Condition` **`true`** .

## <a name="syntax"></a>Söz dizimi

```cpp
template <bool B, class T = void>
struct enable_if;
```

### <a name="parameters"></a>Parametreler

*Kenarı*\
Sonuç türünün varlığını belirleyen değer.

*Şı*\
*B* true ise örneklendirilecek tür.

## <a name="remarks"></a>Açıklamalar

*B* true ise `enable_if<B, T>` *T*için bir eş anlamlı olan "Type" adlı iç içe geçmiş bir typedef öğesine sahiptir.

*B* yanlış ise, `enable_if<B, T>` "tür" adlı iç içe typedef yoktur.

Bu diğer ad şablonu sağlanır:

```cpp
template <bool B, class T = void>
using enable_if_t = typename enable_if<B,T>::type;
```

C++ ' da, şablon parametrelerinin değiştirme hatası kendi kendine bir hata değildir. Bu, *SFINAE* olarak adlandırılır (değiştirme hatası bir hata değildir). Genellikle `enable_if` aşırı yükleme çözümünden adayları kaldırmak için kullanılır — diğer bir deyişle, aşırı yükleme kümesi, yani bir tanımın başka bir şekilde reddedilebilmesini sağlar. Bu, SFıNAE davranışına uyar. SFıNAE hakkında daha fazla bilgi için bkz. değiştirme hatası, Vikipde [hata değildir](https://go.microsoft.com/fwlink/p/?linkid=394798) .

Dört örnek senaryo aşağıda verilmiştir:

- Senaryo 1: bir işlevin dönüş türünü sarmalama:

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

- Senaryo 2: varsayılan bağımsız değişkenine sahip bir işlev parametresi ekleme:

```cpp
    template <your_stuff>
your_return_type_if_present
    yourfunction(args, enable_if_t<your condition, FOO> = BAR) {// ...
}
```

- Senaryo 3: varsayılan bağımsız değişkenine sahip bir şablon parametresi ekleme:

```cpp
    template <your_stuff, typename Dummy = enable_if_t<your_condition>>
rest_of_function_declaration_goes_here
```

- Senaryo 4: işlevinizde Şablonsuz olmayan bir bağımsız değişken varsa, türünü kaydırabilirsiniz:

```cpp
    template <typename T>
void your_function(const T& t,
    enable_if_t<is_something<T>::value, const string&>
s) {// ...
}
```

Dönüş türleri olmadığından, senaryo 1 oluşturucular ve dönüştürme işleçleri ile çalışmaz.

Senaryo 2, parametresini adlandırılmamış halde bırakır. `::type Dummy = BAR`Ancak ad `Dummy` ilgisiz olur ve bir ad, "başvurulmayan parametre" uyarısını tetikleyeolasıdır. Bir `FOO` işlev parametresi türü ve `BAR` Varsayılan bağımsız değişken seçmeniz gerekir.  **`int`** Ve `0` , ancak kodunuzun kullanıcıları yanlışlıkla, yoksayılması gereken ek bir tamsayı ile işleve geçirebilir. Bunun yerine, veya ' yi kullanmanız önerilir, `void **` `0` **`nullptr`** ancak neredeyse hiçbir şey şu şekilde dönüştürülebilir `void **` :

```cpp
template <your_stuff>
your_return_type_if_present
yourfunction(args, typename enable_if<your_condition, void **>::type = nullptr) {// ...
}
```

Ayrıca, Senaryo 2 sıradan oluşturucular için de kullanılabilir.  Ancak, ek parametreler almadıklarından, dönüştürme işleçleri için çalışmaz.  Ayrıca, fazladan parametre eklemek [variadic](../cpp/ellipses-and-variadic-templates.md) işlev parametre paketini çıkarılamayan bir bağlam yapar ve bu nedenle amacını erteler `enable_if` .

Senaryo 3, adı kullanır `Dummy` , ancak isteğe bağlıdır. Yalnızca " `typename = typename` " çalışır, ancak tuhaf göründüğünü düşünüyorsanız, "kukla" adı kullanabilirsiniz; işlev tanımında de kullanılabilecek bir tane kullanmayın. Bir tür belirtmezseniz `enable_if` , varsayılan olarak void olur ve ne olduğunu merak etmeyin `Dummy` . Bu, dönüştürme işleçleri ve [değişen sayıda bağımsız](../cpp/ellipses-and-variadic-templates.md) Oluşturucu dahil her şey için geçerlidir.

Senaryo 4, dönüş türleri olmayan oluşturucular içinde çalışarak Senaryo 1 ' in sarmalama sınırlamasını çözer.  Ancak Senaryo 4, her zaman kullanılabilir olmayan Şablonsuz işlev bağımsız değişkenleriyle sınırlandırılmıştır.  (Şablonlu işlev bağımsız değişkeninde Senaryo 4 kullanılması, şablon bağımsız değişkeni üzerinde çalışmaya engel olur.)

`enable_if`güçlüdür, ancak kötüye kullanılan ise tehlikeli olur.  Amaç, aşırı yükleme çözünürlüğünden önce adayları bir bütün hale getirmek olduğundan, bu kötü amaçlı olduğunda, etkileri çok karmaşık olabilir.  Bazı öneriler aşağıda verilmiştir:

- `enable_if`Derleme zamanında uygulamalar arasında seçim yapmak için kullanmayın. İçin bir ve için bir tane kullanmayın `enable_if` `CONDITION` `!CONDITION` .  Bunun yerine, verilen yineleyicilerin güçlerine bağlı olarak uygulamaları seçen bir algoritma gibi bir *etiket gönderme* modelini kullanın.

- `enable_if`Gereksinimleri zorlamak için kullanmayın.  Şablon parametrelerini doğrulamak istiyorsanız ve doğrulama başarısız olursa, başka bir uygulama seçmek yerine bir hataya neden oluyorsa [static_assert](../cpp/static-assert.md)kullanın.

- `enable_if`Başka türlü iyi kod belirsiz hale getiren bir aşırı yükleme kümesi olduğunda kullanın.  Çoğu zaman, bu durum örtük olarak dönüşümde Oluşturucu olarak oluşur.

## <a name="example"></a>Örnek

Bu örnekte, standart [:: make_pair ()](../standard-library/utility-functions.md#make_pair) C++ standart kitaplığı şablon işlevinin avantajı açıklanmaktadır `enable_if` .

```cpp
void func(const pair<int, int>&);

void func(const pair<string, string>&);

func(make_pair("foo", "bar"));
```

Bu örnekte, `make_pair("foo", "bar")` döndürür `pair<const char *, const char *>` . Aşırı yükleme çözümünün, istediğinizi belirlemesi `func()` gerekir. `pair<A, B>`, ' den örtük olarak dönüştürme yapıcısına sahiptir `pair<X, Y>` .  Bu yeni değil — C++ 98 ' de. Ancak, C++ 98/03 ' de örtük olarak dönüştürme oluşturucunun imzası, olsa bile, her zaman vardır `pair<int, int>(const pair<const char *, const char *>&)` .  Aşırı yükleme çözümlemesi `const char *` , örtülü olarak dönüştürülebilir olmadığından **`int`** ve yalnızca imzalara bakıyor, işlev tanımlarının örneklendirilmesinden önce, bu oluşturucuyu bir örnek oluşturma girişiminde bulunur.  Bu nedenle, imzaların hem hem de öğesine dönüştürülmesi için, örnek kod belirsizdir `pair<const char *, const char *>` `pair<int, int>` `pair<string, string>` .

C++ 11, `enable_if` `pair<A, B>(const pair<X, Y>&)` **yalnızca** `const X&` örtülü olarak dönüştürülebilir `A` ve `const Y&` örtülü olarak dönüştürülebilir `B` olduğundan emin olmak için kullanarak bu belirsizliği ortadan çözülür.  Bu, aşırı yükleme çözümünün, `pair<const char *, const char *>` ' a dönüştürülebilir olmayan ve uygun olan aşırı yüklemeye göre belirlenmesini sağlar `pair<int, int>` `pair<string, string>` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
