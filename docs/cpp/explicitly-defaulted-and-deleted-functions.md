---
title: Açıkça Varsayılan Haline Getirilen ve Silinen İşlevler
ms.date: 11/04/2016
ms.assetid: 5a588478-fda2-4b3f-a279-db3967f5e07e
ms.openlocfilehash: fd3fb53dec0cc08274b7ea54176c2a15dbab45d7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211586"
---
# <a name="explicitly-defaulted-and-deleted-functions"></a>Açıkça Varsayılan Haline Getirilen ve Silinen İşlevler

C++ 11 ' de, varsayılan ve silinmiş işlevler özel üye işlevlerinin otomatik olarak oluşturulup oluşturulmayacağı üzerinde açık denetim sağlar. Silinen işlevler, bağımsız değişkenlerde her türden işleve (özel üye işlevleri, normal üye işlevleri ve üye olmayan işlevler) sorunlu tür yükseltmelerini önlemenizi sağlayacak basit dil de sağlar. Böyle yükseltmeler önlenmezse, istenmeyen işlev çağrıları ortaya çıkabilir.

## <a name="benefits-of-explicitly-defaulted-and-deleted-functions"></a>Açıkça varsayılan olarak ayarlanmış ve silinen işlevlerin avantajları

C ++'da, derleyici varsayılan oluşturucuyu, kopya oluşturucuyu, kopya atama işlecini ve yıkıcıyı bunları bildirmeyen bir tür için otomatik olarak atar. Bu işlevler *özel üye işlevleri*olarak bilinir ve C++ ' da basit kullanıcı tanımlı türler C 'de yapılar gibi davranır. Diğer bir deyişle, ek kodlama çabaları olmadan bunları oluşturabilir, kopyalayabilir ve yok edebilirsiniz. C++11, dil için daha fazla semantik sağlar ve taşıma oluşturucuyu ve taşıma atama oluşturucusunu derleyicinin otomatik olarak oluşturabileceği özel üye işlevleri listesine ekler.

Bu basit türler için uygundur, ancak karmaşık türler genellikle bir veya daha fazla özel üye işlevi tanımlar ve bu, diğer özel üye işlevlerinin otomatik olarak oluşturulmasını engelleyebilir. Uygulamada:

- Herhangi bir oluşturucu açıkça bildirilirse, hiçbir varsayılan oluşturucu otomatik olarak oluşturulmaz.

- Sanal bir yıkıcı açıkça bildirirse, hiçbir varsayılan yıkıcı otomatik olarak oluşturulmaz.

- Bir taşıma oluşturucu veya taşıma atama işleci açıkça bildirilirse, bu durumda:

  - Hiçbir kopya Oluşturucu otomatik olarak oluşturulmaz.

  - Hiçbir kopyalama atama işleci otomatik olarak oluşturulmaz.

- Bir kopya oluşturucu, kopya atama işleci, taşıma oluşturucu, taşıma atama işleci veya yıkıcı açıkça bildirilirse, bu durumda:

  - Hiçbir taşıma Oluşturucusu otomatik olarak oluşturulmaz.

  - Hiçbir Move-atama işleci otomatik olarak oluşturulmaz.

> [!NOTE]
> Buna ek olarak, C ++ 11 standardı aşağıdaki ek kuralları belirtir:
>
> - Kopya oluşturucu veya yıkıcı açıkça bildirilirse, kopya atama işlecinin otomatik oluşturulması kullanım dışı kalır.
> - Kopya atama işleci veya yıkıcı açıkça bildirilirse, kopya oluşturucunun otomatik oluşturulması kullanım dışı kalır.
>
> Visual Studio, her iki durumda da gerekli işlevleri otomatik olarak örtük bir şekilde oluşturmaya devam eder ve bir uyarı vermez.

Bu kuralların sonuçları, nesne hiyerarşilerine de sızabilir. Örneğin, herhangi bir nedenle bir temel sınıf, türetilen bir sınıftan çağrılabilir bir varsayılan oluşturucuya sahip olmaz — yani parametresi olmayan bir **`public`** veya **`protected`** Oluşturucu — bundan türetilmiş bir sınıf, kendi varsayılan oluşturucusunu otomatik olarak üretemiyor.

Bu kurallar, basit iletme, Kullanıcı tanımlı türler ve ortak C++ oluşturucuları 'nin uygulanmasını karmaşıklaştırır. Örneğin, kopya oluşturucusunu ve kopya atama işlecini özel olarak bildirerek ve bunları tanımlamaktan, Kullanıcı tanımlı tür kopyalanabilir olmayan bir tür oluşturma.

```cpp
struct noncopyable
{
  noncopyable() {};

private:
  noncopyable(const noncopyable&);
  noncopyable& operator=(const noncopyable&);
};
```

C++ 11 ' den önce, bu kod parçacığı kopyalanabilir olmayan türlerin ıdimatik biçimidir. Ancak, çeşitli sorunlar vardır:

- Kopya oluşturucunun gizlenmesi için özel olarak bildirilmesini gerekir, ancak her birinde bildirildiği için, varsayılan oluşturucunun otomatik olarak oluşturulması engellenir. Herhangi bir şey yapmasa bile, bir tane istiyorsanız, varsayılan oluşturucuyu açıkça tanımlamanız gerekir.

- Açıkça tanımlanmış varsayılan Oluşturucu hiçbir şey yapmasa bile, derleyici tarafından önemsiz olmayan kabul edilir. Bu, otomatik olarak oluşturulan varsayılan oluşturucudan daha az verimlidir ve `noncopyable` öğesinin gerçek bir POD türü olmasını önler.

- Kopya oluşturucu ve kopya atama işleci dış koddan gizlense de, `noncopyable` öğesinin üye işlevleri ve arkadaşları onu görmeye ve çağırmaya devam edebilir. Bunlar, tanımlarsa ve tanımlanmazsa, çağrı bir bağlayıcı hatasına neden olur.

- Bu, yaygın olarak kabul edilen bir deyim olsa da, özel üye işlevlerinin otomatik olarak oluşturulmasına yönelik tüm kuralları anlamadığınız müddetçe amaç net değildir.

C ++ 11'de, kopyalanamayan deyim daha basit bir yolla uygulanabilir.

```cpp
struct noncopyable
{
  noncopyable() =default;
  noncopyable(const noncopyable&) =delete;
  noncopyable& operator=(const noncopyable&) =delete;
};
```

Pre-C + + 11 deyimciyle ilgili sorunların çözümlendiğine dikkat edin:

- Varsayılan oluşturucunun oluşturulması, kopya oluşturucu bildirilerek önlenmeye devam eder, ancak bunu açıkça varsayılan haline getirerek geri alabilirsiniz.

- Açıkça varsayılan haline getirilen özel üye işlevleri önemsiz olarak sayılmaya devam eder, bu nedenle performans cezası olmaz ve `noncopyable` öğesinin gerçek bir POD türü olması engellenmez.

- Kopya Oluşturucu ve kopya atama işleci herkese açıktır, ancak silinir. Silinen bir işlevi tanımlamak veya çağırmak için derleme zamanı hatası.

- Amaç, `=default` ve `=delete`'i anlayan herkes için açıktır. Özel üye işlevlerinin otomatik olarak oluşturulmasına ilişkin kuralları anlamanız gerekmez.

Taşınabilir olmayan, yalnızca dinamik olarak ayrılabilen ya da dinamik olarak ayrılamaz Kullanıcı tanımlı türler oluşturmak için benzer bir ıoms vardır. Bu deyimlerin her biri, benzer sorunları çözen ve aynı şekilde C++ 11 ' de, varsayılan olarak ayarlanmış ve silinen özel üye işlevlerini uygulayarak benzer şekilde çözümlenen önceden C + + 11 uygulamalarına sahiptir.

## <a name="explicitly-defaulted-functions"></a>Açıkça varsayılan işlevler

Özel üye işlevinin varsayılan uygulamayı kullanmasını, özel üye işlevini genel olmayan bir erişim niteleyicisi ile tanımlamak ya da otomatik oluşturma diğer koşullar tarafından engellenmiş özel bir üye işlevini yeniden devreye sokmak için özel üye işlevlerinden herhangi birini varsayılan olarak kullanabilirsiniz.

Bu örnekte olduğu gibi bildirerek özel bir üye işlevini varsayılan olarak görürsünüz:

```cpp
struct widget
{
  widget()=default;

  inline widget& operator=(const widget&);
};

inline widget& widget::operator=(const widget&) =default;
```

Özel bir üye işlevini, bir sınıfın gövdesi dışında, geçersiz olduğu sürece varsayılan olarak belirleyebildiğinize dikkat edin.

Önemsiz özel üye işlevlerinin performans avantajları nedeniyle, varsayılan davranışı istediğinizde boş işlev gövdeleri üzerinden otomatik olarak oluşturulan özel üye işlevleri tercih etmenizi öneririz. Bu işlemi, özel üye işlevini açıkça değiştirerek ya da bildirmiyorsanız (ve ayrıca otomatik olarak oluşturulmasını engelleyecek diğer özel üye işlevleri bildirmiyorsanız) yapabilirsiniz.

## <a name="deleted-functions"></a>Silinen İşlevler

Tanımlanmalarını veya çağrılmasına engel olmak için, özel üye işlevlerini, normal üye işlevlerini ve üye olmayan işlevleri de silebilirsiniz. Özel üye işlevlerinin silinmesi, derleyicinin istemediğiniz özel üye işlevleri oluşturmasını engelleyen bir temizleyici yol sağlar. İşlev bildirildiği sırada silinmelidir; daha sonra işlevin bildirilebileceği ve varsayılan haline getirilebileceği şekilde silinemez.

```cpp
struct widget
{
  // deleted operator new prevents widget from being dynamically allocated.
  void* operator new(std::size_t) = delete;
};
```

Normal üye işlev veya üye olmayan işlevlerin silinmesi, sorunlu tür yükseltmelerin istenmeden işlevin çağrılmasına neden olmasını engeller. Silinen İşlevler hala aşırı yükleme çözümüne katıldığından ve türler yükseltildikten sonra çağrılabilecek işlevle daha iyi bir eşleşme sağladığından bu çalışır. İşlev çağrısı, daha belirgin, ancak silinmiş bir işleve çözümlenir ve bir derleyici hatasına neden olur.

```cpp
// deleted overload prevents call through type promotion of float to double from succeeding.
void call_with_true_double_only(float) =delete;
void call_with_true_double_only(double param) { return; }
```

Yukarıdaki örnekte, `call_with_true_double_only` bir bağımsız değişken kullanılarak çağırmanın bir **`float`** derleyici hatasına neden olacağını, ancak `call_with_true_double_only` bir bağımsız değişken kullanılarak çağrılmasını fark **`int`** etmez; **`int`** Bu durumda, bağımsız değişken ' dan ' a yükseltilir **`int`** **`double`** ve işlevin sürümünü başarılı bir şekilde çağırır **`double`** , ancak böyle bir amaçla kullanılmayabilir. Double olmayan bağımsız değişken kullanarak bu işleve yapılan herhangi bir çağrının bir derleyici hatasına neden olduğundan emin olmak için, silinen işlevin şablon sürümünü bildirebilirsiniz.

```cpp
template < typename T >
void call_with_true_double_only(T) =delete; //prevent call through type promotion of any T to double from succeeding.

void call_with_true_double_only(double param) { return; } // also define for const double, double&, etc. as needed.
```
