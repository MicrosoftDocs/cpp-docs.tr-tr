---
title: '&lt;yardımcı programı&gt; işlevleri'
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
ms.openlocfilehash: 723b077500b9b741445efcd8574fb26cd53e5fc7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246305"
---
# <a name="ltutilitygt-functions"></a>&lt;yardımcı programı&gt; işlevleri

## <a name="asconst"></a> as_const

```cpp
template <class T> constexpr add_const_t<T>& as_const(T& t) noexcept;
template <class T> void as_const(const T&&) = delete;
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür *T*.

## <a name="declval"></a> declval

```cpp
template <class T> add_rvalue_reference_t<T> declval() noexcept;  // as unevaluated operand
```

## <a name="exchange"></a> Exchange

**(C ++ 14)**  Bir nesneye yeni bir değer atar ve eski değeri döndürür.

```cpp
template <class T, class Other = T>
    T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>Parametreler

*VAL*\
New_val değeri alacak nesne.

*new_val*\
Nesne değeri kopyalanamaz ya da val taşındı.

### <a name="remarks"></a>Açıklamalar

Karmaşık türler için `exchange` taşıma oluşturucusu yok, geçici bir nesne veya taşınır ve her türlü kullanılabilir dönüştürme atama işlecinden kullanarak yeni değer kabul eder, yeni değeri kopyalamaktan kaçınır olduğunda eski değeri kopyalamaktan kaçınır. Exchange işlevi farklıdır [std::swap](../standard-library/algorithm-functions.md#swap) sol bağımsız değişkeni değil veya taşınmış doğru bağımsız kopyalanan.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `exchange`. Gerçek dünyada `exchange` kopyalamak pahalı olan büyük nesneleri ile kullanışlıdır:

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

## <a name="forward"></a> İleriye doğru

Bağımsız değişken bir rvalue'da veya rvalue başvurusundaysa, bağımsız değişkenini bir rvalue başvurusuna koşullu olarak yayınlar. Bu, bir bağımsız değişkenin rvalue olma durumunu mükemmel iletim desteği sunarak iletim işlevine geri yükler.

```cpp
template <class Type>    // accepts lvalues
    constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
    constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>Parametreler

*Türü*\
Geçirilen değerin türü *Arg*, olabilen türünden farklı *Arg*. Genellikle iletme işlevinin bir şablon bağımsız değişkeni tarafından belirlenir.

*bağımsız değişken*\
Yayınlama için bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

Bir rvalue başvurusu döndürür *Arg* değer iletilmezse *Arg* özgün bir rvalue ise veya bir rvalue başvuru oluştu; Aksi halde döndürür *Arg* türünü değiştirmeden.

### <a name="remarks"></a>Açıklamalar

Çağırmak için bir açık şablon bağımsız değişkeni belirtmeniz gerekir `forward`.

`forward` bağımsız değişkeni ileriye doğru değil. Özgün bir rvalue ise veya rvalue başvurusu ise, bunun yerine, tarafından bağımsız değişkeni olarak bir rvalue başvurusuna koşullu olarak atama `forward` iletilen bağımsız değişkenin özgün türünün bilgisiyle aşırı yük çözümlemesi gerçekleştirmek derleyiciyi etkinleştirir. Bir iletme işlevine bağımsız değişkenin açık türü kendi özgün türünden farklı olabilir — örneğin, ne zaman bir rvalue bir işlev için bağımsız değişken olarak kullanılan ve bir parametre adı için bağlı bir ada sahip olması sağlar ne olursa olsun değer, aslında bir rvalue olarak var olan bir lvalue — `forward` bağımsız değişkenin rvalue durumunu geri yükler.

Aşırı yükleme çözümlemesi için bir bağımsız değişkenin özgün değerinin rvalue durumunu geri yükleme olarak bilinir *kusursuz iletme*. Kusursuz iletme bir şablon işlevinin her iki başvuru türünün bağımsız değişkenini kabul etmesini ve aşırı yük çözümlemeleri yapılması gerektiğinde rvalue durumunu geri yüklemesini sağlar. Kusursuz iletme kullanarak, rvalues için taşıma semantiğini koruyabilir ve bağımsız değişkenlerinin yalnızca başvuru türüne göre çeşitlenen işlevler için aşırı yük sağlanmasını önleyebilirsiniz.

## <a name="from_chars"></a> from_chars

```cpp
from_chars_result from_chars(const char* first, const char* last, see below& value, int base = 10);

from_chars_result from_chars(const char* first, const char* last, float& value, chars_format fmt = chars_format::general); 

from_chars_result from_chars(const char* first, const char* last, double& value, chars_format fmt = chars_format::general); 

from_chars_result from_chars(const char* first, const char* last, long double& value, chars_format fmt = chars_format::general);
```

## <a name="get"></a> Al

Bir öğeyi alır bir `pair` nesne türü veya dizin konumu.

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

*Dizin*\
Seçilen öğenin 0 tabanlı dizini.

*T1*\
İlk çifti öğenin türü.

*T2*\
İkinci çift öğe türü.

*çekme isteği*\
Aralarından seçim yapabileceğiniz çifti.

### <a name="remarks"></a>Açıklamalar

Şablon işlevleri her bir öğenin bir başvuru döndürmeyi kendi `pair` bağımsız değişken.

Dizinli aşırı yüklemeler için değerini *dizin* işlevler döndürür 0 `pr.first` ve değerini *dizin* 1 işlevler döndürür `pr.second`. Türü `RI` döndürülen öğe türü.

Dizin parametresi olmayan aşırı yükler için döndürülecek öğe türü bağımsız değişkeni tarafından çıkarılır. Çağırma `get<T>(Tuple)` , bir derleyici hatasına neden olur *çekme isteği* t türünde bir öğe sayısından fazla veya az içerir

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

## <a name="index_sequence"></a> index_sequence

```cpp
template<size_t... I>
    using index_sequence = integer_sequence<size_t, I...>;
```

## <a name="index_sequence_for"></a> index_sequence_for

```cpp
template<class... T>
    using index_sequence_for = make_index_sequence<sizeof...(T)>;
```

## <a name="make_index_sequence"></a> make_index_sequence

```cpp
template<size_t N>
    using make_index_sequence = make_integer_sequence<size_t, N>;
```

## <a name="make_integer_sequence"></a> make_integer_sequence

```cpp
template<class T, T N>
    using make_integer_sequence = integer_sequence<T, see below >;
```

## <a name="make_pair"></a> make_pair

Türünde nesne oluşturmak için kullanabileceğiniz bir şablon işlevi `pair`, burada bileşen türleri parametre olarak geçirilen veri türlerine dayanan otomatik olarak seçilir.

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

*val1*\
İlk öğesini başlatan değer `pair`.

*Val2*\
İkinci öğesini başlatan değer `pair`.

### <a name="return-value"></a>Dönüş Değeri

Oluşturulan çift nesnesi: `pair` < `T`,`U`> (`Val1`, `Val2`).

### <a name="remarks"></a>Açıklamalar

`make_pair` türü nesneyi [reference_wrapper sınıfı](../standard-library/reference-wrapper-class.md) başvuru türleri ve dizileri ve işlevleri işaretçilere küçülen dönüştürür.

Döndürülen `pair` nesnesi `T` şu şekilde belirlenir:

- Giriş türü `T` olduğu `reference_wrapper<X>`, döndürülen türü `T` olduğu `X&`.

- Aksi takdirde, döndürülen tür `T` olduğu `decay<T>::type`. Varsa [decay sınıfı](../standard-library/decay-class.md) desteklenmiyor, döndürülen tür `T` giriş türü ile aynı `T`.

Döndürülen türü `U` türündekine benzer şekilde belirlenir `U`.

Bir avantajı `make_pair` faydası depolanan nesne türlerinin derleyici tarafından otomatik olarak belirlenir ve açıkça belirtilmesi gerekmez. Açık şablon bağımsız değişkenleri gibi kullanmayın `make_pair<int, int>(1, 2)` kullandığınızda `make_pair` ayrıntılı olduğundan ve derleme hatasına neden olabilecek karmaşık rvalue başvuru sorunları ekler. Bu örnek için doğru sözdizimi olacaktır `make_pair(1, 2)`

`make_pair` Yardımcı işlevi ayrıca bir giriş parametresi olarak bir çift gerektiren bir işleve iki değer geçirilecek mümkün kılar.

### <a name="example"></a>Örnek

Yardımcı işlevini kullanma hakkında bir örnek `make_pair` bildirmek ve bir çift başlatmak için bkz: [pair yapısı](../standard-library/pair-structure.md).

## <a name="move"></a> Taşıma

Kendi bağımsız değişkenini koşulsuz olarak bir rvalue başvurusuna yayınlar ve böylece kendi türünün taşınması etkinse, taşınabileceğini belirtir.

```cpp
template <class Type>
    constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>Parametreler

*Türü*\
Geçirilen bağımsız değişkenin türünden çıkarsanan tür *Arg*başvuru daraltma kurallarıyla birlikte.

*bağımsız değişken*\
Yayınlama için bağımsız değişkeni. Ancak türünü *Arg* bir rvalue başvurusu olarak belirtilmesi için görünür `move` lvalue başvuruları rvalue başvurularına bağlanabileceğinden lvalue bağımsız değişkenlerini de kabul eder.

### <a name="return-value"></a>Dönüş Değeri

`Arg` bir rvalue başvurusu olarak olsun veya olmasın, türü bir başvuru türüdür.

### <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişkeni *türü* açıkça belirtilmesi, ancak geçirilen değerin türünden deyimli tasarlanmamıştır *Arg*. Türünü *türü* başvuru daraltma kurallarına göre daha fazla ayarlanır.

`move` bağımsız değişkeni taşınmaz. Bunun yerine, kendi bağımsız değişkeninin koşulsuzca tarafından — bir lvalue olabilen — kopyalama, geçirilen değer yerine isteğe bağlı olarak bir rvalue başvurusunu daha sonra taşımasına olanak sağlayan *Arg* türü taşıma etkinse. Türü taşıma etkin değilse, bunun yerine kopyalanır.

Değer iletilmezse *Arg* bir lvalue değeridir — diğer bir deyişle, bir ada sahip veya kendi adresi alınabiliyorsa — taşıma gerçekleştiğinde geçersiz kılınır. Geçirilen değere bakın yoksa *Arg* adı veya adresi taşındıktan sonra göre.

## <a name="moveif"></a> move_if_noexcept

```cpp
template <class T> constexpr conditional_t< !is_nothrow_move_constructible_v<T> && is_copy_constructible_v<T>, const T&, T&&> move_if_noexcept(T& x) noexcept;
```

## <a name="swap"></a> değiştirme

İki tür öğelerini değiştirir veya [pair yapısı](../standard-library/pair-structure.md) nesneleri.

```cpp
template <class T>
    void swap(T& left, T& right) noexcept(see below );
template <class T, size_t N>
    void swap(T (&left)[N], T (&right)[N]) noexcept(is_nothrow_swappable_v<T>);
template <class T, class U>
    void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü veya tür `pair`.

*sağ*\
Bir nesne türü veya tür `pair`.

### <a name="remarks"></a>Açıklamalar

Bir avantajı `swap` faydası depolanan nesne türlerinin derleyici tarafından otomatik olarak belirlenir ve açıkça belirtilmesi gerekmez. Açık şablon bağımsız değişkenleri gibi kullanmayın `swap<int, int>(1, 2)` kullandığınızda `swap` ayrıntılı olduğundan ve derleme hatasına neden olabilecek karmaşık rvalue başvuru sorunları ekler.

## <a name="to_chars"></a> to_chars

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

Değer aralığı doldurarak bir karakter dizisine dönüştürür `[first, last)`burada `[first, last)` geçerli bir aralıkta olması gerekir.
