---
title: "Bağımsız değişkenler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- arguments [C++], function
- function parameters
- functions [C], parameters
- function parameters, about function parameters
- function arguments
- function calls, arguments
ms.assetid: 14cf0389-2265-41f0-9a96-f2223eb406ca
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54819766da9ebd002fa4990ca0b9650626b89015
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="arguments"></a>Arguments
Bir işlevdeki bağımsız değişkenler şu biçimde olabilir:  
  
```  
  
expression  
(  
expression-list <SUB>opt</SUB> )  /* Function call */  
```  
  
 Bir işlev çağrısında *ifade listesi* (virgülle ayrılmış) ifade listesini içerir. Bu ikinci ifadelerin değerleri, işleve geçirilen bağımsız değişkenlerdir. İşlev bağımsız değişkenler, uzun sürerse *ifade listesinde* anahtar sözcüğü içermelidir `void`.  
  
 Bağımsız değişken temel, yapı, birleşim veya işaretçi türünde herhangi bir değer olabilir. Tüm bağımsız değişkenler değere göre geçirilir. Bu, bağımsız değişkenin bir kopyasının ilgili parametreye atandığı anlamına gelir. İşlev, geçirilen bağımsız değişkenin gerçek bellek konumunu bilmez. İşlev, ilk olarak türetildiği değişkeni etkilemeden bu kopyayı kullanır.  
  
 Dizileri veya işlevleri bağımsız değişkenler olarak geçiremezseniz de, bu öğelere işaretçileri geçirebilirsiniz. İşaretçiler, işlevin bir değere başvuruya göre erişmesi için bir yöntem sağlar. Bir değişken işaretçisi değişkenin adresini tuttuğu için işlev değişkenin değerine erişmek amacıyla bu adresi kullanabilir. İşaretçi bağımsız değişkenleri, diziler ve işlevler bağımsız değişkenler olarak geçirilemese de bir işlevin dizilere ve işlevlere erişmesini sağlar.  
  
 Bağımsız değişkenlerin değerlendirilme sırası, farklı derleyiciler ve farklı iyileştirme düzeyleri altında değişebilir. Bununla birlikte, işlev girilmeden önce bağımsız değişkenler ve yan etkileri tamamen değerlendirilir. Bkz: [yan etkileri](../c-language/side-effects.md) yan etkileri hakkında bilgi için.  
  
 *İfade listesinde* bir işlev çağrısı değerlendirilir ve olağan aritmetik dönüştürmeler her işlev çağrısı değişkeninde üzerinde gerçekleştirilir. Bir prototip varsa, sonuçta elde edilen bağımsız değişken türü prototipin ilgili parametresiyle karşılaştırılır. Bunlar eşleşmiyorsa, bir dönüştürme işlemi gerçekleştirilir veya bir tanılama iletisi verilir. Parametreler de olağan aritmetik dönüştürmelerden geçer.  
  
 İfadelerde sayısı *ifade listesinde* işlev prototipi veya tanımı açıkça değişken sayıda bağımsız değişken belirtmedikçe parametre sayısı aynı olmalıdır. Bu durumda, derleyici parametreler listesinde olabildiğince çok bağımsız değişkeni ve tür adlarını denetler ve bunları gerekirse yukarıda açıklandığı gibi dönüştürür. Bkz: [bir değişken sayısı değişkenlerin aramaları](../c-language/calls-with-a-variable-number-of-arguments.md) daha fazla bilgi için.  
  
 Prototipin parametre listesi yalnızca `void` anahtar sözcüğünü içeriyorsa, derleyici işlev çağrısında sıfır bağımsız değişken ve tanımda sıfır parametre bekler. Herhangi bir bağımsız değişken bulursa, bir tanılama iletisi verilir.  
  
## <a name="example"></a>Örnek  
 Bu örnek, işaretçileri bağımsız değişkenler olarak kullanır:  
  
```  
int main()  
{  
    /* Function prototype */  
  
    void swap( int *num1, int *num2 );  
    int x, y;  
    .  
    .  
    .  
    swap( &x, &y );  /* Function call */  
}  
  
/* Function definition */  
  
void swap( int *num1, int *num2 )  
{  
    int t;  
  
    t = *num1;  
    *num1 = *num2;  
    *num2 = t;  
}  
```  
  
 Bu örnekte, `swap` işlevi `main`'de iki bağımsız değişkeni olacak şekilde bildirilmiştir; her ikisi de `num1` değerlerinin işaretçileri olan bu bağımsız değişkenler, sırasıyla `num2` ve `int` tanımlayıcılarıyla temsil edilir. Prototip stili tanımdaki `num1` ve `num2` parametreleri de `int` türü değerlerin işaretçileri olarak bildirilmiştir.  
  
 İşlev çağrısında  
  
```  
swap( &x, &y )  
```  
  
 `x` adresi `num1` içinde, `y` adresi ise `num2` içinde depolanır. Artık aynı konumda iki ad veya "diğer ad" vardır. `*num1` öğesindeki `*num2` ve `swap` başvuruları, `x` öğesinde `y` ve `main`'nin etkili başvurularıdır. `swap` içindeki atamalar, `x` ve `y` içeriğini birbiriyle değiştirir. Bu nedenle, `return` deyimine gerek yoktur.  
  
 Derleyici, `swap` prototipi her parametreye yönelik bağımsız değişken türleri içerdiğinden `swap` bağımsız değişkenleri için tür denetimi gerçekleştirir. Prototip ve tanımın parantez içindeki tanımlayıcıları, aynı veya farklı olabilir. Önemli olan, hem prototipte hem de tanımda bağımsız değişken türlerinin parametre listelerindeki türlerle eşleşmesidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev Çağrıları](../c-language/function-calls.md)