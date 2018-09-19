---
title: Şablonları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- template_cpp
dev_langs:
- C++
helpviewer_keywords:
- templates, C++
- templates [C++]
ms.assetid: 90fcc14a-2092-47af-9d2e-dba26d25b872
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 715927893ec07d08ca2f2bd6eefc5f10795d5574
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083645"
---
# <a name="templates-c"></a>Şablonlar (C++)

Genel C++ programlamada temelini şablonlardır. Kesin türü belirtilmiş bir dil C++ açıkça Programcı tarafından bildirilen veya derleyici tarafından atanan belirli bir türün tüm değişkenler gerektirir. Ancak, birçok veri yapısı ve algoritma üzerinde çalıştıkları ne tür ne olursa olsun aynı arayın. Şablonları etkin bir sınıfta veya işlevde işlemlerini tanımlayın ve hangi somut belirtmesine olanak tanır. Bu işlemlerin türleri üzerinde çalışması gerekir.

## <a name="defining-and-using-templates"></a>Tanımlama ve şablonları kullanma

Bir şablon bağımsız değişkenleri için şablon parametreleri kullanıcının sağladığı göre derleme zamanında bir sıradan tür veya işlev oluşturan bir yapıdır. Örneğin, şunun gibi bir işlev şablonu tanımlayabilirsiniz:

```cpp
template <typename T>
T minimum(const T& lhs, const T& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

Yukarıdaki kodu tek tür parametresi olan genel bir işlev için bir şablon tanımlayan *T*, dönüş değeri ve çağırma parametreleri (lhs ve sol) olan tüm bu tür. Bir tür parametresi, gibi ancak tek bir büyük harf kuralı tarafından en sık kullanılan adı verebilirsiniz. *T* şablon parametresi; **typename** anahtar sözcüğü, bu parametre için bir tür için bir yer tutucu olduğunu söyler. İşlev çağrıldığında, derleyici her örneği değiştirecek `T` kullanıcı tarafından belirtilen veya derleyici tarafından atanan somut tür bağımsız değişkeni ile. Derleyici bir sınıf oluşturur veya bir şablondan işlevi olarak adlandırılır işlem *şablonu örneklemesi*; `minimum<int>` şablonu örneklemesi `minimum<T>`.

Bir kullanıcı için tamsayı özelleştirilmiş şablon örneği başka bir yerde bildirebilirsiniz Get_a() ve get_b() int döndüren işlevleri olduğunu varsayar:

```cpp
int a = get_a();
int b = get_b();
int i = minimum<int>(a, b);
```

Ancak, çünkü bu bir işlev şablonu ve derleyici türetme türü `T` bağımsız değişkenler'den *bir* ve *b*, bir normal işlev gibi çağırabilirsiniz:

```cpp
int i = minimum(a, b);
```

Derleyici, son deyim ile karşılaştığında hangi her örneğinin içinde yeni bir işlev oluşturur *T* şablonda ile değiştirilir **int**:

```cpp
int minimum(const int& lhs, const int& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

Derleyicinin tür kesintisi'teki işlev şablonlarının nasıl gerçekleştireceğini kurallarını normal işlevleri için kurallar temel alır. Daha fazla bilgi için [aşırı yükleme çözünürlüğü, işlev şablonu çağrılarının](../cpp/overload-resolution-of-function-template-calls.md).

## <a id="type_parameters"></a> Tür parametreleri

İçinde `minimum` yukarıdaki şablonu Not tür parametresi *T* işlevi çağrısı parametrelerinde, başvuru niteleyicileri ve const nereden eklenir kullanıldığı kadar herhangi bir yolla nitelenmiyor.

Tür parametreleri sayısı için pratik sınır yoktur. Birden çok parametre, virgüllerle ayırın:

```cpp
template <typename T, typename U, typename V> class Foo{};
```

Anahtar sözcüğü **sınıfı** eşdeğerdir **typename** bu bağlamda. Önceki örnek olarak ifade edebilirsiniz:

```cpp
template <class T, class U, class V> class Foo{};
```

Üç nokta işleci (...), rastgele bir sayıdan sıfır veya daha fazla tür parametreleri alan şablon tanımlamak için kullanabilirsiniz:

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
```

Herhangi bir yerleşik veya kullanıcı tanımlı türü bir tür bağımsız değişkeni kullanılabilir. Örneğin, std::vector standart kitaplıkta tamsayıları kayanlara, Double, dizeleri depolamak için kullanabileceğiniz MyClass, const MyClass *, MyClass &. Şablonları kullanarak bir tür bağımsız değişkeni tür parametreleri için uygulanan tüm işlemler desteklemelidir olduğunda birincil kısıtlama. Örneğin, en düşük dediğimiz Bu örnekte olduğu gibi MyClass kullanarak:

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

MyClass aşırı için sağlamaz çünkü bir derleyici hatası oluşturulan < işleci.

Bir tür bir kısıtlama uygulayan bir şablon tanımlayabilirsiniz tüm herhangi belirli şablon türü bağımsız değişkenleri aynı nesne hiyerarşilerine ait olduğunu devralınan gereksinimi yoktur. Nesne yönelimli teknikleri şablonları ile birleştirebilirsiniz. Örneğin, türetilmiş * vektör içinde depolayabileceğiniz\<temel\*>.    İşaretçiler bağımsız olması gerektiğini unutmayın

```cpp
vector<MyClass*> vec;
   MyDerived d(3, L"back again", time(0));
   vec.push_back(&d);

   // or more realistically:
   vector<shared_ptr<MyClass>> vec2;
   vec2.push_back(make_shared<MyDerived>());
```

Vektör ve diğer standart kitaplığı kapsayıcıları öğeleri üzerinde büyük oranda yansıtmaktadır temel gereksinimleri `T` olan `T` kopyalama atanabilir ve kopyalama atmamalıdır.

## <a name="non-type-parameters"></a>Türü olmayan parametreleri

C# ve Java gibi diğer dillerdeki genel türlerinin aksine, değer parametreleri olarak da bilinir, tür olmayan parametreler C++ şablonları destekler. Örneğin, standart kitaplık std::array sınıfında benzer Bu örnek olarak bir dizi uzunluğunu belirtmek için sabit bir tamsayı değeri sağlayabilirsiniz:

```cpp
template<typename T, size_t L>
class MyArray
{
    T arr[L];
public:
    MyArray() { ... }
};
```

Sözdizimi şablon bildirimindeki unutmayın. Size_t değeri olarak derleme zamanında bir şablon bağımsız değişkeni geçirilir ve sabit veya bir constexpr ifadesi olmalıdır. Bunu şu şekilde kullanabilirsiniz:

```cpp
MyArray<MyClass*, 10> arr;
```

İşaretçileri ve başvuruları dahil olmak üzere değerlerine diğer türleri, tür olmayan parametreler geçirilebilir. Örneğin, bir işaretçi bir işlev veya başka bir işlem şablonu kod içinde özelleştirmek için işlev nesnesi geçirebilirsiniz.

## <a id="template_parameters"></a> Şablon parametreleri olarak şablonlar

Şablon Şablon parametresi olabilir. Bu örnekte, iki şablon parametreleri MyClass2 vardır: bir typename parametre *T* ve şablon parametresi *Arr*:

```cpp
template<typename T, template<typename U, int I> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
    U u; //Error. U not in scope
};
```

Çünkü *Arr* kendisini parametresinin hiçbir gövdesi, gerekli olmadığında, parametre adları. Aslında, başvurmak için hatadır *Arr*'s typename ya da sınıf parametre adlarından gövdesi içinde `MyClass2`. Bu nedenle, *Arr*ın tür parametresi adlarına atlanabilir, bu örnekte gösterildiği gibi:

```cpp
template<typename T, template<typename, int> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
};
```

## <a name="default-template-arguments"></a>Varsayılan şablon bağımsız değişkenleri

Sınıf ve işlev şablonları varsayılan bağımsız değişkenleri olabilir. Bir şablon bırakabilirsiniz varsayılan bağımsız değişken olduğunda kullandığınız zaman belirtilmemiş. Örneğin, std::vector şablonu, ayırıcı için varsayılan bir bağımsız değişkene sahiptir:

```cpp
template <class T, class Allocator = allocator<T>> class vector;
```

Çoğu durumda varsayılan std::allocator sınıfı kabul edilebilir, böyle bir vektör kullanmak için:

```cpp
vector<int> myInts;
```

Ancak gereken özel bir ayırıcı belirtebilirsiniz, benzer:

```cpp
vector<int, MyAllocator> ints;
```

Birden fazla şablon bağımsız değişkenleri için varsayılan bağımsız değişkenler ilk varsayılan bağımsız değişken sonra tüm bağımsız değişkenler olmalıdır.

Tüm varsayılan parametreleri bir şablonu kullanarak boş açılı ayraçlar kullanarak:

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

Bazı durumlarda, veya istenmediğinde herhangi bir tür ile aynı kodunu tanımlamak bir şablon değildir. Örneğin, yalnızca tür bağımsız değişkeni bir işaretçi ya da bir std::wstring ya da belirli bir temel sınıftan türetilmiş bir tür yürütülecek bir kod yolu tanımlamak isteyebilirsiniz.  Bu gibi durumlarda, tanımladığınız bir *özelleştirmesi* , belirli bir tür için şablonun. Bir kullanıcı bu türüyle şablonu başlattığında, sınıfı oluşturmak için uzmanlık derleyici kullanır ve diğer tüm türleri için derleyici daha genel şablon seçer. Tüm parametreler özelleştirilmiş uzmanlıkları olan *tamamlamak uzmanlıkları*. Yalnızca bazı parametreler özelleştirilmiş adlı bir *kısmi özelleştirmede*.

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

Her özel tür parametresi benzersiz olduğu sürece, bir şablon uzmanlıkları herhangi bir sayıda olabilir. Sınıf şablonlarının kısmi özelleştirilmiş. Bir şablonu tam ve kısmi uzmanlıklar, özgün şablon olarak aynı ad alanında bildirilmelidir.

Daha fazla bilgi için [şablon uzmanlığı](../cpp/template-specialization-cpp.md).