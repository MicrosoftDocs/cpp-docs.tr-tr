---
title: enable_if Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::enable_if
helpviewer_keywords:
- enable_if class
- enable_if
ms.assetid: c6b8d41c-a18f-4e30-a39e-b3aa0e8fd926
ms.openlocfilehash: 6e6b8a286dca8c451e6920e7f25f07829d3b453f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454209"
---
# <a name="enableif-class"></a>enable_if Sınıfı

SFıNAE aşırı yükleme çözümlemesi için bir türün örneğini koşullu olarak oluşturur. İç içe geçmiş `enable_if<Condition,Type>::type` typedef bulunur — ve yalnızca `Condition` **true**ise `Type`, için bir eş anlamlı olur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <bool B, class T = void>
struct enable_if;
```

### <a name="parameters"></a>Parametreler

*KENARI*\
Sonuç türünün varlığını belirleyen değer.

*ŞI*\
*B* true ise örneklendirilecek tür.

## <a name="remarks"></a>Açıklamalar

*B* true `enable_if<B, T>` ise *T*için bir eş anlamlı olan "Type" adlı iç içe geçmiş bir typedef öğesine sahiptir.

*B* yanlış ise, `enable_if<B, T>` "tür" adlı iç içe typedef yoktur.

Bu diğer ad şablonu sağlanır:

```cpp
template <bool B, class T = void>
using enable_if_t = typename enable_if<B,T>::type;
```

' C++De, şablon parametrelerinin değiştirme hatası kendiliğinden bir hata değildir. Bu, *SFINAE* olarak adlandırılır (değiştirme hatası bir hata değildir). `enable_if` Genellikle aşırı yükleme çözümünden adayları kaldırmak için kullanılır — diğer bir deyişle, aşırı yükleme kümesi, yani bir tanımın başka bir şekilde reddedilebilmesini sağlar. Bu, SFıNAE davranışına uyar. SFıNAE hakkında daha fazla bilgi için bkz. değiştirme hatası, Vikipde [hata değildir](https://go.microsoft.com/fwlink/p/?linkid=394798) .

Dört örnek senaryo aşağıda verilmiştir:

- Senaryo 1: Bir işlevin dönüş türünü sarmalama:

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

- Senaryo 2: Varsayılan bağımsız değişkeni olan bir işlev parametresi ekleniyor:

```cpp
    template <your_stuff>
your_return_type_if_present
    yourfunction(args, enable_if_t<your condition, FOO> = BAR) {// ...
}
```

- Senaryo 3: Varsayılan bağımsız değişkenine sahip bir şablon parametresi ekleme:

```cpp
    template <your_stuff, typename Dummy = enable_if_t<your_condition>>
rest_of_function_declaration_goes_here
```

- Senaryo 4: İşlevinizde Şablonsuz bir bağımsız değişken varsa, türünü kaydırabilirsiniz:

```cpp
    template <typename T>
void your_function(const T& t,
    enable_if_t<is_something<T>::value, const string&>
s) {// ...
}
```

Dönüş türleri olmadığından, senaryo 1 oluşturucular ve dönüştürme işleçleri ile çalışmaz.

Senaryo 2, parametresini adlandırılmamış halde bırakır. `::type Dummy = BAR`Ancak ad`Dummy` ilgisiz olur ve bir ad, "başvurulmayan parametre" uyarısını tetikleyeolasıdır. Bir `FOO` işlev parametresi türü ve `BAR` varsayılan bağımsız değişken seçmeniz gerekir.  **İnt** ve ile `0`söyleyebilirsiniz, ancak kodunuzun kullanıcıları yanlışlıkla yok sayılacak fazladan bir tamsayı işlevine geçirebilir. Bunun yerine, neredeyse hiçbir şey `void **` dönüştürülemediğinden `void **`, `0` ya da **nullptr** kullanmanızı öneririz:

```cpp
template <your_stuff>
your_return_type_if_present
yourfunction(args, typename enable_if<your_condition, void **>::type = nullptr) {// ...
}
```

Ayrıca, Senaryo 2 sıradan oluşturucular için de kullanılabilir.  Ancak, ek parametreler almadıklarından, dönüştürme işleçleri için çalışmaz.  Ayrıca, fazladan parametre eklemek [](../cpp/ellipses-and-variadic-templates.md) işlev parametre paketini çıkarılamayan bir bağlam yapar ve bu nedenle amacını `enable_if`erteler.

Senaryo 3, adı `Dummy`kullanır, ancak isteğe bağlıdır. Yalnızca " `typename = typename`" çalışır, ancak tuhaf göründüğünü düşünüyorsanız, "kukla" adı kullanabilirsiniz; işlev tanımında de kullanılabilecek bir tane kullanmayın. Bir tür `enable_if`belirtmezseniz, varsayılan olarak void olur ve ne `Dummy` olduğunu merak etmeyin. Bu, dönüştürme işleçleri ve [değişen sayıda bağımsız](../cpp/ellipses-and-variadic-templates.md) Oluşturucu dahil her şey için geçerlidir.

Senaryo 4, dönüş türleri olmayan oluşturucular içinde çalışarak Senaryo 1 ' in sarmalama sınırlamasını çözer.  Ancak Senaryo 4, her zaman kullanılabilir olmayan Şablonsuz işlev bağımsız değişkenleriyle sınırlandırılmıştır.  (Şablonlu işlev bağımsız değişkeninde Senaryo 4 kullanılması, şablon bağımsız değişkeni üzerinde çalışmaya engel olur.)

`enable_if`güçlüdür, ancak kötüye kullanılan ise tehlikeli olur.  Amaç, aşırı yükleme çözünürlüğünden önce adayları bir bütün hale getirmek olduğundan, bu kötü amaçlı olduğunda, etkileri çok karmaşık olabilir.  Bazı öneriler aşağıda verilmiştir:

- Derleme zamanında uygulamalar `enable_if` arasında seçim yapmak için kullanmayın. İçin bir `enable_if` `CONDITION` ve içinbirtanekullanmayın.`!CONDITION`  Bunun yerine, verilen yineleyicilerin güçlerine bağlı olarak uygulamaları seçen bir algoritma gibi bir *etiket gönderme* modelini kullanın.

- Gereksinimleri zorlamak için `enable_if` kullanmayın.  Şablon parametrelerini doğrulamak istiyorsanız ve doğrulama başarısız olursa, başka bir uygulama seçmek yerine bir hataya neden oluyorsa, [static_assert](../cpp/static-assert.md)kullanın.

- Başka `enable_if` türlü iyi kod belirsiz hale getiren bir aşırı yükleme kümesi olduğunda kullanın.  Çoğu zaman, bu durum örtük olarak dönüşümde Oluşturucu olarak oluşur.

## <a name="example"></a>Örnek

Bu örnekte, C++ [std:: make_pair ()](../standard-library/utility-functions.md#make_pair) standart kitaplık şablonu işlevinin avantajı `enable_if`açıklanmaktadır.

```cpp
void func(const pair<int, int>&);

void func(const pair<string, string>&);

func(make_pair("foo", "bar"));
```

Bu örnekte, `make_pair("foo", "bar")` döndürür `pair<const char *, const char *>`. Aşırı yükleme çözümünün, istediğinizi belirlemesi `func()` gerekir. `pair<A, B>`, ' den `pair<X, Y>`örtük olarak dönüştürme yapıcısına sahiptir.  Bu yeni değil — C++ 98 ' de. Ancak, C++ 98/03 ' de örtük olarak dönüştürme oluşturucunun imzası, olsa bile `pair<int, int>(const pair<const char *, const char *>&)`, her zaman vardır.  Aşırı yükleme çözümlemesi, dolaylı olarak `const char *` **int**'e dönüştürülemediğinden, bu oluşturucunun bir örneğini oluşturma girişiminin yatay olarak bir örneklenme denemesi yapmaz; ancak yalnızca imzalara bakıyor, işlev tanımlarının örneği oluşturulmadan önce.  Bu nedenle, imzaların `pair<const char *, const char *>` `pair<int, int>` hem hem de öğesine dönüştürülmesi için, örnek kod belirsizdir. `pair<string, string>`

C++ 11 `enable_if` ,  `pair<A, B>(const pair<X, Y>&)` yalnızca`const X&`örtülü olarak dönüştürülebilir ve`const Y&`örtülü olarak dönüştürülebilir`B`olduğundan emin olmak için kullanarak bu belirsizliği ortadan çözülür. `A`  Bu, aşırı yükleme çözümünün, ' `pair<const char *, const char *>` a dönüştürülebilir olmayan ve `pair<int, int>` uygun olan aşırı `pair<string, string>` yüklemeye göre belirlenmesini sağlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
