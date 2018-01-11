---
title: "arkadaş (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: friend_cpp
dev_langs: C++
helpviewer_keywords:
- member access, from friend functions
- friend classes [C++]
- friend keyword [C++]
ms.assetid: 8fe9ee55-d56f-40cd-9075-d9fb1375aff4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46caba9230676e30cde02e31cc231d606f446767
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="friend-c"></a>friend (C++)
Bazı durumlarda, bir sınıf üyesi olmayan işlevlere veya ayrı bir sınıf tüm üyeleri için üye düzeyinde erişim vermek daha uygundur. Yalnızca sınıfı uygulayan kendi arkadaş olan bildirebilirsiniz. Bir işlev veya sınıf kendisini herhangi bir sınıf bir arkadaş bildiremezsiniz. Bir sınıf tanımı içinde `friend` anahtar sözcüğü ve üye olmayan işlevi veya sınıfınızın özel ve korumalı üyeleri erişim vermek için başka bir sınıf adı.         Bir şablon açıklamasında bir tür parametresi bir arkadaş olarak bildirilebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class friend F  
friend F;  
```  
  
## <a name="friend-declarations"></a>Arkadaş bildirimleri  
 Daha önce bildirilmemiş bir arkadaş işlevi bildirirseniz bu işlev kapsayan nonclass kapsama dışarı aktarılır.  
  
 Bunlar kullanarak bildirilmiş sanki arkadaş bildiriminde bildirilen işlevler kabul edilir `extern` anahtar sözcüğü. (Hakkında daha fazla bilgi için `extern`, bkz: [statik depolama sınıfı tanımlayıcıları](http://msdn.microsoft.com/en-us/3ba9289a-a412-4a17-b319-ceb2c087df48).)  
  
 Genel kapsamlı işlevleri kendi prototipleri önce arkadaşlar olarak bildirilebilir rağmen üye işlevleri kendi tam sınıf bildirimi görünümünü önce arkadaşlar olarak bildirilemez. Aşağıdaki kod, bu neden başarısız gösterir:  
  
```cpp  
class ForwardDeclared;   // Class name is known.  
class HasFriends  
{  
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected  
};  
```  
  
 Önceki örnekte sınıf adını girer `ForwardDeclared` kapsam, ancak tam bildirimi — özellikle işlev bildirir bölümü `IsAFriend` — bilinmiyor. Bu nedenle, `friend` sınıfı bildiriminde `HasFriends` bir hata oluşturur.  
  
 C ++ 11 başlayarak, bir sınıf için arkadaş bildirimleri iki tür vardır:  
  
```cpp  
friend class F;  
friend F;  
```  
  
 Aynı adı taşıyan varolan bir sınıfı en içteki ad alanında bulunduysa ilk formun yeni bir sınıf F sunar.  **C ++ 11**: ikinci formun yeni bir sınıf sunmaz; sınıf zaten bildirilmiş ve bir şablon türü parametresi ya da bir arkadaş olarak typedef bildirirken kullanılmalıdır olduğunda kullanılabilir.  
  
 Kullanım `class friend F` zaman başvurulan tür değil henüz bildirildikten:  
  
```cpp  
namespace NS  
{  
    class M  
    {  
        class friend F;  // Introduces F but doesn't define it  
    };  
}  
```  
  
```cpp  
namespace NS  
{  
    class M  
    {  
        friend F; // error C2433: 'NS::F': 'friend' not permitted on data declarations  
    };  
}  
```  
  
 Aşağıdaki örnekte, `friend F` başvurduğu `F` NS kapsamı dışında bildirilmiş sınıfı.  
  
```cpp  
class F {};  
namespace NS  
{  
    class M  
    {  
        friend F;  // OK   
    };  
}  
```  
  
 Kullanım `friend F` bir şablon parametresi bir arkadaş olarak bildirmek için:  
  
```cpp  
template <typename T>  
class my_class  
{  
    friend T;  
    //...  
};  
```  
  
 Kullanım `friend F` typedef arkadaş olarak bildirmek için:  
  
```cpp  
class Foo {};  
typedef Foo F;  
  
class G  
{  
    friend F; // OK  
    friend class F // Error C2371 -- redefinition  
};  
```  
  
 Arkadaş birbirleriyle olan iki sınıf bildirmek için tüm ikinci sınıfı bir ilk sınıf arkadaş belirtilmelidir. Bu kısıtlama nedeni derleyici tek tek arkadaş işlevleri yalnızca ikinci sınıfı burada bildirilmiş noktada bildirmek için yeterli bilgiye sahip olur.  
  
> [!NOTE]
>  Tüm ikinci sınıfı ilk sınıf arkadaşınıza olması gerekse de, ilk sınıfında hangi işlevleri ikinci sınıfı arkadaşların olacaktır seçebilirsiniz.  
  
## <a name="friend-functions"></a>arkadaş işlevleri  
 A `friend` işlevidir bir sınıf üyesi değildir ancak sınıfının özel ve korumalı üye erişimi olan bir işlev. Arkadaş işlevleri sınıf üyeleri olarak kabul edilmez; özel erişim ayrıcalıkları verilmiş normal dış işlevler oldukları. Arkadaş sınıfının kapsamında değildir ve bunlar üye seçim işleçleri kullanarak adlandırılır değil (**.** ve -**>**) başka bir sınıf üyesi olmadığı sürece. A `friend` işlevi erişim verilmesi sınıfı tarafından bildirildi. `friend` Bildirimi yerleştirilebilen herhangi bir yere sınıfı bildiriminde. Erişim denetimi anahtar sözcükleri etkilenmez.  
  
 Aşağıdaki örnekte gösterildiği bir `Point` sınıfı ve bir arkadaş işlevi `ChangePrivate`. `friend` İşlevi olan özel veri üyesi erişimi `Point` parametre olarak aldığı nesne.  
  
```cpp  
// friend_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Point  
{  
    friend void ChangePrivate( Point & );  
public:  
    Point( void ) : m_i(0) {}  
    void PrintPrivate( void ){cout << m_i << endl; }  
  
private:  
    int m_i;  
};  
  
void ChangePrivate ( Point &i ) { i.m_i++; }  
  
int main()  
{  
   Point sPoint;  
   sPoint.PrintPrivate();  
   ChangePrivate(sPoint);  
   sPoint.PrintPrivate();  
// Output: 0  
           1  
}  
```  
  
## <a name="class-members-as-friends"></a>Sınıf üyeleri arkadaşlar olarak  
 Sınıf üyesi işlevleri, diğer sınıf arkadaşlarınız olarak bildirilebilir. Aşağıdaki örnek göz önünde bulundurun:  
  
```cpp  
// classes_as_friends1.cpp  
// compile with: /c  
class B;  
  
class A {  
public:  
   int Func1( B& b );  
  
private:  
   int Func2( B& b );  
};  
  
class B {  
private:  
   int _b;  
  
   // A::Func1 is a friend function to class B  
   // so A::Func1 has access to all members of B  
   friend int A::Func1( B& );  
};  
  
int A::Func1( B& b ) { return b._b; }   // OK  
int A::Func2( B& b ) { return b._b; }   // C2248  
```  
  
 Önceki örnekte, yalnızca işlevi `A::Func1( B& )` sınıfı friend erişim izni `B`. Bu nedenle, özel üyesine erişim `_b` doğru olduğu `Func1` sınıfının `A` de `Func2`.  
  
 A `friend` sınıfı, üye işlevleri tümü arkadaş işlevleri bir sınıfın bir sınıf, diğer bir deyişle, üye işlevleri diğer sınıfının özel ve korumalı üye erişimi. Varsayalım `friend` sınıfı bildiriminde `B` eklenmiştir:  
  
```cpp  
friend class A;  
```  
  
 Bu durumda, tüm üye işlevleri sınıfında `A` sınıfına friend erişim izni verilen `B`. Aşağıdaki kod, bir arkadaş sınıf örneğidir:  
  
```cpp  
// classes_as_friends2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class YourClass {  
friend class YourOtherClass;  // Declare a friend class  
public:  
   YourClass() : topSecret(0){}  
   void printMember() { cout << topSecret << endl; }  
private:  
   int topSecret;  
};  
  
class YourOtherClass {  
public:  
   void change( YourClass& yc, int x ){yc.topSecret = x;}  
};  
  
int main() {  
   YourClass yc1;  
   YourOtherClass yoc1;  
   yc1.printMember();  
   yoc1.change( yc1, 5 );  
   yc1.printMember();  
}  
```  
  
 Arkadaşlık açıkça şekilde belirtilmediği sürece karşılıklı değil. Yukarıdaki örnekte, üye işlevlerini `YourClass` özel üyeleri erişemiyor `YourOtherClass`.  
  
 Yönetilen tür herhangi arkadaş işlevleri, arkadaş sınıfları veya arkadaş arabirimleri olamaz.  
  
 Arkadaşlık değil devralınır, öğesinden türetilmiş sınıflar anlamına `YourOtherClass` erişemiyor `YourClass`ait özel üyeler. Arkadaşlık değil geçişli, sınıflar, arkadaşların; bu nedenle `YourOtherClass` erişemiyor `YourClass`ait özel üyeler.  
  
 Dört sınıf bildirimleri aşağıdaki şekilde gösterilmiştir: `Base`, `Derived`, `aFriend`, ve `anotherFriend`. Yalnızca sınıf `aFriend` özel üyeleri doğrudan erişimi `Base` (ve tüm üyelerine `Base` devralmış).  
  
 ![Arkadaş ilişki etkilerini](../cpp/media/vc38v41.gif "vc38V41")  
Arkadaş ilişki etkileri  
  
## <a name="inline-friend-definitions"></a>Satır içi arkadaş tanımları  
 Arkadaş işlevleri sınıf bildirimi içinde tanımlanabilir. Bu işlevler, satır içi işlevlerdir ve üye satır içi işlevleri gibi, tüm sınıf üyeleri görüldükten hemen sonra tanımlanmış gibi davranırlar, ancak bu durum sınıf kapsamı (sınıf bildiriminin sonu) kapatılmadan önce gerçekleşir.  
  
 Sınıf bildirimi içinde tanımlanan arkadaş işlevleri çevreleyen sınıf kapsamında dikkate alınmaz; dosya kapsamındadırlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)