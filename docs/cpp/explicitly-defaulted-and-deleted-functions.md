---
title: Açıkça varsayılan ve silinmiş işlevlerin | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 5a588478-fda2-4b3f-a279-db3967f5e07e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 887ab1e29cf2a0eab656cc6d1b4587252871d328
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402828"
---
# <a name="explicitly-defaulted-and-deleted-functions"></a>Açıkça Varsayılan Haline Getirilen ve Silinen İşlevler
C ++ 11'de, varsayılan haline getirilen ve Silinen İşlevler, özel üye işlevlerinin otomatik olarak oluşturulan üzerinde kesin denetim verir. Silinen işlevler, bağımsız değişkenlerde her türden işleve (özel üye işlevleri, normal üye işlevleri ve üye olmayan işlevler) sorunlu tür yükseltmelerini önlemenizi sağlayacak basit dil de sağlar. Böyle yükseltmeler önlenmezse, istenmeyen işlev çağrıları ortaya çıkabilir.  
  
## <a name="benefits-of-explicitly-defaulted-and-deleted-functions"></a>Açıkça varsayılan ve silinmiş işlevlerin avantajları  
 C ++'da, derleyici varsayılan oluşturucuyu, kopya oluşturucuyu, kopya atama işlecini ve yıkıcıyı bunları bildirmeyen bir tür için otomatik olarak atar. Bu işlevler olarak bilinir *özel üye işlevleri*, ve bunlar ne C'deki yapılar gibi davranmasını basit kullanıcı tanımlı türler c++ sağlar. Diğer bir deyişle, oluşturma, kopyalama ve herhangi ek bir kodlama çabası göstermeden onları yok. C++11, dil için daha fazla semantik sağlar ve taşıma oluşturucuyu ve taşıma atama oluşturucusunu derleyicinin otomatik olarak oluşturabileceği özel üye işlevleri listesine ekler.  
  
 Bu basit türler için uygundur, ancak karmaşık türler genellikle bir veya daha fazla özel üye işlevleri tanımlayın ve bu diğer özel üye işlevlerinin otomatik olarak oluşturulmasını engelleyebilir. Pratikte:  
  
-   Herhangi bir oluşturucu açıkça bildirilirse, hiçbir varsayılan oluşturucu otomatik olarak oluşturulmaz.  
  
-   Sanal bir yıkıcı açıkça bildirirse, hiçbir varsayılan yıkıcı otomatik olarak oluşturulmaz.  
  
-   Bir taşıma oluşturucu veya taşıma atama işleci açıkça bildirilirse, bu durumda:  
  
    -   Hiçbir kopya Oluşturucusu otomatik olarak oluşturulur.  
  
    -   Hiçbir kopya atama işleci otomatik olarak oluşturulur.  
  
-   Bir kopya oluşturucu, kopya atama işleci, taşıma oluşturucu, taşıma atama işleci veya yıkıcı açıkça bildirilirse, bu durumda:  
  
    -   Hiçbir taşıma Oluşturucusu otomatik olarak oluşturulur.  
  
    -   Hiçbir taşıma atama işleci otomatik olarak oluşturulur.  
  
> [!NOTE]
>  Buna ek olarak, C ++ 11 standardı aşağıdaki ek kuralları belirtir:  
>   
>  -   Kopya oluşturucu veya yıkıcı açıkça bildirilirse, kopya atama işlecinin otomatik oluşturulması kullanım dışı kalır.  
> -   Kopya atama işleci veya yıkıcı açıkça bildirilirse, kopya oluşturucunun otomatik oluşturulması kullanım dışı kalır.  
>   
>  Visual Studio, her iki durumda da gerekli işlevleri otomatik olarak örtük bir şekilde oluşturmaya devam eder ve bir uyarı vermez.  
  
 Bu kuralların sonuçları, nesne hiyerarşilerine de sızabilir. Örneğin, türetilen bir sınıftan çağrılabilir olduğu bir varsayılan oluşturucuya sahip bir temel sınıf herhangi bir nedenle başarısız olursa — diğer bir deyişle, bir **genel** veya **korumalı** herhangi bir parametre olarak alan oluşturucu — bir sınıf türetilen kendi varsayılan oluşturucusunu otomatik olarak oluşturulamıyor.  
  
 Bu kurallar, hangi rahatça, kullanıcı tanımlı türleri ve sık kullanılan C++ deyimlerinin olması gerektiği uygulanmasını karmaşık hale getirebilir — Örneğin, kullanıcı tarafından tanımlanan bir türü kopyalanamaz özel ve değil kopya oluşturucu ve kopya atama işleci bildirerek yapma bunları tanımlama.  
  
```cpp 
struct noncopyable  
{  
  noncopyable() {};  
  
private:  
  noncopyable(const noncopyable&);  
  noncopyable& operator=(const noncopyable&);  
};  
```  
  
 C ++ 11'den önce bu kod parçacığı kopyalanamaz türlerin deyimsel form oluştu. Ancak, bazı sorunlar vardır:  
  
-   Kopya Oluşturucu, gizlemek için özel olarak bildirilmesi gerekir, ancak hiç bildirildiğinden, varsayılan oluşturucunun otomatik oluşturulması engellenir. İsterseniz, hiçbir şey yapmasa bile açıkça varsayılan oluşturucuyu tanımlamak zorunda.  
  
-   Açıkça tanımlanmış varsayılan oluşturucular hiçbir şey yapmaz olsa bile, Önemsiz olmayan derleyici tarafından kabul edilir. Bu, otomatik olarak oluşturulan varsayılan oluşturucudan daha az verimlidir ve `noncopyable` öğesinin gerçek bir POD türü olmasını önler.  
  
-   Kopya oluşturucu ve kopya atama işleci dış koddan gizlense de, `noncopyable` öğesinin üye işlevleri ve arkadaşları onu görmeye ve çağırmaya devam edebilir. Bildirilir ancak tanımlanmazsa bunların çağrılması bir bağlayıcı hatasına neden olur.  
  
-   Bu yaygın olarak kabul edilen bir deyim olmasına rağmen özel üye işlevleri otomatik oluşturulması için tüm kurallar anlamadan amaç açık değildir.  
  
 C ++ 11'de, kopyalanamayan deyim daha basit bir yolla uygulanabilir.  
  
```cpp 
struct noncopyable  
{  
  noncopyable() =default;  
  noncopyable(const noncopyable&) =delete;  
  noncopyable& operator=(const noncopyable&) =delete;  
};  
```  
  
 Bildirim nasıl öncesi sorunların-C ++ 11 giderildiğine:  
  
-   Varsayılan oluşturucunun oluşturulması, kopya oluşturucu bildirilerek önlenmeye devam eder, ancak bunu açıkça varsayılan haline getirerek geri alabilirsiniz.  
  
-   Açıkça varsayılan haline getirilen özel üye işlevleri önemsiz olarak sayılmaya devam eder, bu nedenle performans cezası olmaz ve `noncopyable` öğesinin gerçek bir POD türü olması engellenmez.  
  
-   Kopya oluşturucu ve kopya atama işleci geneldir ancak silinmiştir. Bunu tanımlamak veya silinmiş bir işlevi çağırmak için bir derleme zamanı hatasıdır.  
  
-   Amaç, `=default` ve `=delete`'i anlayan herkes için açıktır. İçin özel üye işlevleri otomatik oluşturulması kurallarını anlamak zorunda değilsiniz.  
  
 Benzer deyimleri, taşınabilir olmayan, yalnızca dinamik olarak ayrılabilen veya dinamik olarak ayrılamaz kullanıcı tanımlı türler yapmak için mevcut. Her biri bu deyimleri sahip öncesi-benzer sorunlara ve çözümlenen C ++ 11'de aşısından bunları uygulayarak C ++ 11 uygulamalarına varsayılan ve silinmiş özel üye işlevleri.  
  
## <a name="explicitly-defaulted-functions"></a>Açıkça varsayılan İşlevler  
 Herhangi bir özel üye işlevlerini varsayılan — açıkça özel üye işlevini bir ortak olmayan erişim niteleyicisiyle tanımlamak veya yeniden devreye sokmak için özel üye işlevini varsayılan uygulamayı kullanan durum için özel bir üye işlev ayarlanmış başka koşullar nedeniyle otomatik oluşturma engellendi.  
  
 Bu örnekte olduğu gibi bildirerek özel üye işlevini varsayılan edebilirsiniz:  
  
```cpp 
struct widget  
{  
  widget()=default;  
  
  inline widget& operator=(const widget&);  
};  
  
inline widget& widget::operator=(const widget&) =default;  
```  
  
 Satır içine alınabilir olduğu sürece bir sınıfın gövdesi dışındaki özel üye işlevini varsayılan yapabileceğinize dikkat edin.  
  
 Önemsiz özel üye işlevlerinin performans avantajları nedeniyle varsayılan davranışı istediğinizde boş işlev gövdeleri üzerinden otomatik olarak oluşturulan özel üye işlevleri tercih öneririz. Açıkça özel üye işlevini varsayarak veya bunu bildirmeyerek (ve aynı zamanda otomatik olarak oluşturulmasını önleyen diğer özel üye işlevlerini bildirmeyerek.) ile bunu yapabilirsiniz  
  
## <a name="deleted-functions"></a>Silinen İşlevler  
 Özel üye işlevlerinin yanı sıra normal üye işlevleri ve bunları tanımlanan tanımlanmalarını veya adlandırılmalarını önlemek için üye olmayan işlevleri silebilirsiniz. Özel üye işlevlerini silme, derleyicinin istemediğiniz özel üye işlevleri oluşturmasını daha temiz bir yol sağlar. İşlev bildirildiği sırada silinmelidir; daha sonra işlevin bildirilebileceği ve varsayılan haline getirilebileceği şekilde silinemez.  
  
```cpp 
struct widget  
{  
  // deleted operator new prevents widget from being dynamically allocated.  
  void* operator new(std::size_t) = delete;  
};  
```  
  
 Normal üye işlevini veya üye olmayan işlevleri silme, sorunlu tür yükseltmelerini istenmeden bir işlevin çağrılmasına neden öğesinden engeller. Silinen işlevler yine aşırı yükleme çözünürlüğüne ve türler yükseltildikten sonra çağrılabilen işlevi daha iyi bir eşleşme sağlamak için bu çalışır. İşlev çağrısı, daha belirgin, ancak silinmiş bir işleve çözümlenir ve bir derleyici hatasına neden olur.  
  
```cpp 
// deleted overload prevents call through type promotion of float to double from succeeding.  
void call_with_true_double_only(float) =delete;  
void call_with_true_double_only(double param) { return; }  
```  
  
 Yukarıdaki örnekte, dikkat edin `call_with_true_double_only` kullanarak bir **float** bağımsız değişkeni, bir derleyici hatasına neden ancak arama `call_with_true_double_only` kullanarak bir **int** olmadığına; **int** durumda, bağımsız değişken yükseltilecek gelen **int** için **çift** ve başarıyla **çift** işlevi sürümü olsa bile, amaçlanan olmayabilir. Çift olmayan bir bağımsız değişken kullanılarak bu işleve yapılan tüm çağrıların bir derleyici hatası oluşturduğundan emin olmak için silinen işlevin şablon sürümünü bildirebilirsiniz.  
  
```cpp 
template < typename T >  
void call_with_true_double_only(T) =delete; //prevent call through type promotion of any T to double from succeeding.  
  
void call_with_true_double_only(double param) { return; } // also define for const double, double&, etc. as needed.  
```