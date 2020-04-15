---
title: Satır İçi İşlevler (C++)
ms.date: 10/09/2018
f1_keywords:
- __forceinline_cpp
- __inline_cpp
- inline_cpp
- __inline
- _inline
- __forceinline
- _forceinline
helpviewer_keywords:
- inline functions [C++], class members
ms.assetid: 355f120c-2847-4608-ac04-8dda18ffe10c
ms.openlocfilehash: 703c04873a733d068da025b595909ecc681ff147
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374083"
---
# <a name="inline-functions-c"></a>Satır İçi İşlevler (C++)

Sınıf bildirimi gövdesinde tanımlanan bir işlev, satır içi işlevdir.

## <a name="example"></a>Örnek

Aşağıdaki sınıf bildiriminde, `Account` oluşturucu bir satır dışı işlevdir. Üye `GetBalance`işlevler `Deposit`, `Withdraw` , ve **satır olarak** belirtilmez, ancak satır içinde işlevler olarak uygulanabilir.

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
> Sınıf bildiriminde, işlevler satır **içinde** anahtar sözcük olmadan bildirildi. **Satır daki** anahtar kelime sınıf bildiriminde belirtilebilir; sonuç aynıdır.

Belirli bir satır içi üye işlevi, her derleme biriminde aynı şekilde bildirilmelidir. Bu kısıtlama, satır içi işlevlerin örneği oluşturulmuş işlevler gibi davranmasına neden olur. Ayrıca, satır içi işlevinin yalnızca tek bir tanımı olmalıdır.

Bir sınıf üye işlevi, bu işlevin tanımı satır **içinde** belirtici içermediği sürece dış bağlantıya varsayılan olarak değişir. Önceki örnek, bu işlevlerin **satır içinde** belirteçle açıkça beyan edilmesi gerekmediğini gösterir; işlev tanımında **satır içinde** kullanılması, bir satır içinde işlev olmasına neden olur. Ancak, bu işleviçin bir çağrıdan sonra **satır içinde** bir işlev olarak yeniden bildirmek yasa dışıdır.

## <a name="inline-__inline-and-__forceinline"></a>Satır İçi, \___inline ve _forceinline

**Satır ve** **__inline** belirteci, derleyiciye işlev gövdesinin bir kopyasını işlevin çağrıldığı her yere eklemesini bildirir.

Ekleme (satır içi genişletme veya satır için yerleştirme denir) yalnızca derleyicinin maliyet/kar analizinin karlı olacağını gösterdiği durumlarda oluşur. Satır içi genişletme, daha büyük boyuttaki kodun olası maliyetinde işlev-çağrı ek yükünü azaltır.

**anahtar kelime__forceinline** maliyet/fayda çözümlemesi geçersiz kılar ve bunun yerine programcının kararına dayanır. **__forceinline**kullanırken dikkatli olun. **__forceinline** gelişigüzel kullanımı, yalnızca marjinal performans kazançlarıyla veya bazı durumlarda performans kayıplarıyla (örneğin, daha büyük bir yürütülebilir inanCa yönelik daha yüksek çağrılama nedeniyle) daha büyük kodlara neden olabilir.

Satır içi işlevleri kullanmak, işlev çağrıları ile ilgili ek yükü ortadan kaldırdığı için programınızı daha hızlı yapabilir. Satır içi olarak genişletilen işlevler için, normal işlevlerde kullanılamayan kod iyileştirmeleri yapılır.

Derleyici, satır içi genişleme seçeneklerine ve anahtar sözcüklerine öneri olarak davranır. İşlevlerin satır içi olacağına dair bir garanti yoktur. Derleyiciyi, **__forceinline** anahtar sözcüğüyle bile belirli bir işlevi satır lı olarak vermeye zorlayamazsınız. **/clr**ile derleme yaparken, işleve uygulanan güvenlik öznitelikleri varsa derleyici bir işlevi satır satırlamaz.

**Satır adı** anahtar kelimesi yalnızca C++'da kullanılabilir. **__inline** ve **__forceinline** anahtar kelimeler hem C hem de C++'da mevcuttur. Önceki sürümlerle uyumluluk için **_inline** ve **_forceinline** **__inline**eş anlamlıdır ve derleyici seçeneği [/Za \(Dil uzantılarını devre dışı kılmıyorsa __forceinline)](../build/reference/za-ze-disable-language-extensions.md) ile eş anlamlıdır. **__forceinline**

**Satır adı** anahtar kelimesi derleyiciye satır içinde genişletmenin tercih edilir olduğunu söyler. Ancak, derleyici işlevin ayrı bir örneğini oluşturabilir (örneklediğinizde) ve satır içi kod eklemek yerine standart arama bağlantıları oluşturur. Buna izin veren iki durum vardır:

- Özyinelemeli işlevler.

- Çeviri birimi içinde başka bir yerdeki işaretçi üzerinden başvurulan işlevler.

Bu nedenler, *diğerleri gibi,* derleyicinin takdirine bağlı olarak, inlining engelleyebilir; bir işlevin satır lı olması için **satır içinde** belirticiye bağlı olmamalıdır.

Normal işlevlerde olduğu gibi, satır içi işlevler için bağımsız değişkenlerin değerlendirilmesinde belirlenmiş bir sıra yoktur. Aslında, bağımsız değişkenlerin normal işlev çağrısı protokolü kullanılarak geçirildiği durumların değerlendirilmesindeki sıralamadan farklı olabilir.

[/Ob](../build/reference/ob-inline-function-expansion.md) derleyici optimizasyonu seçeneği, satır satır lı işlev genişletmenin gerçekten gerçekleşip oluşmadığını belirlemeye yardımcı olur.

[/LTCG,](../build/reference/ltcg-link-time-code-generation.md) kaynak kodunda istenip istenmediğine bakılmaksızın çapraz modül inlining gerçekleştirir.

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

Bir sınıfın üye işlevleri **satır içi** anahtar sözcüğü kullanılarak veya işlev tanımını sınıf tanımına yerleştirerek satır içi olarak bildirilebilir.

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

**Microsoft'a Özgü**

**__inline** anahtar kelime **satır içinde**eşdeğerdir.

**__forceinline**bile, derleyici her koşulda satır satır olamaz. Derleyici, şu durumlarda bir işlevi satır içi yapamaz:

- İşlev veya çağıranı /Ob0 (hata ayıklama için varsayılan seçenek) ile derlenir.

- İşlev ve çağıran farklı türde özel durum işlemelerini kullanır (birinde C++ özel durum işlemesi, diğerinde yapı özel durum işlemesi).

- İşlevin değişken bağımsız değişken listesi vardır.

- İşlev; satır içi derlemeyi, /Og, /Ox, /O1 veya /O2 ile derlenmediği sürece kullanır.

- İşlev özyinelemelidir ve **#pragma inline_recursion (on)** ile birlikte değildir. Pragma ile özyinelemeli işlevler varsayılan 16 aramalı derinliğe kadar satır içi yapılırlar. Kaplama derinliğini azaltmak için [inline_depth](../preprocessor/inline-depth.md) pragma kullanın.

- İşlev sanaldır ve sanal olarak çağrılır. Sanal işlevlere doğrudan çağrılar satır içi yapılabilir.

- Program işlevin adresini alır ve çağrı işlev işaretçisi aracılığıyla yapılır. Adresleri alınmış olan doğrudan işlev çağrıları satır içi yapılabilir.

- Fonksiyon da [çıplak](../cpp/naked-cpp.md) [__declspec](../cpp/declspec.md) değiştirici ile işaretlenir.

Derleyici **__forceinline**ile bildirilen bir işlevi satır satıra alamıyorsa, aşağıdaki durumlar dışında düzey 1 uyarısı oluşturur:

- Fonksiyon /Od veya /Ob0 kullanılarak derlenir. Bu gibi durumlarda herhangi bir inlining beklenir.

- İşlev harici olarak, dahil edilmiş bir kitaplıkta veya başka bir çeviri biriminde tanımlanır veya sanal bir arama hedefi veya dolaylı çağrı hedefidir. Derleyici, geçerli çeviri biriminde bulamadığı astarsız kodu tanımlamıyor.

Özyinelemeli işlevler, [inline_depth](../preprocessor/inline-depth.md) pragma tarafından en fazla 16 çağrıya kadar belirtilen bir derinliğe satır satır değiştirilebilir. Bu derinlikten sonra yinelenen işlev çağrıları, işlev örneği çağrıları olarak kabul edilir.  Özyinelemeli işlevlerin derinliği 16'yı geçmeyecek şekilde satır içi buluşsal yöntem tarafından incelenir. [inline_recursion](../preprocessor/inline-recursion.md) pragma şu anda genişletme altında bir işlevin satır satırgenişletme denetler. İlgili bilgiler için [Satır İçi İşlev Genişletme](../build/reference/ob-inline-function-expansion.md) (/Ob) derleyicisi seçeneğine bakın.

**END Microsoft Özel**

**Satır altı** belirticinin kullanımı hakkında daha fazla bilgi için bkz:

- [Satır Satırlı Sınıf Üye Fonksiyonları](../cpp/inline-functions-cpp.md)

- [dllexport ve dllimport ile Satır İçin C++ İşlevlerini Tanımlama](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

## <a name="when-to-use-inline-functions"></a>Satır dışı işlevler ne zaman kullanılır?

Satır içi işlevler, en çok özel veri üyelerine erişme gibi küçük işlevler için yararlıdır. Bu bir veya iki satırlık "erişimci" işlevlerinin temel amacı, nesneler hakkında durum bilgileri döndürmektir; kısa işlevler işlev çağrılarının ek yüküne karşı duyarlıdır. Daha uzun işlevler, çağırma/döndürme dizisinde nispeten daha az süre harcar ve satır içine alma özelliğinden yararlanır.

Bir `Point` sınıf aşağıdaki gibi tanımlanabilir:

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

Koordinat işlemesinin böyle bir sınıfın istemcisinde nispeten yaygın bir işlem olduğunu varsayarsak, **satır altı** genellikle genel yükü kaydeder gibi iki erişimci işlevi (ve`x` `y` önceki örnekte) belirterek:

- İşlev çağrıları (parametre geçirme ve nesnenin adresini yığına yerleştirme dahil)

- Arayanın yığın çerçevesinin korunması

- Yeni yığın çerçevesi kurulumu

- Dönüş değeri iletişimi

- Eski yığın çerçevesini geri yükleme

- Dönüş

## <a name="inline-functions-vs-macros"></a>Satır satır işlevleri ve makrolar

Satır ara işlevleri makrolara benzer olsa da (işlev kodu derleme zamanında çağrı noktasında genişletildiğinden), satır ara işlevleri derleyici tarafından ayrıştırılır, makrolar ise önişlemci tarafından genişletilir. Sonuç olarak, birkaç önemli fark vardır:

- Satır lı işlevler, normal işlevler üzerinde uygulanan tür güvenliği protokollerini izler.

- Satır İçi işlevler, işlev bildirimine **satır satır** anahtar sözcüğü eklemeleri dışında, diğer işlevler ile aynı sözdizimi kullanılarak belirtilir.

- Satır ara işlevlerine bağımsız değişken olarak geçirilen ifadeler bir kez değerlendirilir. Bazı durumlarda, makrolara bağımsız değişken olarak geçirilen ifadeler birden çok kez değerlendirilebilir.

Aşağıdaki örnekte, küçük harfleri büyük harfe dönüştüren bir makro gösterilmektedir:

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

İfadenin `toupper(getc(stdin))` amacı, bir karakterin konsol aygıtından okunması`stdin`ve gerekirse büyük harfe dönüştürülmesidir.

Makronun uygulanması nedeniyle, `getc` karakterin "a"dan büyük mü yoksa eşit mi olduğunu belirlemek için bir kez ve "z"den daha az mı yoksa eşit mi olduğunu belirlemek için bir kez yürütülür. Bu aralıkta ise, `getc` karakteri büyük harfe dönüştürmek için yeniden yürütülür. Bu, programın ideal olarak yalnızca bir karakter beklemesi gerektiğinde iki veya üç karakter beklediği anlamına gelir.

Satır satır işlevleri daha önce açıklanan sorunu gidermek:

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

[noinline](../cpp/noinline.md)<br/>
[auto_inline](../preprocessor/auto-inline.md)
