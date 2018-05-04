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
ms.openlocfilehash: f5aa532246054ff0a0b67b9560e40ae704a40fc8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="templates-c"></a>Şablonlar (C++)
C++'ta genel programlama için temel şablonlarıdır. Kesin türü belirtilmiş bir dil C++ açıkça Programcı tarafından bildirilen ya da derleyici tarafından anlaşılan belirli bir türün tüm değişkenler gerektirir. Ancak, çok sayıda veri yapılarını ve algoritmaları üzerinde işletim ne tür aynı arayın. Şablonları etkinleştirme, bir sınıf ya da işlevin operations tanımlamak ve kullanıcının hangi somut belirtmesine izin vermek için bu işlemler türleri üzerinde çalışması gerekir.  
  
## <a name="defining-and-using-templates"></a>Tanımlama ve şablonları kullanma  
 Bir şablon bir sıradan türe veya işleve bağımsız değişkenler için şablon parametreleri kullanıcının sağladığı göre derleme zamanında oluşturan bir yapıdır. Örneğin, bir işlev şablon bu gibi tanımlayabilirsiniz:  
  
```cpp  
template <typename T>  
T minimum(const T& lhs, const T& rhs)  
{  
    return lhs < rhs ? lhs : rhs;  
}  
```  
  
 Yukarıdaki kod tek tür parametresi ile genel bir işlev için bir şablon açıklar `T`, dönüş değeri ve çağrı (lhs ve rhs) parametreleri olan tüm bu tür. Tür parametresi gibi ancak kuralı tek pın'de büyük harf tarafından en sık kullanılan adı verebilirsiniz. `T` bir şablon parametredir; `typename` anahtar sözcüğü bu parametrenin türü için bir yer tutucu olduğunu söyler. İşlevi çağrıldığında, derleyici, her örneği değiştirecek `T` kullanıcı tarafından belirtilen veya derleyici tarafından anlaşılan somut tür bağımsız değişkeni ile. Derleyici bir sınıf oluşturur veya bir şablondan işlevi olarak adlandırılır işlem *şablonu örneklemesi*;   `minimum<int>` bir şablonun oluşturulmadan `minimum<T>`.  
  
 Bir kullanıcı için tamsayı özelleştirilmiş şablon örneği başka bir yerde bildirebilir Get_a() ve get_b() int döndüren işlevler olduğunu varsayın:  
  
```  
int a = get_a();  
int b = get_b();  
int i = minimum<int>(a, b);  
```  
  
 Ancak, bu olduğundan işlev şablonunun ve derleyici türetme türünü `T` bağımsız değişkenleri gelen `a` ve `b`, yalnızca gibi sıradan bir işlev çağrısı:  
  
```cpp  
int i = minimum(a, b);  
```  
  
 Derleyici bu son deyim karşılaştığında her hangi örneğinin içinde yeni bir işlev oluşturur *T* şablonda ile değiştirilir `int`:  
  
```  
  
      int minimum(const int& lhs, const int& rhs)  
{  
    return lhs < rhs ? lhs : rhs;  
}  
```  
  
 Derleyici türü kesintisi'teki işlev şablonlarının nasıl gerçekleştireceğini kuralları sıradan işlevleri için kurallar dayanır. Daha fazla bilgi için bkz: [aşırı yükleme çözümü, işlev şablonu çağrılarının](../cpp/overload-resolution-of-function-template-calls.md).  
  
## <a id="type_parameters"></a> Tür parametreleri  
 İçinde `minimum` şablonu yukarıdaki not tür parametresi `T` const ve başvuru niteleyicileri burada eklenen işlev çağrısı parametreleri kullanılır kadar herhangi bir şekilde yetkili değil.  
  
 Tür parametreleri sayısına pratik sınır yoktur. Birden çok parametre, virgüllerle ayırın:  
  
```cpp  
template <typename T, typename U, typename V> class Foo{};  
  
```  
  
 Anahtar sözcüğü `class` eşdeğerdir `typename` bu bağlamda. Önceki örnek olarak ifade edebilirsiniz:  
  
```  
template <class T, class U, class V> class Foo{};   
```  
  
 Üç nokta işleci (...), rastgele sayıda sıfır veya daha fazla tür parametre isteyen bir şablonu tanımlamak için kullanabilirsiniz:  
  
```cpp  
template<typename... Arguments> class vtclass;  
  
vtclass< > vtinstance1;  
vtclass<int> vtinstance2;  
vtclass<float, bool> vtinstance3;  
```  
  
 Yerleşik veya kullanıcı tanımlı tür, tür bağımsız değişkeni olarak kullanılabilir. Örneğin, std::vector standart kitaplığında ints, Double, dizeleri depolamak için kullanabileceğiniz MyClass, const MyClass *, MyClass &. Tür bağımsız değişkeni tür parametreleri uygulanan herhangi bir işlem desteklemelidir şablonlarını kullanırken birincil kısıtlaması yoktur. Örneğin, en düşük diyoruz MyClass bu örnekteki kullanarak:  
  
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
  
 MyClass için bir aşırı sağlamadığından derleyici hatası oluşturulan < işleci.  
  
 Böyle bir kısıtlama uygulayan bir şablon tanımlayabilirsiniz rağmen tüm herhangi belirli şablon türü bağımsız değişkenleri aynı nesne hiyerarşiye ait devralınan gereksinimi yoktur. Nesne odaklı teknikleri şablonları ile birleştirebilirsiniz. Örneğin, türetilmiş * bir vektör depolayabileceğiniz\<temel\*>.    Bağımsız değişkenler işaretçileri olması gerektiğini unutmayın  
  
```  
vector<MyClass*> vec;  
   MyDerived d(3, L"back again", time(0));  
   vec.push_back(&d);  
  
   // or more realistically:  
   vector<shared_ptr<MyClass>> vec2;  
   vec2.push_back(make_shared<MyDerived>());  
```  
  
 Vektör ve diğer standart kitaplığı kapsayıcılar öğeleri üzerinde zorunlu tuttukları temel gereksinimleri `T` olan `T` kopyalama atanabilir ve kopya oluşturulabilir.  
  
## <a name="non-type-parameters"></a>Olmayan tür parametreleri  
 C# ve Java gibi diğer dillerde genel türlerinin aksine, C++ şablonları değer parametreleri olarak da bilinir türü olmayan parametreleri destekler. Örneğin, standart kitaplığı std::array sınıfında benzer Bu örnek olarak bir dizi uzunluğu, belirtmek için sabit bir tam sayı değer sağlayabilirsiniz:  
  
```  
template<typename T, size_t L>  
class MyArray  
{  
    T arr[L];  
public:  
    MyArray() { ... }  
};  
  
```  
  
 Şablon bildiriminde sözdiziminde unutmayın. Size_t değer şablon bağımsız değişken derleme zamanında geçirilen ve sabit veya constexpr ifadesi olması gerekir. Bunu şu şekilde kullanın:  
  
```cpp  
MyArray<MyClass*, 10> arr;  
```  
  
 Diğer tür işaretçiler ve başvuruları dahil olmak üzere değer türü olmayan parametreler olarak geçirilebilir. Örneğin, bir işlev veya işlev nesnesi başka bir işlem şablonu kodu içinde özelleştirmek için bir işaretçi geçirebilirsiniz.  
  
## <a id="template_parameters"></a> Şablon parametreleri olarak şablonları  
 Bir şablon bir şablon parametresi olabilir. Bu örnekte, iki şablon parametreleri MyClass2 sahiptir: typename parametresi `T` ve şablon parametresi `Arr`:  
  
```cpp  
template<typename T, template<typename U, int I> class Arr>  
class MyClass2  
{  
    T t; //OK  
    Arr<T, 10> a;  
    U u; //Error. U not in scope  
};  
```  
  
 Çünkü `Arr` kendisini parametresine sahip hiçbir gövdesi, kendi parametre adları gerek duyulmaz. Aslında, başvurmak için bir hata olduğunu `Arr`'s typename veya sınıf parametresi adlarından gövdesi içinde `MyClass2`. Bu nedenle, `Arr`'s tür parametre adları etmeyebilirsiniz, bu örnekte gösterildiği gibi:  
  
```cpp  
template<typename T, template<typename, int> class Arr>  
class MyClass2  
{  
    T t; //OK  
    Arr<T, 10> a;  
};  
```  
  
## <a name="default-template-arguments"></a>Varsayılan şablon bağımsız değişkenleri  
 Sınıf ve işlev şablonları varsayılan bağımsız değişkenler olabilir. Bir şablon bırakabilirsiniz varsayılan bağımsız değişkeni olduğunda kullandığınız zaman belirtilmemiş. Örneğin, std::vector şablonu ayırıcısı için bir varsayılan bağımsız değişkeni vardır:  
  
```cpp  
template <class T, class Allocator = allocator<T>> class vector;  
```  
  
 Çoğu durumda varsayılan std::allocator sınıfı kabul edilebilir, böyle bir vektör kullanmak için:  
  
```cpp  
vector<int> myInts;  
```  
  
 Bu, ancak gerekli özel bir ayırıcı belirtebilirsiniz, ister:  
  
```cpp  
vector<int, MyAllocator> ints;  
```  
  
 Birden çok şablon bağımsız değişkenleri için varsayılan bağımsız değişkenler ilk varsayılan bağımsız sonra tüm bağımsız değişkenler olması gerekir.  
  
 Parametreleri tüm varsayılan bir şablon kullanırken boş köşeli ayraç kullanın:  
  
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
  
## <a name="template-specialization"></a>Şablonu özelleştirme  
 Bazı durumlarda, olası veya herhangi bir türü ile aynı kodunu tanımlamak için bir şablon için istenen değil. Örneğin, yalnızca tür bağımsız değişkeni bir işaretçi ya da bir std::wstring ya da belirli bir taban sınıftan türeyen bir tür ise yürütülecek kod yolu tanımlamak isteyebilirsiniz.  Bu gibi durumlarda tanımladığınız bir *uzmanlık* belirli türü için şablon. Bir kullanıcı bu türüyle şablon başlattığında sınıfı oluşturmak için uzmanlık derleyici kullanır ve diğer tüm türleri için derleyici daha genel şablonunu seçer. Tüm parametreleri özelleştirilmiş özelleştirmeleri olan *tamamlamak özelleştirmeleri*. Yalnızca bazı parametreler özelleştirilmiş adlı bir *kısmi uzmanlığı*.  
  
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
  
 Her özel tür parametresi benzersiz olduğu sürece herhangi bir sayıda özelleştirmeleri bir şablon olabilir.   Sınıf şablonları yalnızca kısmen özelleştirilmiş. Özgün şablon olarak aynı ad alanındaki tüm tam ve kısmi özelleştirmeleri şablonu bildirilmesi gerekir.  
  
 Daha fazla bilgi için bkz: [şablonu uzmanlık](../cpp/template-specialization-cpp.md).