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
ms.openlocfilehash: efaaacc46f63ac1a702ab2110d35fe80727ead1d
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857521"
---
# <a name="inline-functions-c"></a>Satır İçi İşlevler (C++)

Sınıf bildirimi gövdesinde tanımlanan bir işlev, satır içi işlevdir.

## <a name="example"></a>Örnek

Aşağıdaki sınıf bildiriminde `Account` Oluşturucu bir satır içi işlevdir. `GetBalance`, `Deposit`ve `Withdraw` üye işlevleri **satır içi** olarak belirtilmez, ancak satır içi işlevler olarak uygulanabilir.

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
>  Sınıf bildiriminde, işlevler **satır içi** anahtar sözcük olmadan bildirilmiştir. **Satır içi** anahtar sözcüğü sınıf bildiriminde belirtilebilir; sonuç aynıdır.

Belirli bir satır içi üye işlevi, her derleme biriminde aynı şekilde bildirilmelidir. Bu kısıtlama, satır içi işlevlerin örneği oluşturulmuş işlevler gibi davranmasına neden olur. Ayrıca, satır içi işlevinin yalnızca tek bir tanımı olmalıdır.

Bir sınıf üyesi işlevi, bu işlevin tanımı **satır içi** belirtici içermediği takdirde, varsayılan olarak harici bağlantı olur. Yukarıdaki örnekte, bu işlevlerin **satır içi** belirticiyle açıkça bildirilmesini gerektiren bir ifade verilmiştir; işlev tanımında **satır içi** kullanılması bunun satır içi bir işlev olmasına neden olur. Ancak, bu işleve yapılan çağrıdan sonra bir işlevi **satır içi** olarak yeniden bildirmek geçersizdir.

## <a name="inline-__inline-and-__forceinline"></a>Satır içi, __inline ve \__forceinline

**Satır içi** ve **__inline** belirticileri, derleyicinin işlevin çağrıldığı her yere işlev gövdesinin bir kopyasını eklemesini ister.

Ekleme (satır içi genişletme veya satır için yerleştirme denir) yalnızca derleyicinin maliyet/kar analizinin karlı olacağını gösterdiği durumlarda oluşur. Satır içi genişletme, daha büyük boyuttaki kodun olası maliyetinde işlev-çağrı ek yükünü azaltır.

**__Forceinline** anahtar sözcüğü, maliyet/avantaj analizini geçersiz kılar ve bunun yerine programcının kararına dayanır. **__Forceinline**kullanırken dikkatli olun. **__Forceinline** ayrım gözetilmeden erişilemez kullanımı, yalnızca marguinal performans kazançları veya bazı durumlarda (örneğin, daha büyük bir yürütülebilir dosyanın disk belleği arttığı için) daha büyük koda neden olabilir.

Satır içi işlevleri kullanmak, işlev çağrıları ile ilgili ek yükü ortadan kaldırdığı için programınızı daha hızlı yapabilir. Satır içi olarak genişletilen işlevler için, normal işlevlerde kullanılamayan kod iyileştirmeleri yapılır.

Derleyici, satır içi genişleme seçeneklerine ve anahtar sözcüklerine öneri olarak davranır. İşlevlerin satır içi olacağına dair bir garanti yoktur. Derleyiciyi, **__forceinline** anahtar sözcüğüyle bile belirli bir işlevi satır içi olarak zorlayamaz. **/Clr**ile derlerken, işlev için uygulanmış güvenlik öznitelikleri varsa derleyici bir işlevi satır içine alınmaz.

**Satır içi** anahtar sözcüğü yalnızca içinde C++kullanılabilir. **__İnline** ve **__forceinline** anahtar sözcükleri hem C hem de ile C++kullanılabilir. Önceki sürümlerle uyumluluk için, **_inline** ve **_forceinline** **__inline**için eş anlamlılardır ve [/za \(dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtilmemişse **__forceinline** .

**Satır içi** anahtar sözcüğü derleyiciye satır içi genişletmenin tercih edildiğini söyler. Ancak, derleyici işlevin ayrı bir örneğini oluşturabilir (örneklediğinizde) ve satır içi kod eklemek yerine standart arama bağlantıları oluşturur. Buna izin veren iki durum vardır:

- Özyinelemeli işlevler.

- Çeviri birimi içinde başka bir yerdeki işaretçi üzerinden başvurulan işlevler.

Bu nedenlerden bazıları, derleyicide *olduğu gibi, diğer*bir deyişle derleyicinin da kesintiye uğratabileceği için bir işlevin satır içine alınmasına neden olmak için **satır içi** belirticiye dayanmamalıdır.

Normal işlevlerde olduğu gibi, satır içi işlevler için bağımsız değişkenlerin değerlendirilmesinde belirlenmiş bir sıra yoktur. Aslında, bağımsız değişkenlerin normal işlev çağrısı protokolü kullanılarak geçirildiği durumların değerlendirilmesindeki sıralamadan farklı olabilir.

[/Ob](../build/reference/ob-inline-function-expansion.md) derleyici iyileştirme seçeneği, satır içi işlev genişletmesinin gerçekten oluşup oluşmadığını belirlemenize yardımcı olur.

[/LTCG](../build/reference/ltcg-link-time-code-generation.md) , kaynak kodunda istenip istenmediğine bakılmaksızın çapraz modüllü satır gerçekleştirir.

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

Bir sınıfın üye işlevleri, **satır** içi anahtar sözcüğü kullanılarak veya işlev tanımı sınıf tanımına yerleştirilerek satır içi olarak bildirilemez.

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

**Microsoft 'a özgü**

**__İnline** anahtar sözcüğü **satır içi**ile eşdeğerdir.

**__Forceinline**olsa da, derleyici tüm koşullarda satır içi kod kullanamaz. Derleyici, şu durumlarda bir işlevi satır içi yapamaz:

- İşlev veya çağıranı /Ob0 (hata ayıklama için varsayılan seçenek) ile derlenir.

- İşlev ve çağıran farklı türde özel durum işlemelerini kullanır (birinde C++ özel durum işlemesi, diğerinde yapı özel durum işlemesi).

- İşlevin değişken bağımsız değişken listesi vardır.

- İşlev; satır içi derlemeyi, /Og, /Ox, /O1 veya /O2 ile derlenmediği sürece kullanır.

- İşlev özyinelemeli ve **#pragma inline_recursion (açık)** tarafından birlikte kullanılamaz. Pragma ile özyinelemeli işlevler varsayılan 16 aramalı derinliğe kadar satır içi yapılırlar. Satır içi derinliği azaltmak için [inline_depth](../preprocessor/inline-depth.md) pragma kullanın.

- İşlev sanaldır ve sanal olarak çağrılır. Sanal işlevlere doğrudan çağrılar satır içi yapılabilir.

- Program işlevin adresini alır ve çağrı işlev işaretçisi aracılığıyla yapılır. Adresleri alınmış olan doğrudan işlev çağrıları satır içi yapılabilir.

- İşlev, [Naked](../cpp/naked-cpp.md) [__declspec](../cpp/declspec.md) değiştiricisi ile de işaretlenir.

Derleyici **__forceinline**ile belirtilen bir işlevi satır içine alamaz, şunlar dışında bir düzey 1 uyarı üretir:

- İşlev/od veya/Ob0kullanılarak derlenir. Bu durumlarda hiçbir satır beklenmez.

- İşlev, eklenen bir kitaplıkta veya başka bir çeviri biriminde dışarıdan veya bir sanal çağrı hedefi veya dolaylı çağrı hedefi olarak tanımlanır. Derleyici, geçerli çeviri biriminde bulamadığı satır içine alınmamış kodu tanımlayamıyor.

Özyinelemeli işlevler, en fazla 16 çağrıya kadar [inline_depth](../preprocessor/inline-depth.md) pragma tarafından belirtilen bir derinliğe göre değiştirilebilir. Bu derinlikten sonra yinelenen işlev çağrıları, işlev örneği çağrıları olarak kabul edilir.  Özyinelemeli işlevlerin derinliği 16'yı geçmeyecek şekilde satır içi buluşsal yöntem tarafından incelenir. [İnline_recursion](../preprocessor/inline-recursion.md) pragma, genişletmekte olan bir işlevin satır içi genişletmesini denetler. İlgili bilgiler için bkz. [satır Içi Işlev genişletme](../build/reference/ob-inline-function-expansion.md) (/OB) derleyici seçeneği.

**SON Microsoft 'a özgü**

**Satır içi** belirtici kullanma hakkında daha fazla bilgi için bkz.:

- [Satır içi sınıf üye Işlevleri](../cpp/inline-functions-cpp.md)

- [dllexport ve dllimport ile Satır İçi C++ İşlevlerini Tanımlama](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

## <a name="when-to-use-inline-functions"></a>Satır içi işlevlerin ne zaman kullanılacağı

Satır içi işlevler, en çok özel veri üyelerine erişme gibi küçük işlevler için yararlıdır. Bu bir veya iki satırlık "erişimci" işlevlerinin temel amacı, nesneler hakkında durum bilgileri döndürmektir; kısa işlevler işlev çağrılarının ek yüküne karşı duyarlıdır. Daha uzun işlevler, çağırma/döndürme dizisinde nispeten daha az süre harcar ve satır içine alma özelliğinden yararlanır.

Bir `Point` sınıfı aşağıdaki gibi tanımlanabilir:

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

Koordinat değiştirmenin bu tür bir sınıfın istemcisinde görece yaygın bir işlem olduğu varsayılırsa, iki erişimci işlevinin (önceki örnekteki`x` ve `y`) **satır içi** olarak belirtilmesi genellikle yükü şu şekilde kaydeder:

- İşlev çağrıları (parametre geçirme ve nesnenin adresini yığına yerleştirme dahil)

- Arayanın yığın çerçevesinin korunması

- Yeni yığın çerçevesi kurulumu

- Dönüş değeri iletişimi

- Eski yığın çerçevesini geri yükleme

- Return

## <a name="inline-functions-vs-macros"></a>Satır içi işlevler ile makrolar

Satır içi işlevler makrolara benzer olsa da (işlev kodu derleme zamanında çağrı noktasında genişletildiğinden), satır içi işlevler derleyici tarafından ayrıştırılır, ancak makrolar Önişlemci tarafından genişletilir. Sonuç olarak, bazı önemli farklılıklar vardır:

- Satır içi işlevler, normal işlevlerde güvenlik zorlandı türündeki tüm protokolleri izler.

- Satır içi işlevler, işlev bildiriminde **satır içi** anahtar sözcüğünü içermeleri dışında diğer işlevlerle aynı söz dizimi kullanılarak belirtilir.

- Satır içi işlevlere bağımsız değişken olarak geçirilen ifadeler bir kez değerlendirilir. Bazı durumlarda, makrolara bağımsız değişken olarak geçirilen ifadeler birden çok kez değerlendirilebilirler.

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

`toupper(getc(stdin))` ifade amacı, bir karakterin konsol aygıtından okunmalıdır (`stdin`) ve gerekirse büyük harfe dönüştürülür.

Makronun uygulanması nedeniyle `getc`, karakterin "a" değerinden büyük veya ona eşit olup olmadığını ve bir kez "z" değerinden küçük veya buna eşit olup olmadığını belirlemekte bir kez yürütülür. Bu aralıkta ise, karakteri büyük harfe dönüştürmek için `getc` yeniden yürütülür. Bu, programın iki veya üç karakter için beklediği anlamına gelir, ideal olarak yalnızca bir tane bekler.

Satır içi işlevler daha önce açıklanan sorunu ortadan kaldırmak:

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