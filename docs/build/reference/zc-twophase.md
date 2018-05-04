---
title: /ZC:twoPhase-(devre dışı bırak iki aşamalı adı arama) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- twoPhase
- /Zc:twoPhase
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- twoPhase
- disable two-phase name lookup
- /Zc:twoPhase
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5653959b25105f10ae98768217524dc0ff0cbe2a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/ZC:twoPhase-(iki aşamalı adı arama devre dışı bırak)

Zaman **/Zc:twoPhase-** seçeneği belirtildiğinde, derleyici ayrıştırır ve Visual Studio 2017 sürüm 15.3 önce Visual Studio sürümleri uyumsuz aynı şekilde sınıf şablonları ve işlev Şablonları'nı başlatır. 

## <a name="syntax"></a>Sözdizimi

> **/ZC:twoPhase-**

## <a name="remarks"></a>Açıklamalar

Visual Studio 2017 içinde sürüm 15.3 ve daha sonra varsayılan olarak, derleyici şablon ad çözümlemesi için iki aşamalı ad araması kullanır. Varsa **/Zc:twoPhase-** belirtilirse, derleyici önceki uyumsuz sınıfı şablonu ve işlev şablon ad çözümlemesi ve değiştirme davranışını geri döner.

**/Zc:twoPhase-** uyumsuz davranışı etkinleştirmek için seçeneği varsayılan olarak ayarlı değil. [/ İzin veren-](permissive-standards-conformance.md) seçeneği uyumlu iki aşamalı arama derleyici davranışı örtük olarak ayarlar, ancak kullanarak kılınabilir **/Zc:twoPhase-**.

Sürüm 10.0.15063.0 (oluşturucuları güncelleştirme ya da Redstone 2) ve önceki sürümlerinde Windows SDK'sı üst bilgi dosyaları uyumluluk modunda düzgün çalışmıyor. Kullanmalısınız **/Zc:twoPhase-** Visual Studio 2017 sürüm 15.3 ve sonraki sürümler kullandığınızda bu SDK sürümleri için Kodu derlemek için. 10.0.15254.0 (Redstone 3 veya sonbaharda oluşturucuları güncelleştirme) sürümünden başlayarak Windows SDK sürümleri uyumluluk modunda düzgün çalışması ve gerektirmez **/Zc:twoPhase-** seçeneği.

Kullanım **/Zc:twoPhase-** kodunuzun doğru şekilde derlenmesi için eski davranışı gerektiriyorsa. Kesinlikle kodunuzu standardına uygun güncelleştirmeyi deneyin.

### <a name="compiler-behavior-under-zctwophase-"></a>Derleyici davranışı /Zc:twoPhase-altında

Visual Studio 2017 sürüm 15.3, önce derleyici sürümlerinde ve ne zaman **/Zc:twoPhase-** belirtilirse, bu davranış derleyici kullanır:

- Yalnızca şablon bildirim, sınıf head ve temel sınıf listesi ayrıştırır. Şablon gövde belirteci bir akış olarak yakalanır. Hiçbir işlev gövdesi, başlatıcılar, varsayılan bağımsız değişkenler veya noexcept bağımsız değişkenleri ayrıştırılır. Sınıf şablonu bildirimlerinde doğru olduğunu doğrulamak için belirsiz bir tür sözde örneği için sınıf şablonudur. Bu sınıf şablonu göz önünde bulundurun:

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   Şablon bildirim `template <typename T`>, sınıf head `class Derived`ve temel sınıf listesi `public Base<T>` Ayrıştırılan, ancak şablon gövde belirteci bir akış olarak yakalanır.

- İşlev şablonu ayrıştırılırken Derleyici yalnızca işlev imzası ayrıştırır. İşlev gövdesi hiçbir zaman ayrıştırılır. Bunun yerine, bir belirteç akış olarak yakalanır.

Sonuç olarak, söz dizimi hataları şablon gövdesi varsa ve şablon hiçbir zaman örneği, hataları hiçbir zaman tanı koydu.

Bu davranış başka bir etkisi aşırı yük çözüm olmasıdır. Belirteç akışı örneklemesi sitede genişletilmiş yöntemi nedeniyle, şablon bildirim sırasında görünür değil sembolleri örneklemesi noktasında görünür ve aşırı yük çözüm katılmak. Bu şablon, standart aykırı tanımlanırken görünür değildi kodu dayalı davranışı değiştirmek şablonları neden olabilir.

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

Altında derlendiğinde **/Zc:twoPhase-**, bu program "çağrısı int'e çözümler" yazdırır. Uyumluluk modunda altında **/ izin veren-**, ikinci aşırı yükleme çünkü bu program "çağrısı çözümler void *", yazdırır `func` derleyici şablon karşılaştığında görünür değil.

*Bağımlı adları*, bir şablon parametresini bağımlı adlara sahip altında da farklıdır arama davranışı **/Zc:twoPhase-**. Uyumluluk modunda bağımlı adları şablonun tanımı noktasında bağlı değildir. Şablon örneği oluşturulduğunda bunun yerine, bu adlar aranır. Bağımlı işlev adı ile işlev çağrıları için yukarıdaki şablonun tanımı çağrısında noktasında görünür olan işlevler kümesi adı bağlıdır. Bağımsız değişkene bağlı arama gelen ek aşırı noktası şablon tanımının ve burada şablon örneği noktayı eklenir. İki aşama iki aşamalı arama, şablon tanımının ve arama şablonu örneklemesi zaman zaman bağımlı adları için arama bağlı olmayan adları için altındadır. Altında **/Zc:twoPhase-**, derleyici bağımsız değişkene bağlı arama sıradan, nitelenmemiş aramasından ayrı ayrı yapmaz (diğer bir deyişle, iki aşamalı arama bunu değil), aşırı çözümleme sonuçlarını farklı olabilir.

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

Uyumluluk modunda altında **/ izin veren-**, çağrı `tfunc(1729)` çözümler `void func(long)` aşırı değil, `void func(int)` olarak altında aşırı **/Zc:twoPhase-**, çünkü nitelenmemiş `func(int)` şablon tanımı sonra bildirilir ve bağımsız değişkene bağlı arama bulunamadı. Ancak `void func(S)` çağrısı ayarlamak aşırı eklenen şekilde bağımsız değişkene bağlı arama katılmak `tfunc(s)` sonra şablon işlevi bildirilmiş olsa bile.

### <a name="update-your-code-for-two-phase-conformance"></a>İki aşamalı uyum için kodunuzu güncelleştirin

Derleyici eski sürümleri anahtar sözcükleri gerekli olmadığı `template` ve `typename` her yerde C++ Standart bunları gerektirir. Bu anahtar sözcükler bazı konumda nasıl derleyicileri bağımlı adı arama ilk aşamasında ayrıştırması gereken belirsizliğini ortadan kaldırmak için gereklidir. Örneğin:

`T::Foo<a || b>(c);`

Uyumlu derleyici ayrıştırır `Foo` kapsamında bir değişken olarak `T`, bu kod anlamına gelir mantıksal- veya ifadesiyle `T::foo < a` sol işleneni olarak ve `b > (c)` sağ işleneni olarak. Kullanmak şunu mu demek, `Foo` işlevi şablon olarak bunu bir şablon ekleyerek belirtmelidir `template` anahtar sözcüğü:

`T::template Foo<a || b>(c);`

Visual Studio 2017 sürüm 15.3,'den önceki sürümlerde ve ne zaman **/Zc:twoPhase-** belirtilirse, derleyicisi tanır bu kodu olmadan `template` anahtar sözcüğü ve işlev şablonunun bağımsızdeğişkeniileyapılanbirçağrıolarakyorumlar`a || b`, şablonları çok sınırlı bir şekilde ayrıştırır. Yukarıdaki kod hiç Birinci aşamada Ayrıştırılan değil. İkinci aşamasında, bildirmek için yeterli içerik yok `T::Foo` derleyici anahtar sözcüğü kullanılmasını zorunlu olmayan bir değişken yerine bir şablonu olduğundan.

Bu davranış da anahtar sözcük ortadan kaldırarak görülebilir `typename` işlevi şablon gövdeleri, başlatıcılar, varsayılan bağımsız değişkenler ve noexcept bağımsız değişken adlarında önce. Örneğin:

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

Anahtar sözcüğü kullanmıyorsanız `typename` altında bu kod işlev gövdesinde derler **/Zc:twoPhase-**, ancak altında olmayan **/ izin veren-**. `typename` Belirtmek için anahtar sözcüğü gereklidir `TYPE` bağlıdır. Gövde altında ayrıştırılmadı çünkü **/Zc:twoPhase-**, derleyici does't anahtar sözcüğü gerektirir. İçinde **/ izin veren-** uyumluluk modu, kodu olmadan `typename` anahtar sözcüğü hataları oluşturur. Visual Studio 2017 sürüm 15.3 kodunuzu geçirmek ve ötesine, eklemek için `typename` eksik olduğu anahtar sözcüğü.

Benzer şekilde, bu kod örneği göz önünde bulundurun:

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

Altında **/Zc:twoPhase-** ve eski derleyicileri içinde Derleyici yalnızca gerektirir `template` 2 satırındaki anahtar sözcük. Varsayılan olarak ve uyumluluk modunda derleyici şimdi de gerektirir `template` belirtmek için 4 satırındaki anahtar sözcüğü `T::X<T>` bir şablondur. Bu anahtar sözcük eksik kodunu aramak ve kodunuzu standardına uygun hale getirmek için sağlayın.

Uyumluluk sorunları hakkında daha fazla bilgi için bkz: [Visual Studio'da C++ uygunluk geliştirmeleri](../../cpp-conformance-improvements-2017.md) ve [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zc:twoPhase-** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
