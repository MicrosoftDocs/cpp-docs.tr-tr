---
title: Açıkça Varsayılan Haline Getirilen ve Silinen İşlevler
ms.date: 11/04/2016
ms.assetid: 5a588478-fda2-4b3f-a279-db3967f5e07e
ms.openlocfilehash: bd13b5fef3a9dfc13d72f1ee34d7ced902735e15
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360898"
---
# <a name="explicitly-defaulted-and-deleted-functions"></a>Açıkça Varsayılan Haline Getirilen ve Silinen İşlevler

C++11'de varsayılan ve silinmiş işlevler, özel üye işlevlerin otomatik olarak oluşturulup oluşturulmadığı üzerinde açık bir denetim sağlar. Silinen işlevler, bağımsız değişkenlerde her türden işleve (özel üye işlevleri, normal üye işlevleri ve üye olmayan işlevler) sorunlu tür yükseltmelerini önlemenizi sağlayacak basit dil de sağlar. Böyle yükseltmeler önlenmezse, istenmeyen işlev çağrıları ortaya çıkabilir.

## <a name="benefits-of-explicitly-defaulted-and-deleted-functions"></a>Açıkça varsayılan ve silinmiş işlevlerin yararları

C ++'da, derleyici varsayılan oluşturucuyu, kopya oluşturucuyu, kopya atama işlecini ve yıkıcıyı bunları bildirmeyen bir tür için otomatik olarak atar. Bu işlevler *özel üye işlevler*olarak bilinir ve C++'daki basit kullanıcı tanımlı türleri C'deki yapılar gibi yapar. Diğer bir şey, herhangi bir ek kodlama çabası olmadan bunları oluşturabilir, kopyalayabilir ve yok edebilirsiniz. C++11, dil için daha fazla semantik sağlar ve taşıma oluşturucuyu ve taşıma atama oluşturucusunu derleyicinin otomatik olarak oluşturabileceği özel üye işlevleri listesine ekler.

Bu basit türler için uygundur, ancak karmaşık türler genellikle özel üye işlevlerden birini veya daha fazlasını tanımlar ve bu diğer özel üye işlevlerin otomatik olarak oluşturulmasını engelleyebilir. Uygulamada:

- Herhangi bir oluşturucu açıkça bildirilirse, hiçbir varsayılan oluşturucu otomatik olarak oluşturulmaz.

- Sanal bir yıkıcı açıkça bildirirse, hiçbir varsayılan yıkıcı otomatik olarak oluşturulmaz.

- Bir taşıma oluşturucu veya taşıma atama işleci açıkça bildirilirse, bu durumda:

  - Kopya oluşturucu otomatik olarak oluşturulamaz.

  - Kopya atama işleci otomatik olarak oluşturulamaz.

- Bir kopya oluşturucu, kopya atama işleci, taşıma oluşturucu, taşıma atama işleci veya yıkıcı açıkça bildirilirse, bu durumda:

  - Hiçbir hareket oluşturucu otomatik olarak oluşturulur.

  - Hiçbir taşıma atama işleci otomatik olarak oluşturulur.

> [!NOTE]
> Buna ek olarak, C ++ 11 standardı aşağıdaki ek kuralları belirtir:
>
> - Kopya oluşturucu veya yıkıcı açıkça bildirilirse, kopya atama işlecinin otomatik oluşturulması kullanım dışı kalır.
> - Kopya atama işleci veya yıkıcı açıkça bildirilirse, kopya oluşturucunun otomatik oluşturulması kullanım dışı kalır.
>
> Visual Studio, her iki durumda da gerekli işlevleri otomatik olarak örtük bir şekilde oluşturmaya devam eder ve bir uyarı vermez.

Bu kuralların sonuçları, nesne hiyerarşilerine de sızabilir. Örneğin, herhangi bir nedenle bir taban sınıfın, türeyen bir sınıftan çağrılabilen varsayılan bir oluşturucuya sahip olmaması durumunda, yani hiçbir parametre almayan **bir ortak** veya **korumalı** oluşturucu,sonra ondan türeyen bir sınıf otomatik olarak kendi varsayılan oluşturucusu oluşturamaz.

Bu kurallar, doğrudan, kullanıcı tanımlı türleri ve ortak C++ deyimlerinin uygulanmasını zorlaştırabilir — örneğin, kopya oluşturucuyu ve kopya atama işlecini özel olarak beyan ederek ve tanımlamayarak kullanıcı tanımlı bir türü kopyalanamaz hale getirerek.

```cpp
struct noncopyable
{
  noncopyable() {};

private:
  noncopyable(const noncopyable&);
  noncopyable& operator=(const noncopyable&);
};
```

C++11'den önce, bu kod parçacığı kopyalanamaz türlerin deyimsel biçimiydi. Ancak, çeşitli sorunları vardır:

- Kopya oluşturucunun gizlemek için özel olarak beyan edilmesi gerekir, ancak hiç beyan edildiği için varsayılan oluşturucunun otomatik olarak oluşturulması engellenir. Hiçbir şey vermese bile, isterseniz varsayılan oluşturucuyu açıkça tanımlamanız gerekir.

- Açıkça tanımlanmış varsayılan oluşturucu hiçbir şey yapsa bile, derleyici tarafından önemsiz olarak kabul edilir. Bu, otomatik olarak oluşturulan varsayılan oluşturucudan daha az verimlidir ve `noncopyable` öğesinin gerçek bir POD türü olmasını önler.

- Kopya oluşturucu ve kopya atama işleci dış koddan gizlense de, `noncopyable` öğesinin üye işlevleri ve arkadaşları onu görmeye ve çağırmaya devam edebilir. Bunlar bildiriliyorsa ancak tanımlanmamışsa, bunları çağırmak bağlayıcı hatasına neden olur.

- Bu yaygın olarak kabul edilen bir deyim olmasına rağmen, özel üye işlevlerin otomatik olarak üretilemeye yönelik tüm kuralları anlamadığınız sürece amaç açık değildir.

C ++ 11'de, kopyalanamayan deyim daha basit bir yolla uygulanabilir.

```cpp
struct noncopyable
{
  noncopyable() =default;
  noncopyable(const noncopyable&) =delete;
  noncopyable& operator=(const noncopyable&) =delete;
};
```

Ön C++11 deyimiyle ilgili sorunların nasıl çözüldüğüne dikkat edin:

- Varsayılan oluşturucunun oluşturulması, kopya oluşturucu bildirilerek önlenmeye devam eder, ancak bunu açıkça varsayılan haline getirerek geri alabilirsiniz.

- Açıkça varsayılan haline getirilen özel üye işlevleri önemsiz olarak sayılmaya devam eder, bu nedenle performans cezası olmaz ve `noncopyable` öğesinin gerçek bir POD türü olması engellenmez.

- Kopya oluşturucu ve kopyalama atama işleci herkese açıktır, ancak silinir. Silinmiş bir işlevi tanımlamak veya çağırmak için bir derleme zamanı hatasıdır.

- Amaç, `=default` ve `=delete`'i anlayan herkes için açıktır. Otomatik nesil özel üye işlevlerin kurallarını anlamak zorunda değilsiniz.

Benzer deyimler, kullanıcı tarafından tanımlanabilir olmayan, yalnızca dinamik olarak ayrılabilen veya dinamik olarak tahsis edilemeyen türleri yapmak için de vardır. Bu deyimlerin her biri benzer sorunlarla karşılaşan c++11 öncesi uygulamalara sahiptir ve benzer şekilde C++11'de varsayılan ve silinen özel üye işlevler açısından uygulanarak çözülür.

## <a name="explicitly-defaulted-functions"></a>Açıkça varsayılan işlevler

Özel üye işlevlerinden herhangi birini varsayılan olarak, özel üye işlevinin varsayılan uygulamayı kullandığını açıkça belirtmek, özel üye işlevini genel olmayan bir erişim niteleyicisiyle tanımlamak veya otomatik oluşturma diğer koşullar tarafından engellenen özel bir üye işlevini eski durumuna getirmek için varsayılan olarak yapabilirsiniz.

Özel bir üye işlevini bu örnekte olduğu gibi beyan ederek varsayılan olarak:

```cpp
struct widget
{
  widget()=default;

  inline widget& operator=(const widget&);
};

inline widget& widget::operator=(const widget&) =default;
```

Özel bir üye işlevini, bir sınıfın gövdesi dışında, silinemez olduğu sürece varsayılan olarak kullanabileceğinize dikkat edin.

Önemsiz özel üye işlevlerin performans avantajları nedeniyle, varsayılan davranışı istediğinizde otomatik olarak oluşturulan özel üye işlevleri boş işlev gövdelerine tercih edersiniz. Bunu, özel üye işlevini açıkça varsayılan olarak varsayılan olarak veya bildirmeyerek (ve ayrıca otomatik olarak oluşturulmasını engelleyecek diğer özel üye işlevleri beyan etmeyerek) yapabilirsiniz.

## <a name="deleted-functions"></a>Silinen işlevler

Özel üye işlevlerin yanı sıra normal üye işlevleri ve üye olmayan işlevleri, tanımlanmasını veya çağrılmasını önlemek için silebilirsiniz. Özel üye işlevlerin silmesi, derleyicinin istemediğiniz özel üye işlevler oluşturmasını önlemenin daha temiz bir yolunu sağlar. İşlev bildirildiği sırada silinmelidir; daha sonra işlevin bildirilebileceği ve varsayılan haline getirilebileceği şekilde silinemez.

```cpp
struct widget
{
  // deleted operator new prevents widget from being dynamically allocated.
  void* operator new(std::size_t) = delete;
};
```

Normal üye işlevin veya üye olmayan işlevlerin silmesi, sorunlu tür promosyonlarının istenmeyen bir işlevin çağrılmasına neden olmasını önler. Silinen işlevler hala aşırı yük çözünürlüğüne katıldığından ve türler tanıtıldıktan sonra çağrılabilecek işlevden daha iyi bir eşleşme sağladığından bu işe yarar. İşlev çağrısı, daha belirgin, ancak silinmiş bir işleve çözümlenir ve bir derleyici hatasına neden olur.

```cpp
// deleted overload prevents call through type promotion of float to double from succeeding.
void call_with_true_double_only(float) =delete;
void call_with_true_double_only(double param) { return; }
```

Önceki örnekte, **float** `call_with_true_double_only` bağımsız değişkeni kullanarak aramanın derleyici hatasına neden olacağını, ancak **int** bağımsız değişkeni kullanarak aramanın `call_with_true_double_only` buna yol açacağını belirten bildirim; **int** durumda, bağımsız değişken **int** **çift** ve başarıyla işlevin **çift** sürümünü aramak için terfi edilecektir, bu ne amaçlanan olmayabilir. Çift olmayan bir bağımsız değişken kullanarak bu işleve yapılan herhangi bir çağrının derleyici hatasına neden olduğundan emin olmak için, silinen işlevin şablon sürümünü bildirebilirsiniz.

```cpp
template < typename T >
void call_with_true_double_only(T) =delete; //prevent call through type promotion of any T to double from succeeding.

void call_with_true_double_only(double param) { return; } // also define for const double, double&, etc. as needed.
```
