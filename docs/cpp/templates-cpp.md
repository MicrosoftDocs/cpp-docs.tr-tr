---
title: Şablonlar (C++)
ms.date: 12/27/2019
f1_keywords:
- template_cpp
helpviewer_keywords:
- templates, C++
- templates [C++]
ms.assetid: 90fcc14a-2092-47af-9d2e-dba26d25b872
ms.openlocfilehash: e47f00c7e387974c7d1756cf3ee3865f892e6951
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032349"
---
# <a name="templates-c"></a>Şablonlar (C++)

Şablonlar C++'daki genel programlamanın temelidir. Güçlü bir şekilde yazılan bir dil olarak C++, tüm değişkenlerin programcı tarafından açıkça beyan edilen veya derleyici tarafından çıkarılan belirli bir türe sahip olmasını gerektirir. Ancak, birçok veri yapıları ve algoritmalar ne tür onlar üzerinde faaliyet olursa olsun aynı görünür. Şablonlar, bir sınıfın veya işlevin işlemlerini tanımlamanızı sağlar ve kullanıcının bu işlemlerin hangi somut türlerüzerinde çalışması gerektiğini belirtmesini sağlar.

## <a name="defining-and-using-templates"></a>Şablonları tanımlama ve kullanma

Şablon, şablon parametreleri için kullanıcı nın sağladığı bağımsız değişkenlere dayalı olarak derleme zamanında sıradan bir tür veya işlev oluşturan bir yapıdır. Örneğin, şu gibi bir işlev şablonu tanımlayabilirsiniz:

```cpp
template <typename T>
T minimum(const T& lhs, const T& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

Yukarıdaki kod, iade değeri ve çağrı parametreleri (lhs ve rhs) tümü bu türolan tek bir tür parametre *T*olan genel bir işlev için bir şablon açıklar. İstediğiniz bir tür parametresini adlandırabilirsiniz, ancak kural olarak tek büyük harf en sık kullanılır. *T* bir şablon parametresi; **tür adı** anahtar kelimesi, bu parametrenin bir tür için yer tutucu olduğunu söyler. İşlev çağrıldığında, derleyici kullanıcı tarafından `T` belirtilen veya derleyici tarafından çıkarılan somut tür bağımsız değişkeninin her örneğini değiştirir. Derleyicinin bir şablondan bir sınıf veya işlev oluşturduğu işleme *şablon anlık olarak*adlandırılır; `minimum<int>` şablonun `minimum<T>`bir anlık olduğunu.

Başka bir yerde, kullanıcı int için özelleştirilmiş şablonun bir örneğini bildirebilir. get_a() ve get_b() int döndüren işlevler olduğunu varsayalım:

```cpp
int a = get_a();
int b = get_b();
int i = minimum<int>(a, b);
```

Ancak, bu bir işlev şablonu olduğundan ve derleyici `T` *a* ve *b*bağımsız değişkenlerinin türünü çıkarabildiği için, bunu sıradan bir işlev gibi çağırabilirsiniz:

```cpp
int i = minimum(a, b);
```

Derleyici bu son deyimle karşılaştığında, şablondaki *her T* oluşumunun **int**ile değiştirildiği yeni bir işlev oluşturur:

```cpp
int minimum(const int& lhs, const int& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

Derleyicinin işlev şablonlarında tür çıkarımını nasıl gerçekleştirdiğine ilişkin kurallar, sıradan işlevler için kurallara dayanır. Daha fazla bilgi için bkz: [İşlev Şablonu Çağrılarının Aşırı Yük Çözünürlüğü.](../cpp/overload-resolution-of-function-template-calls.md)

## <a name="type-parameters"></a><a id="type_parameters"></a>Tip parametreleri

Yukarıdaki `minimum` şablonda, const ve başvuru niteleyicilerinin eklendiği işlev çağrı parametrelerinde kullanılana kadar *T* türü parametresi hiçbir şekilde nitelikli değildir.

Tür parametreleri sayısı için pratik bir sınır yoktur. Birden çok parametreyi virgüle göre ayırın:

```cpp
template <typename T, typename U, typename V> class Foo{};
```

Anahtar kelime **sınıfı** bu bağlamda **tür adı** eşdeğerdir. Önceki örneği şu şekilde ifade edebilirsiniz:

```cpp
template <class T, class U, class V> class Foo{};
```

Rasgele sıfır veya daha fazla tür parametresi alan bir şablon tanımlamak için elips isi işleci (...) kullanabilirsiniz:

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
```

Yerleşik veya kullanıcı tanımlı herhangi bir tür tür bağımsız değişkeni olarak kullanılabilir. Örneğin, standart kitaplıktaki [std::vektörü](../standard-library/vector-class.md) kullanarak **int**, **double**, [std::string](../standard-library/basic-string-class.md) `MyClass`, **const** `MyClass`*, `MyClass&`, , ve benzeri değişkenleri depolayabilirsiniz. Şablonları kullanırken birincil kısıtlama, tür bağımsız değişkeninin tür parametrelerine uygulanan tüm işlemleri desteklemesi gerektiğidir. Örneğin, bu örnekte `MyClass` olduğu gibi kullanma diyoruz: `minimum`

```cpp
class MyClass
{
public:
    int num;
    std::wstring description;
};

int main()
{
    MyClass mc1 {1, L"hello"};
    MyClass mc2 {2, L"goodbye"};
    auto result = minimum(mc1, mc2); // Error! C2678
}
```

Operatör için aşırı yük `MyClass` sağlamadığından derleyici hatası oluşturulur. **<**

Belirli bir şablonun tür bağımsız değişkenlerinin tümü aynı nesne hiyerarşisine ait olmakla birlikte, böyle bir kısıtlamayı zorlayan bir şablon tanımlayabilirsiniz. Nesne yönelimli teknikleri şablonlarla birleştirebilirsiniz; örneğin, türetilmiş*> vektör\<Baz'da\* depolayabilirsiniz.    Bağımsız değişkenlerin işaretçi olması gerektiğini unutmayın

```cpp
vector<MyClass*> vec;
   MyDerived d(3, L"back again", time(0));
   vec.push_back(&d);

   // or more realistically:
   vector<shared_ptr<MyClass>> vec2;
   vec2.push_back(make_shared<MyDerived>());
```

Temel gereksinimleri `std::vector` ve diğer standart kitaplık `T` kapsayıcıları `T` öğeleri empoze kopyalanabilir ve kopyalanabilir olmasıdır.

## <a name="non-type-parameters"></a>Tür dışı parametreler

C# ve Java gibi diğer dillerdeki genel türlerin aksine, C++ şablonları değer parametreleri olarak da adlandırılan *tür dışı parametreleri*destekler. Örneğin, Standart Kitaplıktaki [std::dizi](../standard-library/array-class-stl.md) sınıfına benzer bu örnekte olduğu gibi, bir dizinin uzunluğunu belirtmek için sabit bir integral değeri sağlayabilirsiniz:

```cpp
template<typename T, size_t L>
class MyArray
{
    T arr[L];
public:
    MyArray() { ... }
};
```

Şablon bildirimindeki sözdizimine dikkat edin. Değer `size_t` derleme zamanında şablon bağımsız değişkeni olarak geçirilir ve **const** veya **constexpr** ifadesi olmalıdır. Şöyle kullanıyorsun:

```cpp
MyArray<MyClass*, 10> arr;
```

İşaretçiler ve başvurular da dahil olmak üzere diğer değer türleri tür dışı parametreler olarak geçirilebilir. Örneğin, şablon kodu içinde bazı işlemleri özelleştirmek için bir işaretçiyi bir işlev veya işlev nesnesine geçirebilirsiniz.

### <a name="type-deduction-for-non-type-template-parameters"></a>Tür dışı şablon parametreleri için tür çıkarımı

Visual Studio 2017 ve sonraki durumlarda, **/std:c++17** modunda derleyici **otomatik**olarak bildirilen tür olmayan şablon bağımsız değişkeninin türünü algılar:

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

## <a name="templates-as-template-parameters"></a><a id="template_parameters"></a>Şablon parametreleri olarak şablonlar

Şablon bir şablon parametresi olabilir. Bu örnekte, MyClass2'nin iki şablon parametresi vardır: bir yazı adı parametresi *T* ve şablon parametresi *Arr:*

```cpp
template<typename T, template<typename U, int I> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
    U u; //Error. U not in scope
};
```

*Arr* parametresinin gövdesi olmadığından, parametre adları gerekmez. Aslında, *Arr*'ın yazı adı veya sınıf parametre adlarını gövdesi nden `MyClass2`başvurmak bir hatadır. Bu nedenle, *Arr'ın*tür parametre adları, bu örnekte gösterildiği gibi atlanabilir:

```cpp
template<typename T, template<typename, int> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
};
```

## <a name="default-template-arguments"></a>Varsayılan şablon bağımsız değişkenleri

Sınıf ve işlev şablonlarında varsayılan bağımsız değişkenler olabilir. Bir şablonvarsayılan bağımsız değişkene sahipse, şablonu kullandığınızda belirsiz bırakabilirsiniz. Örneğin, std::vektör şablonu ayırıcı için varsayılan bir bağımsız değişkene sahiptir:

```cpp
template <class T, class Allocator = allocator<T>> class vector;
```

Çoğu durumda varsayılan std::allocator sınıfı kabul edilebilir, bu nedenle aşağıdaki gibi bir vektör kullanın:

```cpp
vector<int> myInts;
```

Ancak gerekirse, aşağıdaki gibi özel bir ayırıcı belirtebilirsiniz:

```cpp
vector<int, MyAllocator> ints;
```

Birden çok şablon bağımsız değişkeni için, ilk varsayılan bağımsız değişkenden sonraki tüm bağımsız değişkenlerin varsayılan bağımsız değişkenleri olması gerekir.

Parametreleri varsayılan bir şablon kullanırken, boş açı braketleri kullanın:

```cpp
template<typename A = int, typename B = double>
class Bar
{
    //...
};
...
int main()
{
    Bar<> bar; // use all default type arguments
}
```

## <a name="template-specialization"></a>Şablon uzmanlığı

Bazı durumlarda, bir şablonun herhangi bir tür için tam olarak aynı kodu tanımlaması mümkün veya istenmez. Örneğin, yalnızca tür bağımsız değişkeni bir işaretçi veya std::wstring veya belirli bir taban sınıftan türetilen bir türse yürütülecek bir kod yolu tanımlamak isteyebilirsiniz.  Bu gibi durumlarda, söz konusu tür için şablonun *bir uzmanlık* tanımlayabilirsiniz. Bir kullanıcı şablonu bu türde instantiates olduğunda, derleyici sınıfı oluşturmak için uzmanlık kullanır ve diğer tüm türler için derleyici daha genel şablonu seçer. Tüm parametrelerin özelleştirildiği uzmanlıklar *tam uzmanlıklardır.* Parametrelerden yalnızca bazıları özelleştirilmişse, *buna kısmi uzmanlık*denir.

```cpp
template <typename K, typename V>
class MyMap{/*...*/};

// partial specialization for string keys
template<typename V>
class MyMap<string, V> {/*...*/};
...
MyMap<int, MyClass> classes; // uses original template
MyMap<string, MyClass> classes2; // uses the partial specialization
```

Her özel leştirilmiş tür parametresi benzersiz olduğu sürece şablonun herhangi bir sayıda uzmanlık alanı olabilir. Yalnızca sınıf şablonları kısmen özelleştirilmiş olabilir. Bir şablonun tüm tam ve kısmi uzmanlıkları özgün şablonla aynı ad alanında bildirilmelidir.

Daha fazla bilgi için [Şablon Uzmanlığı'na](../cpp/template-specialization-cpp.md)bakın.
