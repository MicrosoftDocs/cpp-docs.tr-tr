---
title: Satır İçi İşlevler (C++)
description: C++ satır içi işlevlerini derleyiciye önermek için C++ satır içi anahtar sözcüğü kullanılabilir.
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
ms.openlocfilehash: 454a727f0c002dc476e5fdab217efc3dea716e14
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180715"
---
# <a name="inline-functions-c"></a>Satır İçi İşlevler (C++)

Sınıf bildirimi gövdesinde tanımlanan bir işlev, satır içi işlevdir.

## <a name="example"></a>Örnek

Aşağıdaki sınıf bildiriminde, `Account` Oluşturucu bir satır içi işlevdir. Üye işlevleri, `GetBalance` `Deposit` ve `Withdraw` olarak belirtilmez **`inline`** ancak satır içi işlevler olarak uygulanabilir.

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
> Sınıf bildiriminde işlevler **`inline`** anahtar sözcük olmadan bildirilmiştir. **`inline`** Anahtar sözcüğü, sınıf bildiriminde belirtilebilir; sonuç aynıdır.

Belirli bir satır içi üye işlevi, her derleme biriminde aynı şekilde bildirilmelidir. Bu kısıtlama, satır içi işlevlerin örneği oluşturulmuş işlevler gibi davranmasına neden olur. Ayrıca, satır içi işlevinin yalnızca tek bir tanımı olmalıdır.

Bir sınıf üyesi işlevi, bu işlevin tanımı tanımlayıcı içermiyorsa, varsayılan olarak harici bağlantı olur **`inline`** . Yukarıdaki örnek, bu işlevleri tanımlayıcı ile açıkça bildirmeniz gerektiğini gösterir **`inline`** . **`inline`** İşlev tanımında kullanmak bunun satır içi bir işlev olmasına neden olur. Ancak, bu işleve yapılan çağrıdan sonra bir işlevi yeniden bildirmeye izin verilmez **`inline`** .

## <a name="inline-__inline-and-__forceinline"></a>`inline`, `__inline` ve`__forceinline`

**`inline`** Ve **`__inline`** belirticileri, derleyicinin işlevin çağrıldığı her yere işlev gövdesinin bir kopyasını eklemesini ister.

*Satır içi genişletme veya satır içi* olarak adlandırılan *ekleme, yalnızca*derleyicinin maliyet avantajı analizinin kullanım dışı olduğunu gösteriyorsa oluşur. Satır içi genişletme, işlev çağrısı yükünü, büyük kod boyutunun olası maliyetinden en aza indirir.

**`__forceinline`** Anahtar sözcüğü, maliyet avantajı analizini geçersiz kılar ve bunun yerine programcının kararına dayanır. Kullanırken dikkatli olun **`__forceinline`** . Ayrım gözetilmeden erişilemez kullanımı, **`__forceinline`** yalnızca marguinal performans kazançları veya bazı durumlarda (örneğin, daha büyük bir yürütülebilir dosya disk belleği arttığı için) bile daha büyük koda neden olabilir.

Satır içi işlevleri kullanmak, işlev çağrıları ile ilgili ek yükü ortadan kaldırdığı için programınızı daha hızlı yapabilir. Satır içi olarak genişletilen işlevler için, normal işlevlerde kullanılamayan kod iyileştirmeleri yapılır.

Derleyici, satır içi genişleme seçeneklerine ve anahtar sözcüklerine öneri olarak davranır. İşlevlerin satır içine alınır garantisi yoktur. Derleyiciye, anahtar sözcüğüyle bile belirli bir işlevi satır içi olarak zorlayamaz **`__forceinline`** . İle derleme yaparken **`/clr`** , işleve uygulanan güvenlik öznitelikleri varsa derleyici bir işlevi satır içine alınmaz.

**`inline`** Anahtar sözcüğü yalnızca C++ ' da kullanılabilir. **`__inline`** Ve **`__forceinline`** anahtar sözcükleri hem C hem de C++ ' da kullanılabilir. Önceki sürümlerle uyumluluk için **`_inline`** ve **`_forceinline`** için eş anlamlılardır ve **`__inline`** **`__forceinline`** derleyici seçeneği [ `/Za` \( devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) ' ı belirtilmediyse) belirtilir.

**`inline`** Anahtar sözcüğü derleyiciye satır içi genişletmenin tercih edildiğini söyler. Ancak, derleyici işlevin ayrı bir örneğini oluşturabilir (örneklediğinizde) ve satır içi kod eklemek yerine standart arama bağlantıları oluşturur. Bu davranışın gerçekleşebileceği iki durum vardır:

- Özyinelemeli işlevler.

- Çeviri birimi içinde başka bir yerdeki işaretçi üzerinden başvurulan işlevler.

Bu nedenlerden bazıları, derleyicide *olduğu gibi, diğer*bir deyişle derleyicinin da kesintiye uğratabileceği için **`inline`** bir işlevin satır içine alınmasına neden olacak şekilde belirticiye dayanmamanız gerekir.

Normal işlevlerde olduğu gibi, bir satır içi işlevde bağımsız değişken değerlendirmesi için tanımlı bir sıra yoktur. Aslında, normal işlev çağrısı protokolü kullanılarak geçirildiğinde bağımsız değişken değerlendirme siparişinden farklı olabilir.

[`/Ob`](../build/reference/ob-inline-function-expansion.md)Derleyici iyileştirme seçeneği, satır içi işlev genişletmesinin gerçekten oluşup oluşmadığını belirlemenize yardımcı olur.

[`/LTCG`](../build/reference/ltcg-link-time-code-generation.md)Kaynak kodda istenip istenmediğini çapraz modülle alır.

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

Bir sınıfın üye işlevleri, **`inline`** anahtar sözcüğü kullanılarak veya işlev tanımı sınıf tanımı içine yerleştirerek satır içi olarak bildirilemez.

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

**Microsoft'a özgü**

**`__inline`** Anahtar sözcüğü ile eşdeğerdir **`inline`** .

İçinde bile **`__forceinline`** derleyici, her durumda satır içi kod içeremez. Derleyici, şu durumlarda bir işlevi satır içi olarak görüntüleyemez:

- İşlevi veya çağıranı ile derlenir **`/Ob0`** (hata ayıklama derlemeleri için varsayılan seçenek).

- İşlev ve çağıran farklı türde özel durum işlemelerini kullanır (birinde C++ özel durum işlemesi, diğerinde yapı özel durum işlemesi).

- İşlevin değişken bağımsız değişken listesi vardır.

- İşlevi, veya ile derlenmediği takdirde satır içi derleme kullanır **`/Ox`** **`/O1`** **`/O2`** .

- İşlev özyinelemeli ve **`#pragma inline_recursion(on)`** ayarlanmamış. Pragma ile özyinelemeli işlevler varsayılan 16 aramalı derinliğe kadar satır içi yapılırlar. Satır içi derinliği azaltmak için [`inline_depth`](../preprocessor/inline-depth.md) pragma kullanın.

- İşlev sanaldır ve sanal olarak çağrılır. Sanal işlevlere doğrudan çağrılar satır içi yapılabilir.

- Program işlevin adresini alır ve çağrı işlev işaretçisi aracılığıyla yapılır. Adresleri alınmış olan doğrudan işlev çağrıları satır içi yapılabilir.

- İşlev [`naked`](../cpp/naked-cpp.md) [`__declspec`](../cpp/declspec.md) değiştiriciyle de işaretlenir.

Derleyicinin ile belirtilen bir işlevi satır içine alıyorsa **`__forceinline`** , şunlar dışında bir düzey 1 uyarı üretir:

- İşlev/od veya/Ob0kullanılarak derlenir. Bu durumlarda hiçbir satır beklenmez.

- İşlev, eklenen bir kitaplıkta veya başka bir çeviri biriminde dışarıdan veya bir sanal çağrı hedefi veya dolaylı çağrı hedefi olarak tanımlanır. Derleyici, geçerli çeviri biriminde bulamadığı satır içine alınmamış kodu tanımlayamıyor.

Özyinelemeli işlevler [`inline_depth`](../preprocessor/inline-depth.md) , en fazla 16 çağrıya kadar, pragma tarafından belirtilen bir derinliğe satır içi kod ile değiştirilebilir. Bu derinlikten sonra yinelenen işlev çağrıları, işlev örneği çağrıları olarak kabul edilir.  Özyinelemeli işlevlerin satır içi buluşsal yöntem tarafından İncelenme derinliği 16 ' yı aşamaz. [`inline_recursion`](../preprocessor/inline-recursion.md)Pragma, şu anda genişlemekte olan bir işlevin satır içi genişletmesini denetler. İlgili bilgiler için bkz. [satır Içi Işlev genişletme](../build/reference/ob-inline-function-expansion.md) (/OB) derleyici seçeneği.

**SON Microsoft 'a özgü**

**Satır içi** belirtici kullanma hakkında daha fazla bilgi için bkz.:

- [Satır içi sınıf üye Işlevleri](../cpp/inline-functions-cpp.md)

- [Dllexport ve dllimport ile satır Içi C++ Işlevlerini tanımlama](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

## <a name="when-to-use-inline-functions"></a>Satır içi işlevlerin ne zaman kullanılacağı

Satır içi işlevler, en çok özel veri üyelerine erişme gibi küçük işlevler için yararlıdır. Bu tek veya iki satırlık "erişimci" işlevlerinin ana amacı nesneler hakkında durum bilgilerini döndürmemektedir. Kısa işlevler, işlev çağrılarının ek yüküne duyarlıdır. Daha uzun işlevler, çağırma ve döndürme sırasında daha az zaman harcamaz ve satır içi avantajdan daha az faydalanır.

Bir `Point` sınıf aşağıdaki şekilde tanımlanabilir:

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

Koordinat işleme, böyle bir sınıfın istemcisinde görece ortak bir işlem olduğu varsayılırsa, iki erişimci işlevini ( `x` ve `y` Önceki örnekte) belirtmek için genellikle yükü şu şekilde **`inline`** kaydeder:

- İşlev çağrıları (parametre geçirme ve nesnenin adresini yığına yerleştirme dahil)

- Arayanın yığın çerçevesinin korunması

- Yeni yığın çerçevesi kurulumu

- Dönüş değeri iletişimi

- Eski yığın çerçevesini geri yükleme

- Döndürülmesini

## <a name="inline-functions-vs-macros"></a>Satır içi işlevler ile makrolar

İşlev kodu, derleme zamanında çağrı noktasında genişletildiğinden, satır içi işlevler makrolara benzerdir. Ancak, satır içi işlevler derleyici tarafından ayrıştırılır ve makrolar Önişlemci tarafından genişletilir. Sonuç olarak, bazı önemli farklılıklar vardır:

- Satır içi işlevler, normal işlevlerde güvenlik zorlandı türündeki tüm protokolleri izler.

- Satır içi işlevler, **`inline`** işlev bildirimine anahtar sözcüğünü dahil ettikleri dışında, başka bir işlevle aynı söz dizimi kullanılarak belirtilir.

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

İfadenin amacı, `toupper(getc(stdin))` konsol aygıtından () bir karakterin okunmalıdır `stdin` ve gerekirse büyük harfe dönüştürülür.

Makronun uygulanması nedeniyle, karakterin "a" değerinden `getc` büyük veya ona eşit olup olmadığını ve bir kez, "z" değerinden küçük veya buna eşit olup olmadığını belirlemekte bir kez yürütülür. Bu aralıkta ise, `getc` karakteri büyük harfe dönüştürmek için yeniden yürütülür. Bu, ideal olarak, programın yalnızca bir tane beklemesi gereken iki veya üç karakter için beklediği anlamına gelir.

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

[`noinline`](../cpp/noinline.md)<br/>
[`auto_inline`](../preprocessor/auto-inline.md)
