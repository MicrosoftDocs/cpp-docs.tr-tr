---
title: Şablonlar (C++)
ms.date: 12/27/2019
f1_keywords:
- template_cpp
helpviewer_keywords:
- templates, C++
- templates [C++]
ms.assetid: 90fcc14a-2092-47af-9d2e-dba26d25b872
ms.openlocfilehash: 996458417b20533db074ce2fa13c06860c54247c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223570"
---
# <a name="templates-c"></a>Şablonlar (C++)

Şablonlar, C++ ' ta genel programlama için temeldir. C++ türü kesin belirlenmiş bir dil olarak tüm değişkenlerin, programcı tarafından açıkça veya derleyici tarafından çıkarılan belirli bir türe sahip olmasını gerektirir. Bununla birlikte, birçok veri yapısı ve algoritması, hangi tür üzerinde çalıştıkları ile aynı şekilde görünür. Şablonlar bir sınıfın veya işlevin işlemlerini tanımlamanızı sağlar ve kullanıcının bu işlemlerin hangi somut türleri üzerinde çalışması gerektiğini belirtmesini sağlayabilirsiniz.

## <a name="defining-and-using-templates"></a>Şablonları tanımlama ve kullanma

Şablon, Kullanıcı tarafından şablon parametreleri için sağladığı bağımsız değişkenlere göre derleme zamanında sıradan bir tür veya işlev üreten bir yapıdır. Örneğin, şöyle bir işlev şablonu tanımlayabilirsiniz:

```cpp
template <typename T>
T minimum(const T& lhs, const T& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

Yukarıdaki kod, dönüş değeri ve çağrı parametreleri (lhs ve RHS) bu türün tümü olan tek tür parametresi *T*olan genel bir işlev için bir şablon tanımlar. Bir tür parametresini dilediğiniz şekilde adlandırın, ancak kurala göre tek büyük harfler en yaygın olarak kullanılır. *T* bir şablon parametresidir; **`typename`** anahtar sözcüğü, bu parametrenin bir tür için yer tutucu olduğunu söyler. İşlev çağrıldığında, derleyici her örneğinin, `T` Kullanıcı tarafından belirtilen veya derleyici tarafından belirtilen somut tür bağımsız değişkeniyle değiştirilir. Derleyicinin bir sınıf veya işlev oluşturduğu işlem *şablon örneği oluşturma*olarak adlandırılır; , `minimum<int>` şablonun bir örneklemedir `minimum<T>` .

Başka bir yerde, bir Kullanıcı, int için özelleştirilmiş bir şablon örneği bildirebilir. get_a () ve get_b () 'nin bir int döndüren işlevler olduğunu varsayalım:

```cpp
int a = get_a();
int b = get_b();
int i = minimum<int>(a, b);
```

Ancak, bu bir işlev şablonu olduğundan ve derleyici `T` a ve *b*bağımsız değişkenlerinden *bir* türünü algıladığında, bunu sıradan bir işlev gibi çağırabilirsiniz:

```cpp
int i = minimum(a, b);
```

Derleyici bu son deyimle karşılaştığında, şablonda her *T* oluşumunun değiştirildiği yeni bir işlev oluşturur **`int`** :

```cpp
int minimum(const int& lhs, const int& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

Derleyici, işlev şablonlarında tür kesintilerini nasıl gerçekleştirdiğine ilişkin kurallar, normal işlevlerin kurallarını temel alır. Daha fazla bilgi için bkz. [Işlev şablonu çağrılarının aşırı yükleme çözünürlüğü](../cpp/overload-resolution-of-function-template-calls.md).

## <a name="type-parameters"></a><a id="type_parameters"></a>Tür parametreleri

`minimum`Yukarıdaki şablonda, tür parametresi *T* , const ve başvuru niteleyicilerinin eklendiği işlev çağrısı parametrelerinde kullanılana kadar hiçbir şekilde nitelenmediğini unutmayın.

Tür parametrelerinin sayısında pratik bir sınır yoktur. Birden çok parametreyi virgülle ayırın:

```cpp
template <typename T, typename U, typename V> class Foo{};
```

Anahtar sözcüğü, **`class`** **`typename`** Bu bağlamda ile eşdeğerdir. Önceki örneği şu şekilde ifade edebilirsiniz:

```cpp
template <class T, class U, class V> class Foo{};
```

Rastgele sayıda sıfır veya daha fazla tür parametresi alan bir şablon tanımlamak için üç nokta işlecini (...) kullanabilirsiniz:

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
```

Herhangi bir yerleşik veya Kullanıcı tanımlı tür, tür bağımsız değişkeni olarak kullanılabilir. Örneğin, standart kitaplıkta [std:: vector](../standard-library/vector-class.md) türünü **`int`** ,, **`double`** [std:: String](../standard-library/basic-string-class.md), `MyClass` , **`const`** `MyClass` *, `MyClass&` ve benzeri değişkenleri depolamak için kullanabilirsiniz. Şablonları kullanırken birincil kısıtlama, tür bağımsız değişkeninin tür parametrelerine uygulanan tüm işlemleri desteklemesi gerekir. Örneğin, `minimum` `MyClass` Bu örnekte olduğu gibi öğesini çağırdık:

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

Bir derleyici hatası oluşturulacak, çünkü `MyClass` işleç için aşırı yükleme sağlamıyor **<** .

Belirli bir şablon için tür bağımsız değişkenlerinin hepsi aynı nesne hiyerarşisine ait olduğundan, bu tür bir kısıtlamayı zorlayan bir şablon tanımlayabilirsiniz. Nesne odaklı teknikleri şablonlarla birleştirebilirsiniz; Örneğin, bir vektör içinde türetilmiş bir * saklayabilirsiniz \<Base\*> .    Bağımsız değişkenlerin işaretçiler olması gerektiğini unutmayın

```cpp
vector<MyClass*> vec;
   MyDerived d(3, L"back again", time(0));
   vec.push_back(&d);

   // or more realistically:
   vector<shared_ptr<MyClass>> vec2;
   vec2.push_back(make_shared<MyDerived>());
```

`std::vector`Ve diğer standart kitaplık kapsayıcılarının öğeleri üzerinde yerine getirme temel gereksinimler, `T` `T` kopya atanabilir ve kopya oluşturulabilir.

## <a name="non-type-parameters"></a>Tür olmayan parametreler

C# ve Java gibi diğer dillerdeki genel türlerin aksine, C++ şablonları değer parametreleri olarak da adlandırılan *tür olmayan parametreleri*destekler. Örneğin, standart kitaplıktaki [std:: Array](../standard-library/array-class-stl.md) sınıfına benzer şekilde, bu örnekte olduğu gibi, bir dizinin uzunluğunu belirtmek için sabit bir integral değeri sağlayabilirsiniz:

```cpp
template<typename T, size_t L>
class MyArray
{
    T arr[L];
public:
    MyArray() { ... }
};
```

Şablon bildiriminde söz dizimini aklınızda edin. `size_t`Değer, derleme zamanında bir şablon bağımsız değişkeni olarak geçirilir ve **`const`** ya da bir **`constexpr`** ifadesi olmalıdır. Bunu şöyle kullanın:

```cpp
MyArray<MyClass*, 10> arr;
```

İşaretçiler ve başvurular dahil diğer değer türleri, tür olmayan parametreler olarak geçirilebilir. Örneğin, şablon kodu içindeki bazı işlemleri özelleştirmek için bir işlev veya işlev nesnesine bir işaretçi geçirebilirsiniz.

### <a name="type-deduction-for-non-type-template-parameters"></a>Tür olmayan şablon parametreleri için tür kesintisi

Visual Studio 2017 ve üzeri sürümlerde, **/std: c++ 17** modunda, derleyici, ile belirtilen tür olmayan bir şablon bağımsız değişkeninin türünü kesintiler **`auto`** :

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

## <a name="templates-as-template-parameters"></a><a id="template_parameters"></a>Şablon parametreleri olarak şablonlar

Şablon bir şablon parametresi olabilir. Bu örnekte, MyClass2 iki şablon parametresine sahiptir: bir typeName parametresi *T* ve bir şablon parametresi *ARR*:

```cpp
template<typename T, template<typename U, int I> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
    U u; //Error. U not in scope
};
```

*ARR* parametresinin gövdesi olmadığından, parametre adları gerekli değildir. Aslında, ' ın gövdesinden, *ARR*'nin TypeName veya sınıf parametresi adlarına başvurabileceği bir hatadır `MyClass2` . Bu nedenle, aşağıdaki örnekte gösterildiği gibi *ARR*'nin tür parametresi adları atlanabilir:

```cpp
template<typename T, template<typename, int> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
};
```

## <a name="default-template-arguments"></a>Varsayılan şablon bağımsız değişkenleri

Sınıf ve işlev şablonlarının varsayılan bağımsız değişkenleri olabilir. Bir şablonun varsayılan bir bağımsız değişkeni olduğunda, onu kullandığınızda belirtilmemiş olarak bırakabilirsiniz. Örneğin, std:: vector şablonunun ayırıcı için varsayılan bir bağımsız değişkeni vardır:

```cpp
template <class T, class Allocator = allocator<T>> class vector;
```

Çoğu durumda varsayılan std:: ayırıcı sınıfı kabul edilebilir, bu nedenle şöyle bir vektör kullanırsınız:

```cpp
vector<int> myInts;
```

Ancak gerekirse şöyle bir özel ayırıcı belirtebilirsiniz:

```cpp
vector<int, MyAllocator> ints;
```

Birden çok şablon bağımsız değişkeni için, ilk varsayılan bağımsız değişkenden sonraki tüm bağımsız değişkenlerin varsayılan bağımsız değişkenleri olmalıdır.

Parametreleri varsayılan olarak ayarlanmış bir şablon kullanırken, boş açılı ayraçlar kullanın:

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

Bazı durumlarda, bir şablon için herhangi bir tür için tam olarak aynı kodu tanımlamak mümkün değildir veya istenmez. Örneğin, yalnızca tür bağımsız değişkeni bir işaretçi veya std:: wstring ya da belirli bir temel sınıftan türetilmiş bir tür ise yürütülecek bir kod yolu tanımlamak isteyebilirsiniz.  Bu gibi durumlarda, söz konusu tür için şablonun bir *özelleştirmesi* tanımlayabilirsiniz. Bir Kullanıcı şablonu bu türle birlikte örnekleyen derleyici, sınıfı oluşturmak için özelleştirmeyi kullanır ve diğer tüm türler için, derleyici daha genel şablonu seçer. Tüm parametrelerin özelleşmiş olduğu uzmanlık, tüm *uzmanlardır*. Parametrelerin yalnızca bir kısmı özelleştirilmiştir, bu, *kısmi özelleşme*olarak adlandırılır.

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

Her bir özelleştirilmiş tür parametresi benzersiz olduğu sürece bir şablonda herhangi bir sayıda özelleştirilmiş öğe olabilir. Yalnızca sınıf şablonları kısmen özelleştirilmiş olabilir. Bir şablonun tüm tamamen ve kısmi uzmanlık alanı, özgün şablonla aynı ad alanında bildirilmelidir.

Daha fazla bilgi için bkz. [şablon özelleştirmesi](../cpp/template-specialization-cpp.md).
