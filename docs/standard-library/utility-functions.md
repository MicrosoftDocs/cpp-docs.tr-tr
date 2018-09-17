---
title: '&lt;yardımcı programı&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: 12e8b2c4dfb0d7d36974fb2e5979d82b69c89316
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718348"
---
# <a name="ltutilitygt-functions"></a>&lt;yardımcı programı&gt; işlevleri

||||
|-|-|-|
|[exchange](#exchange)|[İleriye doğru](#forward)|[get işlevi &lt;yardımcı programı&gt;](#get)|
|[make_pair](#make_pair)|[Taşıma](#move)|[değiştirme](#swap)|

## <a name="exchange"></a>  Exchange

**(C ++ 14)**  Bir nesneye yeni bir değer atar ve eski değeri döndürür.

```cpp
template <class T, class Other = T>
T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
New_val değeri alacak nesne.

*new_val*<br/>
Nesne değeri kopyalanamaz ya da val taşındı.

### <a name="remarks"></a>Açıklamalar

Karmaşık türler için `exchange` taşıma oluşturucusu yok, geçici bir nesne veya taşınır ve her türlü kullanılabilir dönüştürme atama işlecinden kullanarak yeni değer kabul eder, yeni değeri kopyalamaktan kaçınır olduğunda eski değeri kopyalamaktan kaçınır. Exchange işlevi farklıdır [std::swap](../standard-library/algorithm-functions.md#swap) sol bağımsız değişkeni değil taşınmış veya sağ bağımsız değişkeni için kopyalanır.

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

## <a name="forward"></a>  İleriye doğru

Bağımsız değişken bir rvalue'da veya rvalue başvurusundaysa, bağımsız değişkenini bir rvalue başvurusuna koşullu olarak yayınlar. Bu, bir bağımsız değişkenin rvalue olma durumunu mükemmel iletim desteği sunarak iletim işlevine geri yükler.

```cpp
template <class Type>    // accepts lvalues
constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Türü*|Geçirilen değerin türü *Arg*, olabilen türünden farklı *Arg*. Genellikle iletme işlevinin bir şablon bağımsız değişkeni tarafından belirlenir.|
|*bağımsız değişken*|Yayınlama için bağımsız değişkeni.|

### <a name="return-value"></a>Dönüş Değeri

Bir rvalue başvurusu döndürür *Arg* değer iletilmezse *Arg* özgün bir rvalue ise veya bir rvalue başvuru oluştu; Aksi halde döndürür *Arg* türünü değiştirmeden.

### <a name="remarks"></a>Açıklamalar

Çağırmak için bir açık şablon bağımsız değişkeni belirtmeniz gerekir `forward`.

`forward` kendi bağımsız değişkeninin iletmez. Özgün bir rvalue ise veya rvalue başvurusu ise, bunun yerine, tarafından bağımsız değişkeni olarak bir rvalue başvurusuna koşullu olarak atama `forward` iletilen bağımsız değişkenin özgün türünün bilgisiyle aşırı yük çözümlemesi gerçekleştirmek derleyiciyi etkinleştirir. Bir iletme işlevine bağımsız değişkenin açık türü kendi özgün türünden farklı olabilir — örneğin, ne zaman bir rvalue bir işlev için bağımsız değişken olarak kullanılan ve bir parametre adı için bağlı bir ada sahip olması sağlar değeri gerçekten bir rvalue var olup bağımsız olarak, bir lvalue — `forward` bağımsız değişkenin rvalue durumunu geri yükler.

Aşırı yük çözümlemesi gerçekleştirmek için bir bağımsız değişkenin özgün değerinin rvalue durumunu geri yükleme olarak bilinir *kusursuz iletme*. Kusursuz iletme bir şablon işlevinin her iki başvuru türünün bağımsız değişkenini kabul etmesini ve aşırı yük çözümlemeleri yapılması gerektiğinde rvalue durumunu geri yüklemesini sağlar. Kusursuz iletme kullanarak, rvalues için taşıma semantiğini koruyabilir ve bağımsız değişkenlerinin yalnızca başvuru türüne göre çeşitlenen işlevler için aşırı yük sağlanmasını önleyebilirsiniz.

## <a name="get"></a>  Al

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

*Index*<br/>
Belirtilen öğe 0 tabanlı dizini.

*T1*<br/>
İlk çifti öğenin türü.

*T2*<br/>
İkinci çift öğe türü.

*çekme isteği*<br/>
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

    /*
    Output:
    9 3.14
    1 0.27
    */

}
```

## <a name="make_pair"></a>  make_pair

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

*val1*<br/>
İlk öğesini başlatan değer `pair`.

*Val2*<br/>
İkinci öğesini başlatan değer `pair`.

### <a name="return-value"></a>Dönüş Değeri

Oluşturulan çift nesnesi: `pair` <  `T`, `U`> ( `Val1`, `Val2`).

### <a name="remarks"></a>Açıklamalar

`make_pair` türü nesneyi [reference_wrapper sınıfı](../standard-library/reference-wrapper-class.md) başvuru türleri ve dizileri ve işlevleri işaretçilere küçülen dönüştürür.

Döndürülen `pair` nesnesi `T` şu şekilde belirlenir:

- Giriş türü `T` olduğu `reference_wrapper<X>`, döndürülen türü `T` olduğu `X&`.

- Aksi takdirde, döndürülen tür `T` olduğu `decay<T>::type`. Varsa [decay sınıfı](../standard-library/decay-class.md) desteklenmiyor, döndürülen tür `T` giriş türü ile aynı `T`.

Döndürülen türü `U` türündekine benzer şekilde belirlenir `U`.

Bir avantajı `make_pair` faydası depolanan nesne türlerinin derleyici tarafından otomatik olarak belirlenir ve açıkça belirtilmesi gerekmez. Açık şablon bağımsız değişkenleri gibi kullanmayın `make_pair<int, int>(1, 2)` kullandığınızda `make_pair` çünkü gereksiz ayrıntılıdır ve derleme hatasına neden olabilecek karmaşık rvalue başvuru sorunları ekler. Bu örnek için doğru sözdizimi olacaktır `make_pair(1, 2)`

`make_pair` Yardımcı işlevi ayrıca bir giriş parametresi olarak bir çift gerektiren bir işleve iki değer geçirilecek mümkün kılar.

### <a name="example"></a>Örnek

Yardımcı işlevini kullanma hakkında bir örnek `make_pair` bildirmek ve bir çift başlatmak için bkz: [pair yapısı](../standard-library/pair-structure.md).

## <a name="move"></a>  Taşıma

Kendi bağımsız değişkenini koşulsuz olarak bir rvalue başvurusuna yayınlar ve böylece kendi türünün taşınması etkinse, taşınabileceğini belirtir.

```cpp
template <class Type>
constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Türü*|Geçirilen bağımsız değişkenin türünden çıkarsanan tür *Arg*başvuru daraltma kurallarıyla birlikte.|
|*bağımsız değişken*|Yayınlama için bağımsız değişkeni. Ancak türünü *Arg* bir rvalue başvurusu olarak belirtilmesi için görünür `move` lvalue başvuruları rvalue başvurularına bağlanabileceğinden lvalue bağımsız değişkenlerini de kabul eder.|

### <a name="return-value"></a>Dönüş Değeri

`Arg` bir rvalue başvurusu olarak olsun veya olmasın, türü bir başvuru türüdür.

### <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişkeni *türü* açıkça belirtilmesi, ancak geçirilen değerin türünden deyimli hedeflenmemiştir *Arg*. Türünü *türü* başvuru daraltma kurallarına göre daha fazla ayarlanır.

`move` bağımsız değişkenini taşımaz. Bunun yerine, kendi bağımsız değişkeninin koşulsuzca tarafından — bir lvalue olabilen — kopyalama, geçirilen değer yerine isteğe bağlı olarak bir rvalue başvurusunu daha sonra taşımasına olanak sağlayan *Arg* türü taşıma etkinse. Türü taşıma etkin değilse, bunun yerine kopyalanır.

Değer iletilmezse *Arg* bir lvalue değeridir — diğer bir deyişle, bir ada sahip veya kendi adresi alınabiliyorsa — taşıma gerçekleştiğinde geçersiz kılınır. Geçirilen değere başvurmayın *Arg* adı veya adresi taşındıktan sonra göre.

## <a name="swap"></a>  değiştirme

İki öğeleri birbiriyle değiştirir [pair yapısı](../standard-library/pair-structure.md) nesneleri.

```cpp
template <class T, class U>
void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sol*|Bir nesne türü `pair`.|
|*sağ*|Bir nesne türü `pair`.|

### <a name="remarks"></a>Açıklamalar

Bir avantajı `swap` faydası depolanan nesne türlerinin derleyici tarafından otomatik olarak belirlenir ve açıkça belirtilmesi gerekmez. Açık şablon bağımsız değişkenleri gibi kullanmayın `swap<int, int>(1, 2)` kullandığınızda `swap` çünkü gereksiz ayrıntılıdır ve derleme hatasına neden olabilecek karmaşık rvalue başvuru sorunları ekler.

## <a name="see-also"></a>Ayrıca bkz.

[\<yardımcı programı >](../standard-library/utility.md)<br/>
