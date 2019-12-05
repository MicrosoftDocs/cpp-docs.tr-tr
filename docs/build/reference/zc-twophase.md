---
title: /Zc:twoPhase- (iki aşamalı ad aramayı devre dışı bırak)
description: '/Permissive-belirtildiğinde/Zc: Twophao-iki aşamalı ad aramasını devre dışı bırakma açıklanmaktadır.'
ms.date: 12/03/2019
f1_keywords:
- twoPhase
- /Zc:twoPhase
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- twoPhase
- disable two-phase name lookup
- /Zc:twoPhase
ms.openlocfilehash: a2ede9f0875bf718d63361201cf8923666078f7a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856962"
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/Zc:twoPhase- (iki aşamalı ad aramayı devre dışı bırak)

**/Zc: Twophabi-** seçeneği, **/Permissive-** altında, derleyiciye sınıf şablonları ve işlev şablonlarının ayrıştırılmasında ve Örneklendirilecek orijinal C++ , uyumsuz Microsoft derleyicisi davranışını kullanmasını söyler.

## <a name="syntax"></a>Sözdizimi

> **/Zc: Twophatıcı-**

## <a name="remarks"></a>Açıklamalar

Visual Studio 2017 sürüm 15,3 ve üzeri: [/Permissive-](permissive-standards-conformance.md)altında, derleyici şablon adı çözümlemesi için iki aşamalı ad araması kullanır. Ayrıca **/Zc: Twophat-** belirtirseniz, derleyici önceki bir uyumsuz sınıf şablonuna ve işlev şablonu adı çözümleme ve değiştirme davranışına geri döner. **/Permissive-** belirtilmediğinde, uyumlu olmayan davranış varsayılandır.

Sürüm 10.0.15063.0 ' deki Windows SDK üst bilgi dosyaları (Creators Update veya RS2) ve önceki sürümlerde uyumluluk modunda çalışmıyor. **/Zc: Twophao-** **/PERMISSIVE-** kullandığınızda bu SDK sürümleri için kod derlemek gerekir. Sürüm 10.0.15254.0 ile başlayan Windows SDK sürümleri (Fall Creators Update veya RS3) uyumluluk modunda doğru şekilde çalışır. **/Zc: Twophabi-** Option ' a gerek kalmaz.

Kodunuz, eski davranışın doğru bir şekilde derlenmesini gerektiriyorsa **/Zc: Twophat-** kullanın. Kodunuzun standart ile uyumlu olması için güncelleştirmeyi kesin olarak düşünün.

### <a name="compiler-behavior-under-zctwophase-"></a>/ZC altında derleyici davranışı: Twophatıcı-

Varsayılan olarak veya Visual Studio 2017 sürüm 15,3 ' de ve sonraki sürümlerde hem **/Permissive-** hem de **/Zc: twophabi-** belirttiğinizde, derleyici bu davranışı kullanır:

- Yalnızca şablon bildirimini, sınıf kafasını ve temel sınıf listesini ayrıştırır. Şablon gövdesi bir belirteç akışı olarak yakalanır. Hiçbir işlev gövdesi, Başlatıcı, varsayılan bağımsız değişken veya noexcept bağımsız değişkeni ayrıştırılmaz. Sınıf şablonu, sınıf şablonundaki bildirimlerin doğru olduğunu doğrulamak için belirsiz bir tür üzerinde sözde olarak oluşturulur. Bu sınıf şablonunu göz önünde bulundurun:

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   Şablon bildirimi, `template <typename T>`, sınıf Head `class Derived`ve temel sınıf listesi `public Base<T>` ayrıştırılır, ancak şablon gövdesi bir belirteç akışı olarak yakalanır.

- Bir işlev şablonu ayrıştırılırken, derleyici yalnızca işlev imzasını ayrıştırır. İşlev gövdesi hiçbir şekilde ayrıştırılmaz. Bunun yerine, belirteç akışı olarak yakalanır.

Sonuç olarak, şablon gövdesinde sözdizimi hataları varsa, ancak şablon hiçbir şekilde oluşturulamadığında, derleyici hataları tanımaz.

Bu davranışın başka bir etkisi aşırı yükleme çözümüne neden olur. Standart olmayan davranış, belirteç akışının örnekleme sitesinde genişletilme biçimi nedeniyle oluşur. Şablon bildiriminde görünmeyen semboller, örnek oluşturma noktasında görünebilir olabilir. Bu, aşırı yükleme çözümüne katılabilecekleri anlamına gelir. Şablon tanımında görünmeyen ve standart aksine şablonlar değişiklik davranışını fark edebilirsiniz.

Örneğin, aşağıdaki kodu düşünün:

```cpp
// zctwophase.cpp
// To test options, compile by using
// cl /EHsc /nologo /W4 zctwophase.cpp
// cl /EHsc /nologo /W4 /permissive- zctwophase.cpp
// cl /EHsc /nologo /W4 /permissive- /Zc:twoPhase- zctwophase.cpp

#include <cstdio>

void func(long) { std::puts("Standard two-phase") ;}

template<typename T> void g(T x)
{
    func(0);
}

void func(int) { std::puts("Microsoft one-phase"); }

int main()
{
    g(6174);
}
```

**/Zc: Twophabi-** derleyici seçenekleriyle varsayılan modunu, uygunluk modunu ve uyumluluk modunu kullandığınızda bu çıktı şu şekildedir:

```cmd
C:\Temp>cl /EHsc /nologo /W4 zctwophase.cpp && zctwophase
zctwophase.cpp
Microsoft one-phase

C:\Temp>cl /EHsc /nologo /W4 /permissive- zctwophase.cpp && zctwophase
zctwophase.cpp
Standard two-phase

C:\Temp>cl /EHsc /nologo /W4 /permissive- /Zc:twoPhase- zctwophase.cpp && zctwophase
zctwophase.cpp
Microsoft one-phase
```

**/Permissive-** altında uygunluk modunda derlendiğinde, bu program "`Standard two-phase`" yazdırır, çünkü derleyici şablona ulaştığında `func` ikinci aşırı yüklemesi görünür değildir. **/Zc: Twophabi-** eklerseniz, program "`Microsoft one-phase`" yazdırır. Çıktı, **/Permissive-** belirtmemenizi ile aynıdır.

*Bağımlı adlar* , bir şablon parametresine bağlı olan adlardır. Bu adların **/Zc: Twophao-** altında da farklılık gösteren arama davranışı vardır. Uygunluk modunda, bağımlı adlar şablonun tanımının noktasında bağlı değildir. Bunun yerine, derleyici şablonu örnekleyen zaman onları arar. Bağımlı işlev adına sahip işlev çağrıları için, ad, şablon tanımındaki çağrı sitesinde görünen işlevlere bağlıdır. Bağımsız değişkene bağlı arama 'dan ek aşırı yüklemeler, hem şablon tanımının hem de şablon örneklemesinin üzerine eklenir.

İki aşamalı arama iki bölümden oluşur: şablon tanımı sırasında bağımlı olmayan adlara yönelik arama ve şablon örneği oluşturma sırasında bağımlı adlara yönelik arama. **/Zc: Twophasa**' nın altında, derleyici bağımsız değişkene bağlı arama, nitelenmemiş aramalardan ayrı olarak yapmaz. Yani, iki aşamalı arama yapmaz, bu nedenle aşırı yükleme çözümünün sonuçları farklı olabilir.

Bir örnek daha:

```cpp
// zctwophase1.cpp
// To test options, compile by using
// cl /EHsc /W4 zctwophase1.cpp
// cl /EHsc /W4 /permissive- zctwophase1.cpp
// cl /EHsc /W4 /permissive- /Zc:twoPhase- zctwophase1.cpp

#include <cstdio>

void func(long) { std::puts("func(long)"); }

template <typename T> void tfunc(T t) {
    func(t);
}

void func(int) { std::puts("func(int)"); }

namespace NS {
    struct S {};
    void func(S) { std::puts("NS::func(NS::S)"); }
}

int main() {
    tfunc(1729);
    NS::S s;
    tfunc(s);
}
```

**/Permissive-** olmadan derlendiğinde, bu kod şunu yazdırır:

```Output
func(int)
NS::func(NS::S)
```

**/Permissive-** ile derlendiğinde, ancak **/Zc: twophale-** , bu kod şunu yazdırır:

```Output
func(long)
NS::func(NS::S)
```

Hem **/Permissive-** hem de **/Zc: twophade**ile derlendiğinde, bu kod şunu yazdırır:

```Output
func(int)
NS::func(NS::S)
```

Uyumluluk modu **/Permissive-** altında, çağrı `tfunc(1729)` `void func(long)` aşırı yüklemeye çözümlenir. **/Zc: Twophao-** altında olduğu gibi `void func(int)` aşırı yüküne çözümlenmez. Bunun nedeni, nitelenmemiş `func(int)` şablonun tanımladıktan sonra bildirildiği ve bağımsız değişkene bağlı arama yoluyla bulunamamıştır. `void func(S)`, bağımsız değişkene bağlı aramaya katılır, bu nedenle, şablon işlevinden sonra bildirildiği halde çağrı `tfunc(s)`için aşırı yükleme kümesine eklenir.

### <a name="update-your-code-for-two-phase-conformance"></a>Kodunuzu iki aşamalı uygunluk için güncelleştirin

Derleyicinin daha eski sürümleri, anahtar sözcükler `template` gerektirmez ve standart için C++ gereken her yerde `typename`. Bu anahtar sözcükler, derleyicilerin ilk aşamasında, derleyicilerin bağımlı bir adı nasıl ayrıştıracağını ortadan kaldırmak için bazı konumlarda gereklidir. Örneğin:

`T::Foo<a || b>(c);`

Uygun bir derleyici, `T`kapsamındaki bir değişken olarak `Foo` ayrıştırır, yani bu kod, sol işlenen olarak `T::foo < a` olan bir mantıksal or ifadesi ve sağ işlenen olarak `b > (c)`. `Foo` bir işlev şablonu olarak kullanmak istiyorsanız, bir şablon olduğunu `template` anahtar sözcüğünü ekleyerek belirtmeniz gerekir:

`T::template Foo<a || b>(c);`

Visual Studio 2017 sürüm 15,3 ve üzeri sürümlerde, **/Permissive-** ve **/Zc: twophao-** belirtildiğinde, derleyici `template` anahtar sözcüğü olmadan bu koda izin verir. Yalnızca şablonları sınırlı bir biçimde ayrıştırdığından, kodu bir işlev şablonu `a || b`bağımsız değişkeniyle bir çağrı olarak yorumlar. Yukarıdaki kod, ilk aşamada ayrıştırılmaz. İkinci aşamada, `T::Foo` bir değişken yerine bir şablon olduğunu söylemek için yeterli bağlam vardır. bu nedenle, derleyici anahtar sözcüğünün kullanımını zorlamaz.

Bu davranış, işlev şablonu gövdelerinde, başlatıcılarda, varsayılan bağımsız değişkenlerde ve noexcept bağımsız değişkenlerinde adlardan önce `typename` anahtar sözcüğü ortadan kaldırarak da görülebilir. Örneğin:

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

İşlev gövdesinde `typename` anahtar sözcüğünü kullanmıyorsanız, bu kod **/Permissive-/Zc: Twophaken-** altında derlenir, ancak tek başına **/Permissive-** altında değildir. `TYPE` bağımlı olduğunu göstermek için `typename` anahtar sözcüğü gereklidir. Gövde **/Zc: Twophabi-** altında ayrıştırılmadığından, derleyici anahtar sözcüğü gerektirmez. **/Permissive-** uygunluk modunda, `typename` anahtar sözcüğü olmayan kod hata oluşturur. Kodunuzu Visual Studio 2017 sürüm 15,3 ve üzerinde uygunluk 'e geçirmek için, eksik olan `typename` anahtar sözcüğünü ekleyin.

Benzer şekilde, şu kod örneğini göz önünde bulundurun:

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

**/Permissive-/Zc: twoPhase** ' nin altında ve eski derleyicilerde, derleyici yalnızca 2. satırda `template` anahtar sözcüğünü gerektirir. Uyumluluk modunda, derleyici artık `T::X<T>` bir şablon olduğunu göstermek için 4. satırda `template` anahtar sözcüğünü de gerektirir. Bu anahtar sözcüğü eksik kodu arayın ve kodunuzu standart ile uyumlu hale getirmek için sağlayın.

Uyumluluk sorunları hakkında daha fazla bilgi için bkz [ C++ . Visual Studio 'da uyumluluk geliştirmeleri](../../overview/cpp-conformance-improvements.md) ve [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /**  > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: twophat** öğesini içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
