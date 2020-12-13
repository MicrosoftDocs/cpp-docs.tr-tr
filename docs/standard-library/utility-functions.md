---
description: 'Daha fazla bilgi edinin: &lt; yardımcı program &gt; işlevleri'
title: '&lt;yardımcı program &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- utility/std::exchange
- utility/std::forward
- utility/std::make_pair
- utility/std::move
- utility/std::swap
ms.assetid: b1df38cd-3a59-4098-9c81-83342eb719a4
helpviewer_keywords:
- std::exchange [C++]
- std::forward [C++]
- std::make_pair [C++]
- std::move [C++]
- std::swap [C++]
ms.openlocfilehash: 421f9a24d59d25e03f5b947c2c68cbecb4a71b3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153479"
---
# <a name="ltutilitygt-functions"></a>&lt;yardımcı program &gt; işlevleri

## <a name="as_const"></a><a name="asconst"></a> as_const

```cpp
template <class T> constexpr add_const_t<T>& as_const(T& t) noexcept;
template <class T> void as_const(const T&&) = delete;
```

### <a name="return-value"></a>Dönüş Değeri

*T* döndürür.

## <a name="declval"></a><a name="declval"></a> declval

```cpp
template <class T> add_rvalue_reference_t<T> declval() noexcept;  // as unevaluated operand
```

## <a name="exchange"></a><a name="exchange"></a> değişimi

**(C++ 14)** Nesnesine yeni bir değer atar ve eski değerini döndürür.

```cpp
template <class T, class Other = T>
    T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>Parametreler

*Acil*\
New_val değerini alacak nesne.

*new_val*\
Değeri kopyalanmış veya Val 'e taşınan nesne.

### <a name="remarks"></a>Açıklamalar

Karmaşık türler için, `exchange` bir taşıma Oluşturucusu kullanılabilir olduğunda eski değerin kopyalanmasını önler, geçici bir nesne ise veya taşınmışsa yeni değeri kopyalamayı önler ve kullanılabilir herhangi bir dönüştürme atama işlecini kullanarak yeni değer olarak herhangi bir türü kabul eder. Exchange işlevi, sol bağımsız değişkenin sağ bağımsız değişkenine taşınmadığından veya kopyalanmadığı için [std:: Swap](../standard-library/algorithm-functions.md#swap) 'dan farklıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını göstermektedir `exchange` . Gerçek dünyada, `exchange` kopyalamanın pahalı olduğu büyük nesneler ile en çok yararlı olur:

```cpp
#include <utility>
#include <iostream>

using namespace std;

struct C
{
   int i;
   //...
};

int main()
{
   // Use brace initialization
   C c1{ 1 };
   C c2{ 2 };
   C result = exchange(c1, c2);
   cout << "The old value of c1 is: " << result.i << endl;
   cout << "The new value of c1 after exchange is: " << c1.i << endl;

   return 0;
}
```

```Output
The old value of c1 is: 1
The new value of c1 after exchange is: 2
```

## <a name="forward"></a><a name="forward"></a> tirler

Bağımsız değişken bir rvalue'da veya rvalue başvurusundaysa, bağımsız değişkenini bir rvalue başvurusuna koşullu olarak yayınlar. Bu, bir bağımsız değişkenin rvalue olma durumunu mükemmel iletim desteği sunarak iletim işlevine geri yükler.

```cpp
template <class Type>    // accepts lvalues
    constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
    constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Bağımsız değişken türünden farklı olabilecek, *arg* içinde geçirilen değerin *türü.* Genellikle iletme işlevinin bir şablon bağımsız değişkeni tarafından belirlenir.

*Değişkeni*\
Yayınlama için bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

*Bağımsız* değişken içinde geçirilen değer ilk olarak bir rvalue veya bir rvalue başvurusu Ise, *arg* 'a bir rvalue başvurusu döndürür; Aksi takdirde, türünü değiştirmeden *bağımsız değişken* döndürür.

### <a name="remarks"></a>Açıklamalar

Çağırmak için açık bir şablon bağımsız değişkeni belirtmeniz gerekir `forward` .

`forward` bağımsız değişkenini iletmez. Bunun yerine, bağımsız değişkenini koşulsuz olarak bir rvalue başvurusuna atama, ilk bir rvalue veya rvalue başvurusu ise, `forward` derleyicinin iletilen bağımsız değişkenin özgün türü hakkında bilgi vererek aşırı yükleme çözümlemesi gerçekleştirmesini sağlar. Bir iletme işlevinin bağımsız değişkeninin görünen türü, özgün türünden farklı olabilir — Örneğin, bir rvalue bir işlev için bağımsız değişken olarak kullanıldığında ve bir parametre adına bağlıysa; bir ada sahip olmak, bu değeri bir lvalue olarak yapar; bu değer bir rvalue olarak, `forward` bağımsız değişkenin rvalue olma durumunu geri yükler.

Bir bağımsız değişkenin özgün değerinin rvalue olma durumunu aşırı yükleme çözümüne geri yüklemek, *kusursuz iletme* olarak bilinir. Kusursuz iletme bir şablon işlevinin her iki başvuru türünün bağımsız değişkenini kabul etmesini ve aşırı yük çözümlemeleri yapılması gerektiğinde rvalue durumunu geri yüklemesini sağlar. Kusursuz iletme kullanarak, rvalues için taşıma semantiğini koruyabilir ve bağımsız değişkenlerinin yalnızca başvuru türüne göre çeşitlenen işlevler için aşırı yük sağlanmasını önleyebilirsiniz.

## <a name="from_chars"></a><a name="from_chars"></a> from_chars

```cpp
from_chars_result from_chars(const char* first, const char* last, see below& value, int base = 10);

from_chars_result from_chars(const char* first, const char* last, float& value, chars_format fmt = chars_format::general);

from_chars_result from_chars(const char* first, const char* last, double& value, chars_format fmt = chars_format::general);

from_chars_result from_chars(const char* first, const char* last, long double& value, chars_format fmt = chars_format::general);
```

## <a name="get"></a><a name="get"></a> Al

Bir `pair` nesneden dizin konumuna veya türe göre bir öğe alır.

```cpp
// get reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&
    get(pair<T1, T2>& Pr) noexcept;

// get reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1& get(pair<T1, T2>& Pr) noexcept;

// get reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2& get(pair<T1, T2>& Pr) noexcept;

// get const reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr const tuple_element_t<Index, pair<T1, T2>>&
    get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr const T1& get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr const T2& get(const pair<T1, T2>& Pr) noexcept;

// get rvalue reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&&
    get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1&& get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2&& get(pair<T1, T2>&& Pr) noexcept;
```

### <a name="parameters"></a>Parametreler

*İndeks*\
Seçilen öğenin 0 tabanlı dizini.

*T1*\
İlk çift öğenin türü.

*T2*\
İkinci çift öğesinin türü.

*çekme isteği*\
Seçilecek çift.

### <a name="remarks"></a>Açıklamalar

Şablon işlevleri, her biri bağımsız değişkeninin bir öğesine bir başvuru döndürür `pair` .

Dizinli aşırı yüklemeler için, *Dizin* değeri 0 ise işlevler döndürülür `pr.first` ve *Dizin* değeri 1 ise işlevler döndürülür `pr.second` . Tür `RI` döndürülen öğenin türüdür.

Dizin parametresi olmayan aşırı yüklemeler için, döndürülecek öğe tür bağımsız değişkeni tarafından anlaşıyor. Çekme isteği `get<T>(Tuple)` T türünde birden fazla veya  daha az öğe içeriyorsa, çağırma bir derleyici hatası oluşturur.

### <a name="example"></a>Örnek

```cpp
#include <utility>
#include <iostream>
using namespace std;
int main()
{

    typedef pair<int, double> MyPair;

    MyPair c0(9, 3.14);

    // get elements by index
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0) << endl;

    // get elements by type (C++14)
    MyPair c1(1, 0.27);
    cout << " " << get<int>(c1);
    cout << " " << get<double>(c1) << endl;
}
```

```Output
9 3.14
1 0.27
```

## <a name="index_sequence"></a><a name="index_sequence"></a> index_sequence

```cpp
template<size_t... I>
    using index_sequence = integer_sequence<size_t, I...>;
```

## <a name="index_sequence_for"></a><a name="index_sequence_for"></a> index_sequence_for

```cpp
template<class... T>
    using index_sequence_for = make_index_sequence<sizeof...(T)>;
```

## <a name="make_index_sequence"></a><a name="make_index_sequence"></a> make_index_sequence

```cpp
template<size_t N>
    using make_index_sequence = make_integer_sequence<size_t, N>;
```

## <a name="make_integer_sequence"></a><a name="make_integer_sequence"></a> make_integer_sequence

```cpp
template<class T, T N>
    using make_integer_sequence = integer_sequence<T, see below >;
```

## <a name="make_pair"></a><a name="make_pair"></a> make_pair

Türü nesneleri oluşturmak için kullanabileceğiniz bir şablon işlevi `pair` , bileşen türlerinin parametre olarak geçirilen veri türlerine göre otomatik olarak seçildiği yerdir.

```cpp
template <class T, class U>
    pair<T, U> make_pair(T& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T& Val1, U&& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U&& Val2);
```

### <a name="parameters"></a>Parametreler

*Val1*\
İlk öğesini Başlatan değer `pair` .

*Val2 & lt*\
İkinci öğesini Başlatan değer `pair` .

### <a name="return-value"></a>Dönüş Değeri

Oluşturulan çift nesne: `pair` < `T` , `U`> ( `Val1` , `Val2` ).

### <a name="remarks"></a>Açıklamalar

`make_pair`[Reference_wrapper sınıfının](../standard-library/reference-wrapper-class.md) nesne türünü başvuru türlerine dönüştürür ve dizi dizilerini ve işlevleri işaretçilere dönüştürür.

Döndürülen `pair` nesnede, `T` şöyle belirlenir:

- Giriş türü ise, `T` `reference_wrapper<X>` döndürülen tür `T` olur `X&` .

- Aksi takdirde, döndürülen tür `T` olur `decay<T>::type` . [Decay sınıfı](../standard-library/decay-class.md) desteklenmiyorsa, döndürülen tür `T` giriş türüyle aynıdır `T` .

Döndürülen tür, `U` giriş türünden benzer şekilde belirlenir `U` .

Uygulamasının bir avantajı, `make_pair` depolanan nesne türlerinin derleyici tarafından otomatik olarak belirlenmesi ve açıkça belirtilmesi gerekmez. Verbose gibi açık şablon bağımsız değişkenleri kullanmayın `make_pair<int, int>(1, 2)` `make_pair` ve derleme hatasına neden olabilecek karmaşık rvalue başvuru sorunları ekler. Bu örnekte, doğru sözdizimi `make_pair(1, 2)`

`make_pair`Yardımcı işlevi aynı zamanda, giriş parametresi olarak çift değeri gerektiren bir işleve iki değer geçişini olanaklı kılar.

### <a name="example"></a>Örnek

Bir çifti bildirmek ve başlatmak için yardımcı işlevin nasıl kullanılacağına ilişkin bir örnek için `make_pair` bkz. [çifte yapısı](../standard-library/pair-structure.md).

## <a name="move"></a><a name="move"></a> geçiş

Kendi bağımsız değişkenini koşulsuz olarak bir rvalue başvurusuna yayınlar ve böylece kendi türünün taşınması etkinse, taşınabileceğini belirtir.

```cpp
template <class Type>
    constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Başvuru daraltma kurallarıyla birlikte *, bağımsız değişken içinde geçirilen* bağımsız değişkenin türünden çıkarılan bir tür.

*Değişkeni*\
Yayınlama için bağımsız değişkeni. *Bağımsız değişken* türü bir rvalue başvurusu olarak belirtilmiş gibi görünse de, lvalue başvuruları `move` rvalue başvurularına bağlayabildiğinden lvalue bağımsız değişkenlerini de kabul eder.

### <a name="return-value"></a>Dönüş Değeri

`Arg` bir rvalue başvurusu olarak, türünün bir başvuru türü olup olmadığı.

### <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişken *türü* açık olarak belirtilmemiştir, ancak *bağımsız* değişken içinde geçirilen değerin türünden çıkarsanmalıdır. *Tür* türü, başvuru daraltma kurallarına göre daha sonra ayarlanır.

`move` bağımsız değişkenini taşımaz. Bunun yerine, bir lvalue olabilecek bağımsız değişkenini koşulsuz olarak atama (bir lvalue olabilir), bir rvalue başvurusuna, derleyicinin, türü taşıma özelliği etkin olduğunda, *değişken* olarak geçirilen değeri kopyalamak yerine daha sonra taşımasını sağlar. Türü taşı etkin değilse, bunun yerine kopyalanmış olur.

*Bağımsız değişken* içinde geçirilen değer bir lvalue ise — diğer bir deyişle, bir ada sahip veya adresi alınabilir — taşıma gerçekleştiğinde geçersiz kılınır. Taşındıktan sonra adı veya adresi tarafından *bağımsız değişken* olarak geçirilen değere başvurmayın.

## <a name="move_if_noexcept"></a><a name="moveif"></a> move_if_noexcept

```cpp
template <class T> constexpr conditional_t< !is_nothrow_move_constructible_v<T> && is_copy_constructible_v<T>, const T&, T&&> move_if_noexcept(T& x) noexcept;
```

## <a name="swap"></a><a name="swap"></a> Kur

İki tür veya [çift yapı](../standard-library/pair-structure.md) nesnesinin öğelerini değiş tokuş eder.

```cpp
template <class T>
    void swap(T& left, T& right) noexcept(see below );
template <class T, size_t N>
    void swap(T (&left)[N], T (&right)[N]) noexcept(is_nothrow_swappable_v<T>);
template <class T, class U>
    void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Türü veya türü bir nesne `pair` .

*Right*\
Türü veya türü bir nesne `pair` .

### <a name="remarks"></a>Açıklamalar

Uygulamasının bir avantajı, `swap` depolanan nesne türlerinin derleyici tarafından otomatik olarak belirlenmesi ve açıkça belirtilmesi gerekmez. Verbose gibi açık şablon bağımsız değişkenleri kullanmayın `swap<int, int>(1, 2)` `swap` ve derleme hatasına neden olabilecek karmaşık rvalue başvuru sorunları ekler.

## <a name="to_chars"></a><a name="to_chars"></a> to_chars

```cpp
to_chars_result to_chars(char* first, char* last, see below value, int base = 10);
to_chars_result to_chars(char* first, char* last, float value);
to_chars_result to_chars(char* first, char* last, double value);
to_chars_result to_chars(char* first, char* last, long double value);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt, int precision);
```

### <a name="remarks"></a>Açıklamalar

Aralığı doldurarak değeri bir karakter dizesine dönüştürür; `[first, last)` burada `[first, last)` geçerli bir Aralık olması gerekir.
