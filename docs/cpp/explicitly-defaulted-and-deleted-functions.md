---
title: "Açıkça varsayılan ve işlevleri silinmiş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 5a588478-fda2-4b3f-a279-db3967f5e07e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f31304a63ddedb90c0aa76ff77883bd1b007b77f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="explicitly-defaulted-and-deleted-functions"></a>Açıkça Varsayılan Haline Getirilen ve Silinen İşlevler
C ++ 11'de, varsayılan haline getirilen ve Silinen işlevler özel üye işlevleri otomatik olarak oluşturulan açık Denetim verin. Silinen işlevler, bağımsız değişkenlerde her türden işleve (özel üye işlevleri, normal üye işlevleri ve üye olmayan işlevler) sorunlu tür yükseltmelerini önlemenizi sağlayacak basit dil de sağlar. Böyle yükseltmeler önlenmezse, istenmeyen işlev çağrıları ortaya çıkabilir.  
  
## <a name="benefits-of-explicitly-defaulted-and-deleted-functions"></a>Avantajları açıkça varsayılan ve işlevleri silindi  
 C ++'da, derleyici varsayılan oluşturucuyu, kopya oluşturucuyu, kopya atama işlecini ve yıkıcıyı bunları bildirmeyen bir tür için otomatik olarak atar. Bu işlevler olarak da bilinir *özel üye işlevleri*, ve bunlar ne yapıları c dilinde gibi davranır basit kullanıcı tanımlı türler c++ olun Diğer bir deyişle, oluşturma, kopyalama ve ek bir kodlama çaba yok. C++11, dil için daha fazla semantik sağlar ve taşıma oluşturucuyu ve taşıma atama oluşturucusunu derleyicinin otomatik olarak oluşturabileceği özel üye işlevleri listesine ekler.  
  
 Bu basit türler için uygundur ancak karmaşık türleri genellikle bir veya daha fazla özel üye işlevleri tanımlar ve bu otomatik olarak oluşturulan diğer özel üye işlevleri engelleyebilir. Uygulamada:  
  
-   Herhangi bir oluşturucu açıkça bildirilirse, hiçbir varsayılan oluşturucu otomatik olarak oluşturulmaz.  
  
-   Sanal bir yıkıcı açıkça bildirirse, hiçbir varsayılan yıkıcı otomatik olarak oluşturulmaz.  
  
-   Bir taşıma oluşturucu veya taşıma atama işleci açıkça bildirilirse, bu durumda:  
  
    -   Kopya Oluşturucu otomatik olarak oluşturulur.  
  
    -   Hiçbir kopya atama işleci otomatik olarak oluşturulur.  
  
-   Bir kopya oluşturucu, kopya atama işleci, taşıma oluşturucu, taşıma atama işleci veya yıkıcı açıkça bildirilirse, bu durumda:  
  
    -   Taşıma Oluşturucusu otomatik olarak oluşturulur.  
  
    -   Hiçbir taşıma atama işleci otomatik olarak oluşturulur.  
  
> [!NOTE]
>  Buna ek olarak, C ++ 11 standardı aşağıdaki ek kuralları belirtir:  
>   
>  -   Kopya oluşturucu veya yıkıcı açıkça bildirilirse, kopya atama işlecinin otomatik oluşturulması kullanım dışı kalır.  
> -   Kopya atama işleci veya yıkıcı açıkça bildirilirse, kopya oluşturucunun otomatik oluşturulması kullanım dışı kalır.  
>   
>  Visual Studio, her iki durumda da gerekli işlevleri otomatik olarak örtük bir şekilde oluşturmaya devam eder ve bir uyarı vermez.  
  
 Bu kuralların sonuçları, nesne hiyerarşilerine de sızabilir. Örneğin, herhangi bir nedenle temel bir sınıfta türetme sınıfından, yani parametre almayan bir `public` veya `protected` oluşturucusundan çağrılabilen varsayılan bir oluşturucu olmazsa, ondan türetilen sınıf kendi varsayılan oluşturucusunu otomatik olarak oluşturamaz.  
  
 Bu kurallar ne düz ileriye doğru kullanıcı tanımlı türler ve ortak C++ deyimleri olması gerektiğini uygulaması karmaşık hale getirebilir — Örneğin, kullanıcı tanımlı bir tür copyable olmayan özel olarak ve değil kopya oluşturucu ve kopya atama işleci bildirerek yapma bunları tanımlama.  
  
```  
struct noncopyable  
{  
  noncopyable() {};  
  
private:  
  noncopyable(const noncopyable&);  
  noncopyable& operator=(const noncopyable&);  
};  
```  
  
 C ++ 11 önce bu kod parçacığında kullanılan deyimsel formun copyable olmayan türlerinin oluştu. Bununla birlikte, bazı sorunlar vardır:  
  
-   Kopya Oluşturucu saklamak için özel olarak bildirilmesi gerekir, ancak hiç bildirildiğinden, varsayılan oluşturucu otomatik olarak oluşturulmasını önledi. Biri, isterseniz, hiçbir şey yapmaz olsa bile açıkça varsayılan oluşturucu tanımlamak zorunda.  
  
-   Açıkça tanımlanmış varsayılan oluşturucu, hiçbir şey yapmıyor olsa bile, onu Önemsiz olmayan derleyici tarafından kabul edilir. Bu, otomatik olarak oluşturulan varsayılan oluşturucudan daha az verimlidir ve `noncopyable` öğesinin gerçek bir POD türü olmasını önler.  
  
-   Kopya oluşturucu ve kopya atama işleci dış koddan gizlense de, `noncopyable` öğesinin üye işlevleri ve arkadaşları onu görmeye ve çağırmaya devam edebilir. Bildirilen ancak tanımlı değil, bunları çağırma bir bağlayıcı hatasına neden olur.  
  
-   Bunun yaygın olarak kabul edilen bir deyim olsa da, tüm kurallar için özel üye işlevleri otomatik olarak oluşturulmasını anlamadan hedefi NET değil.  
  
 C ++ 11'de, kopyalanamayan deyim daha basit bir yolla uygulanabilir.  
  
```  
struct noncopyable  
{  
  noncopyable() =default;  
  noncopyable(const noncopyable&) =delete;  
  noncopyable& operator=(const noncopyable&) =delete;  
};  
```  
  
 Bildirim nasıl öncesi sorunları-C ++ 11 deyim çözülmüş:  
  
-   Varsayılan oluşturucunun oluşturulması, kopya oluşturucu bildirilerek önlenmeye devam eder, ancak bunu açıkça varsayılan haline getirerek geri alabilirsiniz.  
  
-   Açıkça varsayılan haline getirilen özel üye işlevleri önemsiz olarak sayılmaya devam eder, bu nedenle performans cezası olmaz ve `noncopyable` öğesinin gerçek bir POD türü olması engellenmez.  
  
-   Kopya oluşturucu ve kopya atama işleci ortak ancak silindi. Tanımlamak veya silinmiş bir işlevi çağırmak için bir derleme zamanı hata var.  
  
-   Amaç, `=default` ve `=delete`'i anlayan herkes için açıktır. Özel üye işlevleri otomatik olarak oluşturulmasını için kurallar anlamak zorunda değilsiniz.  
  
 Benzer deyimleri taşınabilir olmayan, yalnızca dinamik olarak ayrılan veya dinamik olarak ayrılamıyor kullanıcı tanımlı türler yapmak için mevcut. Her bu deyimleri sahip pre-benzer sorunlar yaşar ve, benzer şekilde çözümlenir C ++ 11 inç cinsinden uygulayarak C ++ 11 uygulamaları varsayılan ve özel üye işlevleri silindi.  
  
## <a name="explicitly-defaulted-functions"></a>Açıkça varsayılan İşlevler  
 Özel üye işlevleri hiçbirini varsayılan — özel üye fonksiyonu genel erişim niteleyicisi özel üye işleviyle tanımlamak ya da yeniden devreye sokmanız varsayılan uygulama kullandığını açıkça durumuna özel bir üye işlev özelliği otomatik oluşturma başka koşullarda tarafından engellendi.  
  
 Özel üye işlevi bu örnekteki bildirerek varsayılan:  
  
```  
struct widget  
{  
  widget()=default;  
  
  inline widget& operator=(const widget&);  
};  
  
inline widget& widget::operator=(const widget&) =default;  
```  
  
 İnlinable olduğu sürece dışında bir sınıfın gövdesi, özel üye işlevi varsayılan dikkat edin.  
  
 Önemsiz özel üye işlevleri performans yararlarını nedeniyle, varsayılan davranışı istediğinizde boş işlevi gövdeleri otomatik olarak oluşturulan özel üye işlevleri tercih öneririz. Özel üye fonksiyonu açıkça varsayarak, veya göre bildirme değil (ve otomatik olarak oluşturulan önleyen diğer özel üye işlevleri bildirme değil de.) bunu yapabilirsiniz  
  
## <a name="deleted-functions"></a>Silinen İşlevler  
 Özel üye işlevleri yanı sıra normal üye işlevleri ve bunları tanımlanan adlı veya kaldırılmasını önlemek için üye olmayan işlevleri silebilirsiniz. Özel üye işlevleri silme istemediğiniz özel üye işlevleri oluşturma derleyici önleme temizleyici bir yol sağlar. İşlev bildirildiği sırada silinmelidir; daha sonra işlevin bildirilebileceği ve varsayılan haline getirilebileceği şekilde silinemez.  
  
```  
struct widget  
{  
  // deleted operator new prevents widget from being dynamically allocated.  
  void* operator new(std::size_t) = delete;  
};  
```  
  
 Normal üye işlevi veya üye olmayan işlevleri silinmesi çağrılacak istenmeyen bir işlev neden gelen sorunlu türü promosyonlar önler. Bu, silinen işlevler hala aşırı yük çözüm katılmak ve türleri yapılandırıldıktan sonra çağrılabilir işlev daha iyi bir eşleşme sağlayabildiği için çalışır. İşlev çağrısı, daha belirgin, ancak silinmiş bir işleve çözümlenir ve bir derleyici hatasına neden olur.  
  
```  
// deleted overload prevents call through type promotion of float to double from succeeding.  
void call_with_true_double_only(float) =delete;  
void call_with_true_double_only(double param) { return; }  
```  
  
 Yukarıdaki örnekte, `call_with_true_double_only` bağımsız değişkeni kullanılarak `float`'nin çağrılmasının, derleyici hatasına neden olduğuna, ancak `call_with_true_double_only` kullanılarak `int`'nin çağrılmasının hataya neden olmadığına dikkat edin; `int` durumunda, bağımsız değişken `int`'ten `double`'a yükseltilecek ve amaçlanan bu olmasa bile işlevin `double` sürümünü başarıyla çağıracaktır. Çift olmayan bir bağımsız değişken kullanılarak bu işleve yapılan tüm çağrıların bir derleyici hatası oluşturduğundan emin olmak için silinen işlevin şablon sürümünü bildirebilirsiniz.  
  
```  
template < typename T >  
void call_with_true_double_only(T) =delete; //prevent call through type promotion of any T to double from succeeding.  
  
void call_with_true_double_only(double param) { return; } // also define for const double, double&, etc. as needed.  
  
```