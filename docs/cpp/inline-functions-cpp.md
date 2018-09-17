---
title: Satır içi işlevler (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __forceinline_cpp
- __inline_cpp
- inline_cpp
dev_langs:
- C++
helpviewer_keywords:
- inline functions [C++], class members
ms.assetid: 355f120c-2847-4608-ac04-8dda18ffe10c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b86c2c4031e1257e2a8a8e0f7b504686ea1c4588
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701695"
---
# <a name="inline-functions-c"></a>Satır İçi İşlevler (C++)
Sınıf bildirimi gövdesinde tanımlanan bir işlev, satır içi işlevdir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki sınıf bildiriminde, `Account` oluşturucusu bir satır içi işlevdir. Üye işlevleri `GetBalance`, `Deposit`, ve `Withdraw` olarak belirtilmeyen **satır içi** ancak satır içi işlevleri uygulanabilir.  
  
```cpp 
// Inline_Member_Functions.cpp  
class Account  
{  
public:  
    Account(double initial_balance) { balance = initial_balance; }  
    double GetBalance();  
    double Deposit( double Amount );  
    double Withdraw( double Amount );  
private:  
    double balance;  
};  
  
inline double Account::GetBalance()  
{  
    return balance;  
}  
  
inline double Account::Deposit( double Amount )  
{  
    return ( balance += Amount );  
}  
  
inline double Account::Withdraw( double Amount )  
{  
    return ( balance -= Amount );  
}  
int main()  
{  
}  
```  
  
> [!NOTE]
>  Sınıf bildiriminde, İşlevler olmadan bildirilir **satır içi** anahtar sözcüğü. **Satır içi** anahtar sözcüğü sınıfı bildiriminde belirtilebilir; sonuç aynıdır.  
  
 Belirli bir satır içi üye işlevi, her derleme biriminde aynı şekilde bildirilmelidir. Bu kısıtlama, satır içi işlevlerin örneği oluşturulmuş işlevler gibi davranmasına neden olur. Ayrıca, satır içi işlevinin yalnızca tek bir tanımı olmalıdır.  
  
 Sınıf üyesi işlevi varsayılan olarak dış bağlantı söz konusu işlev için bir tanım içeriyor sürece **satır içi** tanımlayıcısı. Bu işlevler ile açıkça bildirilmesine yok, önceki örnekte gösterir **satır içi** tanımlayıcısı; kullanarak **satır içi** işlev tanımı, satır içi işlev olmasına neden olur. Ancak, bir işlev olarak çağrıldıktan **satır içi** bu işlev çağrısı yapıldıktan sonra.  
  
## <a name="inline-inline-and-forceinline"></a>Satır içi, __inline, ve \__forceinline  
 **Satır içi** ve **__inline** belirticileri işlevin çağrıldığı her yere işlev gövdesinin bir kopyasını eklemek için derleyicinin isteyin.  
  
 Ekleme (satır içi genişletme veya satır için yerleştirme denir) yalnızca derleyicinin maliyet/kar analizinin karlı olacağını gösterdiği durumlarda oluşur. Satır içi genişletme, daha büyük boyuttaki kodun olası maliyetinde işlev-çağrı ek yükünü azaltır.  
  
 **__Forceinline** anahtar sözcüğü, Maliyet/Kar analizini geçersiz kılar ve bunun yerine programcının kararına yükümlülükten üzerinde kullanır. Kullanırken dikkatli **__forceinline**. Ayrım gözetilmeden kullanımını **__forceinline** neden olabilecek yalnızca Marjinal bir performans artışı ile daha büyük kod veya, bazı durumlarda performans kayıplarına (nedeniyle artan daha büyük bir yürütülebilir, örneğin disk belleği) bile.  
  
 Satır içi işlevleri kullanmak, işlev çağrıları ile ilgili ek yükü ortadan kaldırdığı için programınızı daha hızlı yapabilir. Satır içi olarak genişletilen işlevler için, normal işlevlerde kullanılamayan kod iyileştirmeleri yapılır.  
  
 Derleyici, satır içi genişleme seçeneklerine ve anahtar sözcüklerine öneri olarak davranır. İşlevlerin satır içi olacağına dair bir garanti yoktur. Belirli bir işlevi satır içi derleyiciye bile zorlayamaz **__forceinline** anahtar sözcüğü. İle derlerken **/CLR**, derleyici işleve uygulanmış güvenlik öznitelikleri varsa bu satır bir işlev olur.  
  
 **Satır içi** anahtar sözcüğü yalnızca C++'da kullanılabilir. **__İnline** ve **__forceinline** anahtar sözcükleri hem C'de hem de C++'ta kullanılabilir. Önceki sürümlerle uyumluluk için **eşanlamlıdır** eşanlamlıdır **__inline**.  
  
 **Satır içi** anahtar sözcüğü derleyiciye satır içi genişletmelerin tercih edildiğini bildirir. Ancak, derleyici işlevin ayrı bir örneğini oluşturabilir (örneklediğinizde) ve satır içi kod eklemek yerine standart arama bağlantıları oluşturur. Buna izin veren iki durum vardır:  
  
-   Özyinelemeli işlevler.  
  
-   Çeviri birimi içinde başka bir yerdeki işaretçi üzerinden başvurulan işlevler.  
  
 Bu nedenle ile etkileyebilir karıştırılabilir *diğerleri başkaları gibi*, derleyici; kararımıza, bağlı olmamalıdır **satır içi** bir işlevi satır içine alınmayacak kadar belirticisine.  
  
 Normal işlevlerde olduğu gibi, satır içi işlevler için bağımsız değişkenlerin değerlendirilmesinde belirlenmiş bir sıra yoktur. Aslında, bağımsız değişkenlerin normal işlev çağrısı protokolü kullanılarak geçirildiği durumların değerlendirilmesindeki sıralamadan farklı olabilir.  
  
 [/Ob](../build/reference/ob-inline-function-expansion.md) derleyicisi iyileştirme seçeneği satır içi işlev genişletmesinin gerçekten oluşup oluşmadığını belirlemek yardımcı olur.  
  
 [/ LTCG](../build/reference/ltcg-link-time-code-generation.md) çapraz-modül inlining'i olup olmadığı, kaynak kodunda istendi bağımsız olarak gerçekleştirir.  
  
### <a name="example-1"></a>Örnek 1  
  
```cpp 
// inline_keyword1.cpp  
// compile with: /c  
inline int max( int a , int b ) {  
   if( a > b )   
      return a;  
   return b;  
}  
```  
  
 Bir sınıfın üye işlevleri kullanarak ya da satır içi bildirilebilir **satır içi** anahtar sözcüğü veya sınıf tanımı içine işlev tanımı yerleştirerek.  
  
### <a name="example-2"></a>Örnek 2  
  
```cpp 
// inline_keyword2.cpp  
// compile with: /EHsc /c  
#include <iostream>  
using namespace std;  
  
class MyClass {  
public:  
   void print() { cout << i << ' '; }   // Implicitly inline  
private:  
   int i;  
};  
```  
  
### <a name="microsoft-specific"></a>Microsoft'a Özgü  
 **__İnline** anahtar sözcüğü, eşdeğer **satır içi**.  
  
 Bile **__forceinline**, derleyici her durumda satır içi kod yapamaz. Derleyici, şu durumlarda bir işlevi satır içi yapamaz:  
  
-   İşlev veya çağıranı /Ob0 (hata ayıklama için varsayılan seçenek) ile derlenir.  
  
-   İşlev ve çağıran farklı türde özel durum işlemelerini kullanır (birinde C++ özel durum işlemesi, diğerinde yapı özel durum işlemesi).  
  
-   İşlevin değişken bağımsız değişken listesi vardır.  
  
-   İşlev; satır içi derlemeyi, /Og, /Ox, /O1 veya /O2 ile derlenmediği sürece kullanır.  
  
-   İşlev özyinelemelidir ve eşlik değil **#pragma inline_recursion(on)**. Pragma ile özyinelemeli işlevler varsayılan 16 aramalı derinliğe kadar satır içi yapılırlar. Satır içi derinliğini azaltmak için kullanma [inline_depth](../preprocessor/inline-depth.md) pragması.  
  
-   İşlev sanaldır ve sanal olarak çağrılır. Sanal işlevlere doğrudan çağrılar satır içi yapılabilir.  
  
-   Program işlevin adresini alır ve çağrı işlev işaretçisi aracılığıyla yapılır. Adresleri alınmış olan doğrudan işlev çağrıları satır içi yapılabilir.  
  
-   İşlev ayrıca ile işaretlenmiş [naked](../cpp/naked-cpp.md) [__declspec](../cpp/declspec.md) değiştiricisi.  
  
 Derleyicinin satır içi yapamazsa ile bildirilen bir işlevi **__forceinline**, aşağıdakiler haricinde, düzey 1 uyarısını oluşturur:
  
-   İşlev /Od veya /Ob0 kullanarak derlenir. Hiçbir satır içi kullanım bu gibi durumlarda beklenir.     
  
-   İşlevi, harici olarak bulunan bir kitaplık ya da başka bir çeviri biriminde tanımlanan veya bir sanal çağrı hedefi ya da dolaylı çağrı hedefi. Derleyici, geçerli çeviri biriminde bulunamıyor satır içi olmayan kod tanımlanamıyor.  
  
 Özyinelemeli İşlevler, satır içi olarak değiştirilebilir tarafından belirtilen bir derinlik olabilir [inline_depth](../preprocessor/inline-depth.md) pragması, en çok 16 çağrısı. Bu derinlikten sonra yinelenen işlev çağrıları, işlev örneği çağrıları olarak kabul edilir.  Özyinelemeli işlevlerin derinliği 16'yı geçmeyecek şekilde satır içi buluşsal yöntem tarafından incelenir. [İnline_recursion](../preprocessor/inline-recursion.md) pragması şu anda bir işlevin satır içi genişletme denetler. Bkz: [satır içi işlev genişletmesi](../build/reference/ob-inline-function-expansion.md) (/ Ob) derleyici seçeneği ilgili bilgiler için.  
  
**END Microsoft özgü**

 Kullanma hakkında daha fazla bilgi için **satır içi** belirticisi bakın:  
  
-   [Satır içi sınıfı üye fonksiyonları](../cpp/inline-functions-cpp.md)  
  
-   [dllexport ve dllimport ile Satır İçi C++ İşlevlerini Tanımlama](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)  
  
## <a name="when-to-use-inline-functions"></a>Satır içi işlevlerin ne zaman kullanılacağı  
 Satır içi işlevler, en çok özel veri üyelerine erişme gibi küçük işlevler için yararlıdır. Bu bir veya iki satırlık "erişimci" işlevlerinin temel amacı, nesneler hakkında durum bilgileri döndürmektir; kısa işlevler işlev çağrılarının ek yüküne karşı duyarlıdır. Daha uzun işlevler, çağırma/döndürme dizisinde nispeten daha az süre harcar ve satır içine alma özelliğinden yararlanır.  
  
 A `Point` sınıfı şu şekilde tanımlanabilir:  
  
```cpp 
// when_to_use_inline_functions.cpp  
class Point  
{  
public:  
    // Define "accessor" functions as  
    //  reference types.  
    unsigned& x();  
    unsigned& y();  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
inline unsigned& Point::x()  
{  
    return _x;  
}  
inline unsigned& Point::y()  
{  
    return _y;  
}  
int main()  
{  
}  
```  
  
 Koordinat işleme varsayılarak olan istemcisinde nispeten daha sık karşılaşılan bir işlemi iki erişimci işlevi belirterek bu tür bir sınıfın (`x` ve `y` önceki örnekte) olarak **satır içi** genellikle kaydeder iş yükünü:  
  
-   İşlev çağrıları (parametre geçirme ve nesnenin adresini yığına yerleştirme dahil)  
  
-   Arayanın yığın çerçevesinin korunması  
  
-   Yeni yığın çerçevesi kurulumu  
  
-   Dönüş değeri iletişimi  
  
-   Eski yığın çerçevesini geri yükleme  
  
-   döndürülecek  
  
## <a name="inline-functions-vs-macros"></a>Makrolar ve satır içi işlevler  
 Olsa da (işlev kodunu derleme zamanında çağrısı noktasında genişletildiğinden) satır içi işlevlerle makrolar benzer, satır içi işlevlerle makrolar, önişlemci tarafından genişletilir ancak derleyici tarafından ayrıştırılan. Sonuç olarak, bazı önemli farklılıklar vardır:  
  
-   Satır içi işlevler normal işlevlerde zorlanan tür güvenliği, tüm protokoller izleyin.  
  
-   Satır içi işlevleri içerirler hariç, herhangi bir işlev olarak aynı sözdizimini kullanılarak belirtilen **satır içi** işlevi bildirimindeki anahtar sözcüğü.  
  
-   Satır içi işlevler için bağımsız değişken olarak geçirilen ifade bir kez değerlendirilir. Bazı durumlarda, bağımsız değişkenleri olarak geçtiklerinde makrolara ifadeleri birden fazla kez değerlendirilebilir.  
  
 Aşağıdaki örnek, büyük küçük harflere dönüştürür bir makro gösterir:  
  
```cpp 
// inline_functions_macro.c  
#include <stdio.h>  
#include <conio.h>  
  
#define toupper(a) ((a) >= 'a' && ((a) <= 'z') ? ((a)-('a'-'A')):(a))  
  
int main() {  
   char ch;  
   printf_s("Enter a character: ");  
   ch = toupper( getc(stdin) );  
   printf_s( "%c", ch );  
}  
//  Sample Input:  xyz  
// Sample Output:  Z  
```  
  
 İfade amacı `toupper(getc(stdin))` bir karakter konsol CİHAZDAN okuma, (`stdin`) ve gerekirse büyük harfe dönüştürdüyseniz.  
  
 Makro uygulanması nedeniyle `getc` karakterin büyük olup olmadığını belirlemek için bir kez yürütülmüş veya "a" ve belirlemek için "z" küçüktür veya eşittir olmasından sonra eşittir Bu aralık içinde olup olmadığını `getc` karakteri büyük harfe dönüştürülecek yeniden yürütülür. Başka bir deyişle, ideal olarak, yalnızca bir beklemesi gerekir, program için iki veya üç karakter bekler.  
  
 Satır içi işlevler, daha önce açıklanan bildirime:  
  
```cpp 
// inline_functions_inline.cpp  
#include <stdio.h>  
#include <conio.h>  
  
inline char toupper( char a ) {  
   return ((a >= 'a' && a <= 'z') ? a-('a'-'A') : a );  
}  
  
int main() {  
   printf_s("Enter a character: ");  
   char ch = toupper( getc(stdin) );  
   printf_s( "%c", ch );  
}  
```  
  
```Output  
Sample Input: a  
Sample Output: A  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [noinline](../cpp/noinline.md)   
 [auto_inline](../preprocessor/auto-inline.md)