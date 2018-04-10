---
title: Üye erişim denetimi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- access control [C++]
- member access [C++]
- member-access control [C++]
ms.assetid: 2d596bca-56ad-4277-94e1-ce3db45fa14a
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88fe05ab0c0e6a1c433bf2b6007fb63c18fb5850
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="member-access-control-c"></a>Üye Erişim Denetimi (C++)
Erişim denetimleri ayırmak etkinleştirme [ortak](../cpp/public-cpp.md) öğesinden bir sınıf arabiriminin [özel](../cpp/private-cpp.md) uygulama ayrıntılarını ve [korumalı](../cpp/protected-cpp.md) yalnızca üyelerin kullanmak tarafından türetilen sınıflar. Erişim belirteci sonraki erişim belirticisi karşılaşılanaa kadar sonra bildirilen tüm üyeleri için geçerlidir.  
  
```  
class Point  
{  
public:                   
    Point( int, int ) // Declare public constructor.;  
    Point();// Declare public default constructor.  
    int &x( int ); // Declare public accessor.  
    int &y( int ); // Declare public accessor.  
  
private:                 // Declare private state variables.  
    int _x;  
    int _y;  
  
protected:      // Declare protected function for derived classes only.  
    Point ToWindowCoords();  
};  
  
```  
  
 Varsayılan erişim `private` bir sınıf ve `public` yapı ya da birleşimi. Erişim tanımlayıcıları sınıfında olabilir kez herhangi bir sayıda herhangi bir sırada kullanılır. Sınıf türü nesneleri için depolama alanı ayırma uygulamaya bağlıdır, ancak üyelere, erişim belirticileri arasında sırayla daha yüksek bellek adresleri atanması garantidir.  
  
### <a name="member-access-control"></a>Üye Erişim Denetimi  
  
|Erişim türü|Açıklama|  
|--------------------|-------------|  
|[private](../cpp/private-cpp.md)|Sınıf üyeleri bildirilen `private` yalnızca üye işlevleri ve arkadaş (sınıfları veya işlevleri) sınıfının tarafından kullanılabilir.|  
|[protected](../cpp/protected-cpp.md)|Sınıf üyeleri bildirilen `protected` üye işlevleri ve arkadaş (sınıfları veya işlevleri) sınıfının tarafından kullanılabilir. Ayrıca, bunlar sınıfından türetilen sınıflar tarafından kullanılabilir.|  
|[public](../cpp/public-cpp.md)|Sınıf üyeleri bildirilen **ortak** herhangi bir işlev tarafından kullanılabilir.|  
  
 Erişim denetimi, bunların amaçla kullanılacağını olmayan yollarla nesneleri kullanarak önlemeye yardımcı olur. Açık tür Dönüşümleri (atamaları) gerçekleştirildiğinde bu koruma kaybolur.  
  
> [!NOTE]
>  Erişim denetimi tüm adlarına eşit oranda geçerlidir: üye işlevleri, üye verileri, iç içe geçmiş sınıflar ve numaralandırmalar.  
  
## <a name="access-control-in-derived-classes"></a>Türetilen sınıflar erişim denetimi  
 Türetilen bir sınıfta hangi bir taban sınıfı üyeleri erişilebilir iki faktör denetim; aynı faktörlerin devralınan türetilmiş sınıf üyelerine erişimi kontrol edin:  
  
-   Türetilen sınıfın temel sınıfı kullanılarak olup olmadığını bildirir **ortak** belirticisinin erişim *sınıfı head* (*sınıfı head* Dilbilgisibölümündeaçıklanan[ Sınıf türleri tanımlama](http://msdn.microsoft.com/en-us/e8c65425-0f3a-4dca-afc2-418c3b1e57da)).  
  
-   Taban sınıf içinde üye erişimi nedir.  
  
 Aşağıdaki tabloda bu Etkenler ve temel sınıf üye erişimi belirleme arasındaki etkileşimler gösterilmektedir.  
  
### <a name="member-access-in-base-class"></a>Taban sınıf içinde üye erişimi  
  
|private|protected|Ortak|  
|-------------|---------------|------------|  
|Türetme erişim bakılmaksızın her zaman erişilemez|Özel türetme kullanırsanız, türetilmiş sınıf içinde özel|Özel türetme kullanırsanız, türetilmiş sınıf içinde özel|  
||Korumalı türetme kullanırsanız, türetilen sınıfta korumalı|Korumalı türetme kullanırsanız, türetilen sınıfta korumalı|  
||Ortak türetme kullanırsanız, türetilen sınıfta korumalı|Ortak türetme kullanırsanız, türetilmiş sınıf içinde ortak|  
  
 Aşağıdaki örnekte bu gösterilmektedir:  
  
```  
// access_specifiers_for_base_classes.cpp  
class BaseClass  
{  
public:  
    int PublicFunc();    // Declare a public member.  
protected:  
    int ProtectedFunc(); // Declare a protected member.  
private:  
    int PrivateFunc();   // Declare a private member.  
};  
  
// Declare two classes derived from BaseClass.  
class DerivedClass1 : public BaseClass  
{  
};  
  
class DerivedClass2 : private BaseClass  
{  
};  
  
int main()  
{  
}  
```  
  
 İçinde `DerivedClass1`, üye fonksiyonu `PublicFunc` ortak bir üyesidir ve `ProtectedFunc` korumalı üye olduğundan `BaseClass` ortak bir taban sınıf. `PrivateFunc`özel olduğu `BaseClass`, ve tüm türetilmiş sınıflara erişilemez.  
  
 İçinde `DerivedClass2`, işlevleri `PublicFunc` ve `ProtectedFunc` özel üyeler için kabul edilen `BaseClass` özel bir temel sınıftır. Yeniden `PrivateFunc` özel olduğu `BaseClass`, ve tüm türetilmiş sınıflara erişilemez.  
  
 Türetilmiş bir sınıf bir temel sınıf erişim belirteci olmadan bildirebilirsiniz. Böyle bir durumda türetme türetilmiş sınıf bildiriminin kullanıyorsa, özel olarak kabul edilir **sınıfı** anahtar sözcüğü. Türetme türetilmiş sınıf bildiriminin kullanıyorsa, ortak olarak kabul edilir `struct` anahtar sözcüğü. Örneğin, aşağıdaki kod:  
  
```  
class Derived : Base  
...  
```  
  
 eşdeğerdir:  
  
```  
class Derived : private Base  
...  
```  
  
 Benzer şekilde, aşağıdaki kod:  
  
```  
struct Derived : Base  
...  
```  
  
 eşdeğerdir:  
  
```  
struct Derived : public Base  
...  
```  
  
 Özel erişim sahibi olmayı olarak bildirilen üyeleri işlevleri için erişilebilir olmayan not edin veya bu işlevler veya sınıfları kullanılarak bildirilir sürece türetilmiş sınıfları `friend` bildirimi temel sınıf.  
  
 A **UNION** türü, bir taban sınıf sahip olamaz.  
  
> [!NOTE]
>  Özel bir taban sınıf belirtirken, açıkça kullanmanız önerilir; `private` türetilmiş sınıf kullanıcılarının üye erişimi anlamaları için anahtar sözcüğü.  
  
## <a name="access-control-and-static-members"></a>Erişim denetimi ve statik üyeler  
 `private` olarak temel bir sınıf belirttiğinizde, yalnızca statik olmayan üyeleri etkiler. Genel statik üyeler türetilmiş sınıflarda da erişilebilir. Ancak, işaretçiler, başvurular veya nesneleri kullanarak temel sınıf üyelerinin erişmek, aynı zamanda erişim denetiminin yeniden uygulandığı bir dönüştürme gerektirebilir. Aşağıdaki örnek göz önünde bulundurun:  
  
```  
// access_control.cpp  
class Base  
{  
public:  
    int Print();             // Nonstatic member.  
    static int CountOf();    // Static member.  
};  
  
// Derived1 declares Base as a private base class.  
class Derived1 : private Base  
{  
};  
// Derived2 declares Derived1 as a public base class.  
class Derived2 : public Derived1  
{  
    int ShowCount();    // Nonstatic member.  
};  
// Define ShowCount function for Derived2.  
int Derived2::ShowCount()  
{  
   // Call static member function CountOf explicitly.  
    int cCount = Base::CountOf();     // OK.  
  
   // Call static member function CountOf using pointer.  
    cCount = this->CountOf();  // C2247. Conversion of  
                               //  Derived2 * to Base * not  
                               //  permitted.  
    return cCount;  
}  
```  
  
 Önceki kodda; erişim denetimi, bir `Derived2` işaretçisinden `Base` işaretçisine dönüşümü yasaklar. **Bu** işaretçidir örtük olarak türü `Derived2 *`. Seçilecek `CountOf` işlevi, **bu** yazmak için dönüştürülmelidir `Base *`. `Base`, `Derived2` öğesinin özel dolaylı bir temel sınıfı olduğundan bu tür bir dönüştürmeye izin verilmez. Özel bir temel sınıf türüne dönüştürme yalnızca hemen türetilmiş sınıfların işaretçileri için kabul edilebilir. Bu nedenle, `Derived1 *` türünde işaretçiler `Base *` türüne dönüştürülebilir.  
  
 Kendisini seçmek üzere bir işaretçi, başvuru veya nesne kullanmadan `CountOf` işlevine açık şekilde çağrı yapmanın, herhangi bir dönüştürme yapılacağı anlamına gelmediğine dikkat edin. Bu nedenle, çağrıya izin verilir.  
  
 Türetilmiş bir sınıfın (`T`) üyeleri ve arkadaşları, bir `T` işaretçisini özel doğrudan bir `T` temel sınıfına dönüştürebilir.  
  
## <a name="access-to-virtual-functions"></a>Sanal işlevlere erişim  
 Erişim denetimi uygulanan [sanal](../cpp/virtual-cpp.md) işlevleri işlev çağrısı yapmak için kullanılan türüne göre belirlenir. İşlev bildirimlerinin geçersiz kılınması, belirli bir türe yönelik erişim denetimini etkilemez. Örneğin:  
  
```  
// access_to_virtual_functions.cpp  
class VFuncBase  
{  
public:  
    virtual int GetState() { return _state; }  
protected:  
    int _state;  
};  
  
class VFuncDerived : public VFuncBase  
{  
private:  
    int GetState() { return _state; }  
};  
  
int main()  
{  
   VFuncDerived vfd;             // Object of derived type.  
   VFuncBase *pvfb = &vfd;       // Pointer to base type.  
   VFuncDerived *pvfd = &vfd;    // Pointer to derived type.  
   int State;  
  
   State = pvfb->GetState();     // GetState is public.  
   State = pvfd->GetState();     // C2248 error expected; GetState is private;  
}  
```  
  
 Yukarıdaki örnekte, `GetState` türünün işaretçisi kullanılarak `VFuncBase` sanal işlevinin çağrılması, `VFuncDerived::GetState` öğesini çağırır ve `GetState` genel olarak kabul edilir. Bununla birlikte, `GetState` türünün işaretçisi kullanılarak `VFuncDerived` çağrılması, `GetState``VFuncDerived` sınıfında özel olarak bildirildiği için bir erişim denetimi ihlali oluşturur.  
  
> [!CAUTION]
>  `GetState` sanal işlevi, `VFuncBase` temel sınıfının işaretçisi kullanılarak çağrılabilir. Bu, çağrılan işlevin bu işlevin temel sınıfı olduğu anlamına gelmez.  
  
## <a name="access-control-with-multiple-inheritance"></a>Erişim denetimi ile birden çok devralma  
 Sanal temel sınıflar içeren birden çok devralma kafeslerinde, belirli bir ada birden fazla yolla ulaşılabilir. Bu farklı yollarda farklı erişim denetimi uygulanabileceği için derleyici en çok erişimi sağlayan yolu seçer. Aşağıdaki şekle bakın.  
  
 ![Devralma Grafiği yollarını boyunca erişim](../cpp/media/vc38v91.gif "vc38V91")  
Devralma Grafiğinin Yolları Üzerinde Erişim  
  
 Şekilde `VBase` sınıfında bildirilen bir ada her zaman `RightPath` sınıfıyla ulaşılır. `RightPath``VBase`'i özel olarak bildirirken, `LeftPath``VBase`'i genel bir temel sınıf olarak bildirdiği için sağdaki yol daha fazla erişilebilirdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)