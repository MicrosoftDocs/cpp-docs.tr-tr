---
title: Sınıf üyelerine genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- members [C++], types of class members
- members [C++]
- class members [C++], types of
- class members
ms.assetid: 8802cfa9-705d-4f37-acde-245d6838010c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd280255afe98aa5ca512c63bb00623891eafc4f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="class-member-overview"></a>Sınıf Üyelerine Genel bakış
Sınıfta veya yapı onun üyeleri oluşur. Bir sınıf yaptığı işi kendi üye işlevleri tarafından gerçekleştirilir. Sakladığı durumu veri üyeleri depolanır. Başlatma üyelerinin oluşturucular ve temizleme işini bellek boşaltma gibi yapılır ve kaynakları serbest bırakma Yıkıcılar tarafından yapılır. C ++ 11 ve sonraki sürümlerinde, veri üyeleri noktasında bildirimi başlatılması kullanabilirsiniz ve genellikle gerekir.  
  
## <a name="kinds-of-class-members"></a>Sınıf üyeleri türleri  
 Tam kategori listesi, üye aşağıdaki gibidir:  
  
-   [Özel üye işlevleri](special-member-functions.md).  
  
-   [Üye işlevlerine genel bakış](overview-of-member-functions.md).  
  
-   [Veri üyeleri](static-members-cpp.md) yerleşik türleri ve diğer kullanıcı tanımlı türler.  
  
-   İşleçler  
  
-   [İç içe geçmiş sınıf bildirimleri](nested-class-declarations.md) ve.)  
  
-   [Birleşimler](unions.md)  
  
-   [Numaralandırmalar](../cpp/enumerations-cpp.md).  
  
-   [Bit alanları](../cpp/cpp-bit-fields.md).  
  
-   [Arkadaş](../cpp/friend-cpp.md).  
  
-   [Diğer adlar ve tür tanımları](../cpp/aliases-and-typedefs-cpp.md).  
  
    > [!NOTE]
    >  Sınıf bildirimi içinde bulunduğundan arkadaşlar yukarıdaki listeye dahil edilmiştir. Ancak sınıf kapsamı içinde olmadıklarından gerçek sınıf üyeleri değildirler.  
  
## <a name="example-class-declaration"></a>Örnek sınıf bildirimi  
 Aşağıdaki örnek, bir basit sınıf bildirimi gösterir:  
  
```  
// TestRun.h  
  
class TestRun  
{  
    // Start member list.  
  
    //The class interface accessible to all callers.  
public:  
    // Use compiler-generated default constructor:  
    TestRun() = default;   
    // Don't generate a copy constructor:  
    TestRun(const TestRun&) = delete;    
    TestRun(std::string name);  
    void DoSomething();  
    int Calculate(int a, double d);  
    virtual ~TestRun();  
    enum class State { Active, Suspended };  
  
    // Accessible to this class and derived classes only.  
protected:  
    virtual void Initialize();  
    virtual void Suspend();  
    State GetState();  
  
    // Accessible to this class only.  
private:  
    // Default brace-initialization of instance members:  
    State _state{ State::Suspended };   
    std::string _testName{ "" };   
    int _index{ 0 };  
  
    // Non-const static member:  
    static int _instances;  
    // End member list.  
};  
  
// Define and initialize static member.  
int TestRun::_instances{ 0 };  
```  
  
## <a name="member-accessibility"></a>Üye erişilebilirlik  
 Sınıf üyeleri üye listesinde bildirilir. Üye listesi bir sınıfın herhangi bir sayıda bölünebilir `private`, `protected` ve **ortak** erişim tanımlayıcıları bilinen anahtar sözcükleriyle bölümler.  İki nokta **:** erişim belirticisi izlemeniz gerekir.  Bu bölümlerin bitişik olması gerekmez, diğer bir deyişle, bu anahtar sözcüklerden biri üye listesinde birkaç kez görünebilir.  Sonraki erişim belirticisi veya kapanış ayracına kadar, anahtar sözcük tüm üyelerin erişimini belirler. Daha fazla bilgi için bkz: [üye erişim denetimi (C++)](../cpp/member-access-control-cpp.md).  
  
## <a name="static-members"></a>Statik üyeler  
 Veri üye statik olarak sınıfın tüm nesneleri aynı kopyasını erişimi yani bildirilebilir. Üye işlevi; bu durumda yalnızca statik veri üyeleri sınıfın erişebilmesi için statik olarak bildirilmesi (ve hiçbir *bu* işaretçisi). Daha fazla bilgi için bkz: [statik veri üyeleri](../cpp/static-members-cpp.md).  
  
## <a name="special-member-functions"></a>Özel üye işlevleri  
 Özel üye işlevleri, bunları kaynak kodunda belirtmezseniz, otomatik olarak derleyici tarafından sağlanan işlevlerdir.  
  
1.  Varsayılan oluşturucu  
  
2.  Kopya oluşturucu  
  
3.  **(C ++ 11)**  Taşıma Oluşturucusu  
  
4.  Kopya atama işleci  
  
5.  **(C ++ 11)**  Taşıma atama işleci  
  
6.  Yok edici  
  
Daha fazla bilgi için bkz: [özel üye işlevleri](../cpp/special-member-functions.md).
  
## <a name="memberwise-initialization"></a>Memberwise başlatma  
 C ++ 11 ve sonraki sürümlerinde, statik olmayan üye bildirimleri başlatıcıları içerebilir.  
  
```  
  
class CanInit  
{  
public:  
    long num {7};       // OK in C++11  
    int k = 9;          // OK in C++11  
    static int i = 9; // Error: must be defined and initialized  
                      // outside of class declaration.  
  
    // initializes num to 7 and k to 9  
    CanInit(){}  
  
    // overwrites original initialized value of num:  
    CanInit(int val) : num(val) {}  
};  
int main()  
{  
}  
```  
  
 Üye bir oluşturucuda bir değer atanırsa, bu değer ile üye bildirimi noktasında başlatıldı değeri üzerine yazar.  
  
 Belirli bir sınıf türünün tüm nesneleri için statik veri üyelerinin paylaşılan tek bir kopyası vardır. Statik veri üyeleri tanımlanmış olmalıdır ve dosya kapsamında başlatılabilir. (Statik veri üyeleri hakkında daha fazla bilgi için bkz: [statik veri üyeleri](../cpp/static-members-cpp.md).) Aşağıdaki örnekte bu başlatmaların nasıl yapıldığı gösterilmektedir:  
  
```  
// class_members2.cpp  
class CanInit2  
{  
public:  
    CanInit2() {} // Initializes num to 7 when new objects of type   
                 //  CanInit are created.  
    long     num {7};  
    static int i;  
    static int j;  
};  
  
// At file scope:  
  
// i is defined at file scope and initialized to 15.  
// The initializer is evaluated in the scope of CanInit.  
int CanInit2::i = 15;  
  
// The right side of the initializer is in the scope   
// of the object being initialized  
int CanInit2::j = i;  
```  
  
> [!NOTE]
>  Tanımlanan `CanInit2` öğesinin `i` sınıfının bir üyesi olduğunu belirtmek için, sınıf adı `i`, `CanInit2` öğesinden önce gelmelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)
