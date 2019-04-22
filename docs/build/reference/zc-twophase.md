---
title: /ZC:twoPhase-(iki aşamalı ad aramayı devre dışı bırak)
ms.date: 03/06/2018
f1_keywords:
- twoPhase
- /Zc:twoPhase
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- twoPhase
- disable two-phase name lookup
- /Zc:twoPhase
ms.openlocfilehash: 5f990181fd1e606cf9d7dd33242752bed33aa456
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58898758"
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/ZC:twoPhase-(iki aşamalı ad aramayı devre dışı bırak)

Zaman **/Zc:twoPhase-** seçeneği belirtildiğinde, derleyici ayrıştırır ve sınıf şablonları hem işlev şablonlarına sürümleri Visual Studio'da daha önce Visual Studio 2017 sürüm 15.3 DSCP aynı şekilde oluşturur.

## <a name="syntax"></a>Sözdizimi

> **/Zc:twoPhase-**

## <a name="remarks"></a>Açıklamalar

Visual Studio 2017 sürüm 15.3 ve daha sonra varsayılan olarak, derleyici şablon ad çözümlemesi için iki aşamalı ad aramayı kullanır. Varsa **/Zc:twoPhase-** belirtilirse, derleyici önceki DSCP sınıf şablonu ve işlev şablonu adı çözümlemesi ve değiştirme davranışını geri döner.

**/Zc:twoPhase-** DSCP davranışı etkinleştirmek için seçeneği varsayılan olarak ayarlı değil. [/ Permissive-](permissive-standards-conformance.md) seçeneği uyumlu iki aşamalı arama derleyici davranışı örtük olarak ayarlar, ancak kullanarak kılınabilir **/Zc:twoPhase-**.

Sürüm 10.0.15063.0 (Creators Update veya Redstone 2) ve önceki sürümlerinde Windows SDK'sı üst bilgi dosyaları uyumluluk modu düzgün çalışmaz. Kullanmalısınız **/Zc:twoPhase-** Visual Studio 2017 sürüm 15.3 ve üzeri sürümleri kullandığınızda bu SDK sürümleri için Kodu derlemek için. Sürümleri 10.0.15254.0 (Redstone 3 veya Fall Creators Update) sürümünden itibaren Windows SDK'ın doğru uyumluluk modunda çalışması ve gerekli olmayan **/Zc:twoPhase-** seçeneği.

Kullanım **/Zc:twoPhase-** kodunuzun doğru şekilde derlenmesi için eski davranışı gerekiyorsa. Kesinlikle standarda için kodunuzu güncelleştirmeyi deneyin.

### <a name="compiler-behavior-under-zctwophase-"></a>Derleyici davranışı /Zc:twoPhase-altında

Visual Studio 2017 sürüm 15.3, önce derleyici sürümlerinde ve ne zaman **/Zc:twoPhase-** belirtilirse, derleyici bu davranışı kullanır:

- Bu, yalnızca şablon bildirimi, sınıf baş ve temel sınıf listesi ayrıştırır. Şablon gövdesi bir belirteç akışı yakalanır. Hiçbir işlev gövdeleri, başlatıcılar, varsayılan bağımsız değişkenler veya noexcept bağımsız değişkenleri ayrıştırılır. Sınıf şablonu bildirimlerinde doğru olduğunu doğrulamak için bir belirsiz türde sözde örneği sınıf şablonudur. Bu sınıf şablonu göz önünde bulundurun:

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   Şablon bildirimi `template <typename T`>, sınıf baş `class Derived`ve temel sınıf listesi `public Base<T>` Ayrıştırılan, ancak şablon gövdesi bir belirteç akışı yakalanır.

- Bir işlev şablonu ayrıştırırken, derleyici işlev imzası ayrıştırır. İşlev gövdesi hiçbir zaman ayrıştırılır. Bunun yerine, bir belirteç akışı yakalanır.

Sonuç olarak, şablon gövdesinde söz dizimi hataları var. ve şablon hiçbir zaman örneği, hataları asla tanı koydu.

Başka bir bu davranışı, aşırı yükleme çözünürlüğü içinde etkisidir. Belirteç akışı örneklemesinin sitede genişletilir şekli nedeniyle şablon bildirimine görünür olmayan simgeler örnek oluşturma noktasında görülebilir ve aşırı yükleme çözünürlüğüne. Bu şablon, standart aykırı tanımlandığında, görünür olmayan kod dayalı davranışı değiştirmek şablonları neden olabilir.

Örneğin, aşağıdaki kodu düşünün:

```cpp
#include <cstdio>

void func(void*) { std::puts("The call resolves to void*") ;}

template<typename T> void g(T x)
{
    func(0);
}

void func(int) { std::puts("The call resolves to int"); }

int main()
{
    g(3.14);
}
```

Altında derlendiğinde **/Zc:twoPhase-**, bu program "çağrısı int çözümler" yazdırır. Uyumluluk modunda altında **/ permissive-**, ikinci aşırı yükleme çünkü bu program "çağrısı çözümler void *", yazdırır `func` derleyici şablon karşılaştığında görünür değil.

*Bağımlı adlar*, bir şablon parametresine bağımlı adlara sahip altında da farklıdır, arama davranışı **/Zc:twoPhase-**. Uyumluluk modunda, bağımlı adlar şablonun tanım noktasında bağlı değil. Şablon örneği başlatıldığında bunun yerine, bu adlar aranır. Bağımlı işlev adı ile işlev çağrıları için yukarıdaki gibi şablonun tanımındaki çağrısı noktasında görünür olan işlevleri kümesi adı bağlıdır. Bağımsız değişkene bağlı arama gelen ek aşırı yüklemeler, hem şablon tanımının noktası hem de Burada şablon örneği nokta eklenir. İki aşamalı arama iki aşamaları şablon tanımı ve arama şablonu örneklemesi zaman zaman bağımlı adlara yönelik bağımlı olmayan adları için arama altındadır. Altında **/Zc:twoPhase-**, derleyici bağımsız değişkene bağlı arama sıradan, nitelenmemiş aramasından ayrı olarak yapmaz (diğer bir deyişle, iki aşamalı arama bunu değil), aşırı yükleme çözünürlüğü sonuçlarını farklı olabilir.

Başka bir örnek aşağıda verilmiştir:

```cpp
// zctwophase1.cpp
// Compile by using
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

Olmadan derlendiğinde **/Zc:twoPhase-**, bu yazdırır

```Output
func(long)
NS::func(NS::S)
```

İle derlendiğinde **/Zc:twoPhase-**, bu yazdırır

```Output
func(int)
NS::func(NS::S)
```

Uyumluluk modunda altında **/ permissive-**, çağrı `tfunc(1729)` çözümler `void func(long)` aşırı değil `void func(int)` olarak altında aşırı **/Zc:twoPhase-**, çünkü nitelenmemiş `func(int)` şablon tanımı sonra bildirilen ve bağımsız değişkene bağlı arama ile bulunamadı. Ancak `void func(S)` görüşmesi için aşırı yükleme eklenir bu nedenle bağımsız değişkene bağlı arama içinde yer almaz `tfunc(s)` sonra şablon işlevi bildirilmiş olsa bile.

### <a name="update-your-code-for-two-phase-conformance"></a>İki aşamalı uyumluluğu için kodunuzu güncelleştirin

Eski sürümleri derleyicinin anahtar sözcükleri gerektirmez `template` ve `typename` her yerde C++ standardı, bunları gerektirir. Bu anahtar sözcükler, derleyiciler arama ilk aşaması sırasında bağımlı adı nasıl çözümlenmelidir ayırt etmek için bazı konumları gereklidir. Örneğin:

`T::Foo<a || b>(c);`

Uyumlu bir derleyici ayrıştırır `Foo` kapsam içinde bir değişken olarak `T`, bu kod anlamına gelir mantıksal- veya ifadesiyle `T::foo < a` sol işlenen olarak ve `b > (c)` sağ işlenen olarak. Kullanmak istediyseniz `Foo` bir işlev şablonu bunun bir şablon ekleyerek olduğunu belirtmelidir `template` anahtar sözcüğü:

`T::template Foo<a || b>(c);`

Visual Studio 2017 sürüm 15.3,'dan önceki sürümlerde ve ne zaman **/Zc:twoPhase-** belirtilirse, derleyici Bu kod olmadan sağlayan `template` anahtar sözcüğü ve bağımsızbirişlevşablonuiçinbirçağrıolarakyorumlar`a || b`, şablonları çok sınırlı bir biçimde ayrıştırır. Yukarıdaki kod, tüm Birinci aşamada Ayrıştırılan değil. İkinci aşamasında, bildirmek için yeterli bağlam yoktur `T::Foo` derleyicinin anahtar sözcüğünün kullanılmasını zorunlu kılmaz bir değişkeni yerine bir şablonu olduğundan.

Bu davranış anahtar sözcüğü ortadan kaldırarak ayrıca görülebilir `typename` işlev şablonu gövdeleri, başlatıcılar, varsayılan bağımsız değişkenler ve noexcept bağımsız değişken adları önce. Örneğin:

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

Anahtar sözcüğünü kullanmıyorsanız `typename` altında bu kod işlev gövdesinde derler **/Zc:twoPhase-**, ancak altında olmayan **/ permissive-**. `typename` Göstermek için anahtar sözcüğü gereklidir `TYPE` bağlıdır. Gövde altında ayrıştırılmayacak çünkü **/Zc:twoPhase-**, derleyici olan anahtar sözcüğü gerektirir. İçinde **/ permissive-** uyumluluğu modu, kod olmadan `typename` anahtar sözcüğü hatalar oluşturur. Visual Studio 2017 sürüm 15.3 kodunuzu geçirme ve güncelleştirmesinden eklemek için `typename` eksik olduğu anahtar sözcüğü.

Benzer şekilde, bu kod örneği göz önünde bulundurun:

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

Altında **/Zc:twoPhase-** ve eski derleyicilerde Derleyici yalnızca gerektirir `template` satır 2 anahtar sözcüğü. Varsayılan olarak uyumluluk modunda, derleyici artık da gerektirir ve `template` göstermek için 4. satırı şuna anahtar sözcüğü `T::X<T>` bir şablondur. Bu anahtar sözcük eksik olan kodunu arayın ve kodunuzu standardına uygun hale getirmek için sağlayın.

Uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Visual Studio'da C++ uyumluluk geliştirmeleri](../../overview/cpp-conformance-improvements.md) ve [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zc:twoPhase-** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
