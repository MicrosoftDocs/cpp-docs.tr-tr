---
title: "Satır içi işlevler (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: de370d8dbff1f1340539adc825f7f5316c59a468
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inline-functions-c"></a>Satır İçi İşlevler (C++)
Sınıf bildirimi gövdesinde tanımlanan bir işlev, satır içi işlevdir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki sınıf bildiriminde, `Account` oluşturucusu bir satır içi işlevdir. Üye işlevleri `GetBalance`, `Deposit`, ve `Withdraw` olarak belirtilmemiş **satır içi** ancak satır içi işlevler uygulanabilir.  
  
```  
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
>  Sınıf bildiriminde işlevleri olmadan bildirilen **satır içi** anahtar sözcüğü. **Satır içi** anahtar sözcüğü sınıfı bildiriminde belirtilebilir; sonuç aynıdır.  
  
 Belirli bir satır içi üye işlevi, her derleme biriminde aynı şekilde bildirilmelidir. Bu kısıtlama, satır içi işlevlerin örneği oluşturulmuş işlevler gibi davranmasına neden olur. Ayrıca, satır içi işlevinin yalnızca tek bir tanımı olmalıdır.  
  
 Sınıf üye işlevi bu işlev için bir tanım içeriyor sürece dış bağlantı için varsayılan olarak **satır içi** tanımlayıcısı. Önceki örnekte bu işlevleri açıkça ile bildirilmesi gereken olmayan gösterir **satır içi** kullanarak; tanımlayıcısı **satır içi** işlev tanımı satır içi işlev olması neden olur. Ancak, bir işlev olarak redeclare geçersiz **satır içi** sonra bu işlevi çağrısı.  
  
## <a name="inline-inline-and-forceinline"></a>Satır içi, __inline, ve \__forceinline  
 `inline` ve `__inline` belirticileri, işlevin çağrıldığı her yere işlev gövdesinin bir kopyasını eklemek için talimat verir.  
  
 Ekleme (satır içi genişletme veya satır için yerleştirme denir) yalnızca derleyicinin maliyet/kar analizinin karlı olacağını gösterdiği durumlarda oluşur. Satır içi genişletme, daha büyük boyuttaki kodun olası maliyetinde işlev-çağrı ek yükünü azaltır.  
  
 `__forceinline` anahtar sözcüğü, maliyet/kar analizini geçersiz kılar ve bunun yerine programcının kararına dayanır. `__forceinline` kullanırken dikkatli çalışın. Rasgele `__forceinline` kullanımı, yalnızca marjinal bir performans artışı ile daha büyük kod oluşmasına neden ya da bazı durumlarda performans kayıplarına dahi neden olabilir (örneğin daha büyük çalıştırılabilir belleğin artmasından dolayı).  
  
 Satır içi işlevleri kullanmak, işlev çağrıları ile ilgili ek yükü ortadan kaldırdığı için programınızı daha hızlı yapabilir. Satır içi olarak genişletilen işlevler için, normal işlevlerde kullanılamayan kod iyileştirmeleri yapılır.  
  
 Derleyici, satır içi genişleme seçeneklerine ve anahtar sözcüklerine öneri olarak davranır. İşlevlerin satır içi olacağına dair bir garanti yoktur. Bir `__forceinline` anahtar sözcüğünü kullansanız bile belirli bir işlevin satır içi olması için derleyiciyi zorlayamazsınız. İle derleme yapılırken **/CLR**, derleyici işleve uygulanan güvenlik öznitelik varsa bu hizalı değil işlevi olur.  
  
 **Satır içi** anahtar sözcüğü yalnızca C++ içinde kullanılabilir. `__inline` ve `__forceinline` anahtar sözcükleri hem C'de hem de C++'ta kullanılabilir. Önceki sürümlerle uyumluluk için **_inline** eşanlamlısı olduğu `__inline`.  
  
 **Satır içi** anahtar sözcüğü, satır içi genişletme tercih edilir derleyici söyler. Ancak, derleyici işlevin ayrı bir örneğini oluşturabilir (örneklediğinizde) ve satır içi kod eklemek yerine standart arama bağlantıları oluşturur. Buna izin veren iki durum vardır:  
  
-   Özyinelemeli işlevler.  
  
-   Çeviri birimi içinde başka bir yerdeki işaretçi üzerinden başvurulan işlevler.  
  
 Bu nedenlerden ile etkileyebilir satır içi kullanım, *diğerleri gibi*, derleyici; kümeleri, üzerinde bağımlı olmamalıdır **satır içi** içermesinden olması için bir işlev neden tanımlayıcısı.  
  
 Normal işlevlerde olduğu gibi, satır içi işlevler için bağımsız değişkenlerin değerlendirilmesinde belirlenmiş bir sıra yoktur. Aslında, bağımsız değişkenlerin normal işlev çağrısı protokolü kullanılarak geçirildiği durumların değerlendirilmesindeki sıralamadan farklı olabilir.  
  
 [/Ob](../build/reference/ob-inline-function-expansion.md) satır içi işlev genişletmesi gerçekte oluşup oluşmadığını belirleyin derleyici en iyi duruma getirme seçeneği yardımcı olur.  
  
 [/ LTCG](../build/reference/ltcg-link-time-code-generation.md) çapraz modülü olup, kaynak kodunda istendi bakılmaksızın satır içi kullanım gerçekleştirir.  
  
### <a name="example-1"></a>Örnek 1  
  
```  
// inline_keyword1.cpp  
// compile with: /c  
inline int max( int a , int b ) {  
   if( a > b )   
      return a;  
   return b;  
}  
```  
  
 Sınıf üyesi işlevleri ya da kullanarak satır içi bildirilebilir **satır içi** anahtar sözcüğü veya sınıf tanımı içinde işlev tanımı yerleştirebilirsiniz.  
  
### <a name="example-2"></a>Örnek 2  
  
```  
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
 `__inline` Anahtar sözcüğü eşdeğerdir **satır içi**.  
  
 `__forceinline` kullanılsa da, derleyici her durumda satır içi kodlamayı yapamaz. Derleyici, şu durumlarda bir işlevi satır içi yapamaz:  
  
-   İşlev veya çağıranı /Ob0 (hata ayıklama için varsayılan seçenek) ile derlenir.  
  
-   İşlev ve çağıran farklı türde özel durum işlemelerini kullanır (birinde C++ özel durum işlemesi, diğerinde yapı özel durum işlemesi).  
  
-   İşlevin değişken bağımsız değişken listesi vardır.  
  
-   İşlev; satır içi derlemeyi, /Og, /Ox, /O1 veya /O2 ile derlenmediği sürece kullanır.  
  
-   İşlev yinelemelidir ve eşlik değil **#pragma inline_recursion(on)**. Pragma ile özyinelemeli işlevler varsayılan 16 aramalı derinliğe kadar satır içi yapılırlar. Satır içi kullanım derinliği azaltmak için kullanma [inline_depth](../preprocessor/inline-depth.md) pragması.  
  
-   İşlev sanaldır ve sanal olarak çağrılır. Sanal işlevlere doğrudan çağrılar satır içi yapılabilir.  
  
-   Program işlevin adresini alır ve çağrı işlev işaretçisi aracılığıyla yapılır. Adresleri alınmış olan doğrudan işlev çağrıları satır içi yapılabilir.  
  
-   İşlevi de işaretlenmiş [naked](../cpp/naked-cpp.md) [__declspec](../cpp/declspec.md) değiştiricisi.  
  
 Satır içi derleyici olamaz, bir işlev ile bildirilen `__forceinline`, ne zaman dışında bir düzey 1 uyarı üretir:
  
-   İşlev /Od veya /Ob0 kullanarak derlenir. Hayır satır içi kullanım bu gibi durumlarda beklenir.     
  
-   İşlevi harici olarak bulunan bir kitaplık veya başka bir çeviri birim tanımlı değil veya bir sanal çağrısı hedef ya da dolaylı çağrı hedef. Derleyici geçerli çeviri biriminde bulunamıyor içermesinden olmayan kod tanımlanamıyor.  
  
 Özyinelemeli işlevler tarafından belirtilen bir derinliği değiştirilen satır içi olabilir [inline_depth](../preprocessor/inline-depth.md) en fazla 16 çağrıları pragması. Bu derinlikten sonra yinelenen işlev çağrıları, işlev örneği çağrıları olarak kabul edilir.  Özyinelemeli işlevlerin derinliği 16'yı geçmeyecek şekilde satır içi buluşsal yöntem tarafından incelenir. [İnline_recursion](../preprocessor/inline-recursion.md) pragma genişletme altında şu anda işlev satır içi genişletme denetler. Bkz: [satır içi işlev genişletmesi](../build/reference/ob-inline-function-expansion.md) (/ Ob) ilgili bilgiler için derleyici seçeneği.  
  
**SON Microsoft özel**  
 Kullanma hakkında daha fazla bilgi için **satır içi** belirticisi bakın:  
  
-   [Satır içi sınıfı üye işlevleri](../cpp/inline-functions-cpp.md)  
  
-   [dllexport ve dllimport ile Satır İçi C++ İşlevlerini Tanımlama](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)  
  
## <a name="when-to-use-inline-functions"></a>Satır içi işlevlerin ne zaman kullanılacağı  
 Satır içi işlevler, en çok özel veri üyelerine erişme gibi küçük işlevler için yararlıdır. Bu bir veya iki satırlık "erişimci" işlevlerinin temel amacı, nesneler hakkında durum bilgileri döndürmektir; kısa işlevler işlev çağrılarının ek yüküne karşı duyarlıdır. Daha uzun işlevler, çağırma/döndürme dizisinde nispeten daha az süre harcar ve satır içine alma özelliğinden yararlanır.  
  
 A `Point` sınıfı şu şekilde tanımlanabilir:  
  
```  
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
  
 Koordinat işleme varsayılarak olan bir istemci görece ortak bir işlemde iki erişimci işlevleri belirtme gibi bir sınıf (`x` ve `y` önceki örnekte) olarak **satır içi** genellikle kaydeder ek yükü:  
  
-   İşlev çağrıları (parametre geçirme ve nesnenin adresini yığına yerleştirme dahil)  
  
-   Arayanın yığın çerçevesinin korunması  
  
-   Yeni yığın çerçevesi kurulumu  
  
-   Dönüş değeri iletişimi  
  
-   Eski yığın çerçevesini geri yükleme  
  
-   Döndür  
  
## <a name="inline-functions-vs-macros"></a>Makrolar ve satır içi işlevler  
 Rağmen satır içi işlevler benzerdir makrolar (işlev kodu derleme zamanında çağrısı noktasında genişletildiğinden), satır içi işlevler tarafından Önişlemci makroları genişletilir ancak derleyici tarafından ayrıştırılan. Sonuç olarak, birkaç önemli farklılıklar vardır:  
  
-   Satır içi işlevler normal işlevlerini zorlanan tür güvenliği tüm protokollerin izleyin.  
  
-   Satır içi işlevler içerirler dışında herhangi bir işlev aynı sözdizimini kullanarak belirtilen **satır içi** işlevi bildiriminde anahtar sözcüğü.  
  
-   Satır içi işlevler için bağımsız değişken olarak geçirilen ifade kez değerlendirilir. Bazı durumlarda, makrolar bağımsız değişken olarak geçirilen ifade birden çok kez değerlendirilebilir.  
  
 Aşağıdaki örnek, küçük harfler, büyük harfe dönüştürür makrosu gösterir:  
  
```  
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
  
 İfade amacı `toupper(getc(stdin))` bir karakter konsol aygıttan okuma olduğunu (`stdin`) ve gerekirse, büyük harfe dönüştürülürse.  
  
 Makro uygulanması nedeniyle `getc` karakter büyük olup olmadığını belirlemek için bir kez yürütülmüş ya da "a" ve belirlemek için "z." değerinden küçük veya eşit olup sonra eşit Bu aralıktaki ise `getc` karakter büyük harfe dönüştürülecek yeniden yürütülür. Başka bir deyişle, ideal olarak, yalnızca bir beklemesi gerekir, program için iki veya üç karakter bekler.  
  
 Satır içi işlevler daha önce açıklanan bildirime:  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [noinline](../cpp/noinline.md)   
 [auto_inline](../preprocessor/auto-inline.md)