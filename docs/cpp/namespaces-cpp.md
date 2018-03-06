---
title: "Ad alanları (C++) | Microsoft Docs"
ms.custom: 
ms.date: 08/30/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- namespace_CPP
- using_CPP
dev_langs:
- C++
helpviewer_keywords:
- namespaces [C++], C++
- namespaces [C++]
- namespaces [C++], global
- global namespace
- Visual C++, namespaces
ms.assetid: d1a5a9ab-1cad-47e6-a82d-385bb77f4188
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 801bd8ee8e81c0126ae88c1fb9213b25b9f103dd
ms.sourcegitcommit: 4e01d36ffa64ea11bacf589f79d2f1df947e2510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="namespaces-c"></a>Ad Alanları (C++)
Bir ad alanı içindeki tanımlayıcıları (adları türleri, İşlevler, değişkenler vb.) için bir kapsam sağlayan bir bildirim temelli bölgedir. Ad alanları kod mantıksal gruplar halinde düzenlemek için ve özellikle kod temeliniz birden çok kitaplıklarını içerir yüklendiğinde oluşabilecek ad çakışmaları önlemek için kullanılır. Ad alanı kapsamındaki tüm tanımlayıcılar nitelemesiz birbirine görünür. Örneğin her tanımlayıcısı için tam adı kullanarak ad alanı dışında tanımlayıcıları üyeleri erişebilir `std::vector<std::string> vec;`, göre veya başka bir [bildirimi kullanarak](../cpp/using-declaration.md) tek bir tanımlayıcı için (`using std::string`), ya da bir [yönergesi kullanarak](../cpp/namespaces-cpp.md#using_directives) ad alanındaki tüm tanımlayıcılar için (`using namespace std;`). Üstbilgi dosyaları kodunda her zaman tam ad alanı adı kullanmanız gerekir.  
  
 Aşağıdaki örnek, bir ad alanı bildirimi gösterir ve ad alanı dışında kod üç şekilde üyeleri erişir.  
  
```cpp  
namespace ContosoData  
{      
    class ObjectManager   
    {  
    public:  
        void DoSomething() {}  
    };  
    void Func(ObjectManager) {}  
}  
```  
  
 Tam ad kullanın:  
  
```cpp  
ContosoData::ObjectManager mgr;  
mgr.DoSomething();  
ContosoData::Func(mgr);  
```  
  
 Bir kullanarak kapsam içine bir tanımlayıcı getirmek için bildirimi:  
  
```cpp  
using ContosoData::ObjectManager;  
ObjectManager mgr;  
mgr.DoSomething();  
  
```  
  
 Kullanarak bir kullanma yönergesi her şeyi ad alanında kapsam içine duruma getirmek için:  
  
```cpp  
using namespace ContosoData;
  
ObjectManager mgr;  
mgr.DoSomething();  
Func(mgr);  
  
```  
  
## <a id="using_directives"></a> using yönergelerini  
 `using` Yönergesi verir tüm adlarının bir **ad alanı** olmadan kullanılacak *ad alanı adı* açık bir niteleyici olarak. Bir kullanarak birkaç farklı tanımlayıcı bir ad alanındaki; kullanıyorsanız yönerge bir uygulama dosyasında (yani *.cpp) bir veya iki tanımlayıcıları yeni kullanıyorsanız, kullanarak bir göz önünde bulundurun yalnızca bu tanımlayıcıları kapsamı ve tüm tanımlayıcılar ad alanında duruma getirmek için bildirimi. Yerel bir değişken adı ad alanı değişkeniyle aynı ada sahipse, ad alanı değişkeni gizlenir. Genel bir değişken olarak aynı ada sahip ad alanı değişkeninin bulundurulması bir hatadır.  
  
> [!NOTE]
>  Using yönergesi (Dosya kapsamında), bir .cpp dosyasının üst yerleştirilebilen ya da bir sınıf veya işlev tanımı içinde.  
>   
>  Genel olarak, üst bilgi dosyaları yönergeleri kullanarak Geçirilmemesi (* .h) bu başlığı içeren herhangi bir dosyayı her şeyi ad alanında kapsam içine getirecek hangi adı gizleme neden ve çakışma sorunları ad olduklarından, hata ayıklamak oldukça zor. Her zaman tam olarak nitelenmiş adlar bir üstbilgi dosyası kullanın. Bu adları çok uzun alırsanız, bunları kısaltmak için bir ad alanı diğer adı kullanabilirsiniz. (Aşağıya bakın.)  
  
## <a name="declaring-namespaces-and-namespace-members"></a>Ad alanları ve ad alanı üyeleri bildirme  
 Genellikle, bir ad alanı üstbilgi dosyasında bildirmelidir. İşlev uygulamaları ayrı bir dosyaya varsa, bu örnekte olduğu gibi işlev adları nitelemek.  
  
```cpp  
//contosoData.h   
#pragma once  
namespace ContosoDataServer  
{  
    void Foo();  
    int Bar();  
  
}  
```  
  
 Contosodata.cpp işlevi uygulamalarında yerleştirdiğiniz olsa bile tam adı kullanması gereken bir `using` dosyasının üst yönerge:  
  
```cpp  
#include "contosodata.h"  
using namespace ContosoDataServer;   
  
void ContosoDataServer::Foo() // use fully-qualified name here  
{  
   // no qualification needed for Bar()  
   Bar();   
}  
  
int ContosoDataServer::Bar(){return 0;}  
```  
  
 Bir ad alanı, tek bir dosya ve birden çok dosya birden çok bloklarındaki bildirilebilir. Ön işleme sırasında birlikte derleyici parçaları birleştirir ve sonuçta elde edilen ad alanı tüm parçaları olarak bildirilen tüm üyeler içerir. Buna örnek olarak standart kitaplık üstbilgi dosyaları her bildirilen std ad alanıdır.  
  
 Adlandırılmış bir ad alanı üyeleri tarafından tanımlanan adının açık nitelik bildirilen ad alanı dışında tanımlanabilir. Ancak, tanım bildirimi ait ad alanı kapsayan bir ad alanı bildiriminde noktadan sonra görünmesi gerekir. Örneğin:  
  
```cpp  
// defining_namespace_members.cpp  
// C2039 expected  
namespace V {  
        void f();  
    }  
  
    void V::f() { }        // ok  
    void V::g() { }        // C2039, g() is not yet a member of V  
  
    namespace V {  
        void g();  
    }  
}  
```  
  
 Namespace üyelerini arasında birden çok üst bilgi dosyaları bildirilir ve doğru sırada Bu üstbilgiler eklemediniz bu hata oluşabilir.  
  
## <a name="the-global-namespace"></a>Genel ad alanı  
 Açık bir ad alanında bir tanımlayıcı bildirilmedi, örtük genel ad alanı bir parçasıdır. Genel olarak, mümkün olduğunda, giriş noktası dışında genel kapsamda bildirimleri yapmaktan kaçınmak deneyin [main işlevi](../c-language/main-function-and-program-execution.md), genel ad alanında olması gerekir. Açıkça genel tanımlayıcısı nitelemek için bir ad ile kapsam çözümü işleci olarak kullanın `::SomeFunction(x);`. Tanımlayıcı bu diğer ad alanında aynı ada sahip bir şey gelen ayırt ve ayrıca kodunuz başkalarının anlamak daha kolay hale getirmenize yardımcı olur.  
  
## <a name="the-std-namespace"></a>std ad alanı  
 Tüm C++ Standart Kitaplığı türler ve işlevler içinde bildirilen `std` ad alanı veya ad alanları iç içe içinde `std`.  
  
## <a name="nested-namespaces"></a>İç içe geçmiş ad alanları  
 Ad alanları iç içe. Sıradan iç içe geçmiş ad alanına sahip nitelenmemiş ana öğenin üyeleri, ancak üst üye olmayan erişimi iç içe geçmiş ad alanına nitelenmemiş erişimi (satır içi olarak bildirilir sürece), aşağıdaki örnekte gösterildiği gibi:  
  
```cpp  
namespace ContosoDataServer  
{  
    void Foo();   
  
    namespace Details  
    {  
        int CountImpl;  
        void Ban() { return Foo(); }  
    }  
  
    int Bar(){...};  
    int Baz(int i) { return Details::CountImpl; }      
  
}  
```  
  
 Sıradan iç içe geçmiş ad alanları, ortak arabirimi üst ad alanının parçası olmayan iç uygulama ayrıntılarını kapsüllemek için kullanılabilir.  
  
## <a name="inline-namespaces-c-11"></a>Satır içi ad alanları (C++ 11)  
 Sıradan iç içe geçmiş bir ad aksine bir satır içi ad alanı üyeleri üst ad alanı bir üyesi olarak kabul edilir. Bu özellik, bir üst ve iç içe geçmiş satır içi ad alanı içinde aşırı olan işlevler üzerinde çalışmak için aşırı yüklenmiş işlevlerdeki bağımsız değişkeni bağımlı aramayı etkinleştirir. Ayrıca, satır içi ad alanında bildirilen bir şablon için bir üst ad alanındaki uzmanlık bildirmek sağlar. Aşağıdaki örnekte nasıl dış kod gösterilir varsayılan olarak satır içi ad alanına bağlanır:  
  
```cpp  
//Header.h  
#include <string>  
  
namespace Test  
{  
    namespace old_ns  
    {  
        std::string Func() { return std::string("Hello from old"); }  
    }  
  
    inline namespace new_ns  
    {  
        std::string Func() { return std::string("Hello from new"); }  
    }  
}  
  
#include "header.h"  
#include <string>  
#include <iostream>  
  
int main()  
{  
    using namespace Test;  
    using namespace std;  
  
    string s = Func();  
    std::cout << s << std::endl; // "Hello from new"  
    return 0;  
}  
```  
  
 Aşağıdaki örnek, bir üst öğesi bir satır içi ad alanında bildirilen bir şablon olarak uzmanlık nasıl bildirebilir gösterir:  
  
```cpp  
namespace Parent  
{  
    inline namespace new_ns  
    {  
         template <typename T>  
         struct C  
         {  
             T member;  
         };  
    }  
     template<>  
     class C<int> {};  
}  
  
```  
  
 Ortak arabirimi kitaplığı değişiklikleri yönetmek için bir sürüm oluşturma mekanizması olarak satır içi ad alanları kullanın. Örneğin, bir tek üst ad alanı oluşturun ve her arabirimi üst içinde iç içe geçmiş kendi ad alanında sürümü yalıtma. En son veya tercih edilen sürüm tutan ad alanı, satır içi olarak tam ve üst ad alanı doğrudan üyesi değilmiş gibi bu nedenle sunulur. Parent::Class çağırır istemci kodu otomatik olarak yeni kod bağlarsınız. Eski sürümü kullanmayı tercih ederseniz istemcileri bu kodun sahip iç içe geçmiş ad tam yolunu kullanarak erişmeye devam edebilirsiniz.  
  
 Ad alanı bir derleme biriminde ilk bildirimine inline anahtar sözcüğü uygulanmış olması gerekir.  
  
 Aşağıdaki örnek, bir arabirim, iç içe geçmiş bir ad alanındaki her iki sürümünü gösterir. `v_20` Ad alanına sahip bazı değişikliklere karşı `v_10` arabirim ve satır içi olarak işaretlendi. Yeni Kitaplık ve çağrıları kullanan istemci kodu `Contoso::Funcs::Add` v_20 sürümünü çağıracaktır. Arama girişiminde kod `Contoso::Funcs::Divide` şimdi bir derleme zamanı hatası alırsınız. Bunlar bu işlev gerçekten ihtiyacınız varsa, bunlar erişmeye devam edebilirsiniz `v_10` açıkça çağırarak sürüm `Contoso::v_10::Funcs::Divide`.  
  
```cpp  
namespace Contoso  
{  
    namespace v_10  
    {  
        template <typename T>  
        class Funcs  
        {  
        public:  
            Funcs(void);  
            T Add(T a, T b);  
            T Subtract(T a, T b);  
            T Multiply(T a, T b);  
            T Divide(T a, T b);  
        };  
    }  
  
    inline namespace v_20  
    {  
        template <typename T>  
        class Funcs  
        {  
        public:  
            Funcs(void);  
            T Add(T a, T b);  
            T Subtract(T a, T b);  
            T Multiply(T a, T b);  
            std::vector<double> Log(double);  
            T Accumulate(std::vector<T> nums);  
      };  
    }  
}  
  
```  
  
## <a id="namespace_aliases"></a> Namespace diğer adlar  
 Namespace adlarının benzersiz olması genellikle bunlar çok kısa olmamalıdır, yani gerekir. Kod bir adının uzunluğu okumak zor yaparsa veya burada yönergeleri kullanarak kullanılamaz ve ardından gerçek adı için bir kısaltma olarak hizmet veren bir ad alanı diğer adı yapabileceğiniz bir üstbilgi dosyası yazmak yorucu olabilir. Örneğin:  
  
```cpp  
namespace a_very_long_namespace_name { class Foo {}; }  
namespace AVLNN = a_very_long_namespace_name;  
void Bar(AVLNN::Foo foo){ }  
  
```  
  
## <a name="anonymous-or-unnamed-namespaces"></a>anonim veya adlandırılmamış ad alanları  
 Açık bir ad alanı oluşturma, ancak bir ad verin değil:  
  
```cpp  
namespace  
{  
    int MyFunc(){}  
}  
```  
  
 Bu bir adlandırılmamış veya anonim ad alanı adı verilir ve değişken bildirimleri diğer dosyaları için kod görünmez olmasını istediğinizde yararlı olur (yani iç bağlantı vermediğiniz) adlı bir ad oluşturmak zorunda kalmadan. Aynı dosyada tüm kod adlandırılmamış ad alanındaki tanımlayıcıları görebilir, ancak ad alanı kendisiyle birlikte tanımlayıcıları dışında bu dosyayı görünür değildir — veya çeviri birim dışında daha kesin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Tanımlar](declarations-and-definitions-cpp.md)
