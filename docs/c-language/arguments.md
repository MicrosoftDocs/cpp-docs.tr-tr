---
title: Arguments
ms.date: 11/04/2016
helpviewer_keywords:
- arguments [C++], function
- function parameters
- functions [C], parameters
- function parameters, about function parameters
- function arguments
- function calls, arguments
ms.assetid: 14cf0389-2265-41f0-9a96-f2223eb406ca
ms.openlocfilehash: e1c88034044c74a542384873454f993b6bce3244
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232670"
---
# <a name="arguments"></a>Arguments

Bir işlevdeki bağımsız değişkenler şu biçimde olabilir:

> *ifade* **(** *ifade listesi*<SUB>opt</SUB> **)** /* işlev çağrısı */

Bir işlev çağrısında *ifade listesi* , ifadelerin listesidir (virgülle ayrılmış olarak). Bu ikinci ifadelerin değerleri, işleve geçirilen bağımsız değişkenlerdir. İşlev bağımsız değişken alırsa, *ifade listesi* anahtar sözcüğünü içermelidir **`void`** .

Bağımsız değişken temel, yapı, birleşim veya işaretçi türünde herhangi bir değer olabilir. Tüm bağımsız değişkenler değere göre geçirilir. Bu, bağımsız değişkenin bir kopyasının ilgili parametreye atandığı anlamına gelir. İşlev, geçirilen bağımsız değişkenin gerçek bellek konumunu bilmez. İşlev, ilk olarak türetildiği değişkeni etkilemeden bu kopyayı kullanır.

Dizileri veya işlevleri bağımsız değişkenler olarak geçiremezseniz de, bu öğelere işaretçileri geçirebilirsiniz. İşaretçiler, işlevin bir değere başvuruya göre erişmesi için bir yöntem sağlar. Bir değişken işaretçisi değişkenin adresini tuttuğu için işlev değişkenin değerine erişmek amacıyla bu adresi kullanabilir. İşaretçi bağımsız değişkenleri, diziler ve işlevler bağımsız değişkenler olarak geçirilemese de bir işlevin dizilere ve işlevlere erişmesini sağlar.

Bağımsız değişkenlerin değerlendirilme sırası, farklı derleyiciler ve farklı iyileştirme düzeyleri altında değişebilir. Bununla birlikte, işlev girilmeden önce bağımsız değişkenler ve yan etkileri tamamen değerlendirilir. Yan etkileri hakkında bilgi için bkz. [yan etkileri](../c-language/side-effects.md) .

İşlev çağrısındaki *ifade listesi* değerlendirilir ve işlev çağrısındaki her bağımsız değişkende Olağan aritmetik dönüştürmeler gerçekleştirilir. Bir prototip varsa, sonuçta elde edilen bağımsız değişken türü prototipin ilgili parametresiyle karşılaştırılır. Bunlar eşleşmiyorsa, bir dönüştürme işlemi gerçekleştirilir veya bir tanılama iletisi verilir. Parametreler de olağan aritmetik dönüştürmelerden geçer.

İşlevin prototipi veya tanımı açık olarak değişken sayıda bağımsız değişken belirtmediği müddetçe, *ifade listesindeki* ifadelerin sayısı parametre sayısıyla eşleşmelidir. Bu durumda, derleyici parametreler listesinde olabildiğince çok bağımsız değişkeni ve tür adlarını denetler ve bunları gerekirse yukarıda açıklandığı gibi dönüştürür. Daha fazla bilgi için bkz. [değişken sayıda bağımsız değişkene sahip çağrılar](../c-language/calls-with-a-variable-number-of-arguments.md) .

Prototipin parametre listesi yalnızca anahtar sözcüğünü içeriyorsa **`void`** , derleyici işlev çağrısında sıfır bağımsız değişken ve tanımda sıfır parametre bekler. Herhangi bir bağımsız değişken bulursa, bir tanılama iletisi verilir.

## <a name="example"></a>Örnek

Bu örnek, işaretçileri bağımsız değişkenler olarak kullanır:

```C
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

Bu örnekte, işlevi ' `swap` de, `main` tanımlayıcılardan sırasıyla temsil edilen iki bağımsız değişkene `num1` ve `num2` her ikisi de değer işaretçilerine sahip olacak şekilde bildirilmiştir **`int`** . `num1`Ve `num2` prototip stili tanımındaki parametreler, tür değerlerine işaretçiler olarak da belirtilir **`int`** .

İşlev çağrısında

```C
swap( &x, &y )
```

`x` adresi `num1` içinde, `y` adresi ise `num2` içinde depolanır. Artık aynı konumda iki ad veya "diğer ad" vardır. `*num1` öğesindeki `*num2` ve `swap` başvuruları, `x` öğesinde `y` ve `main`'nin etkili başvurularıdır. `swap` içindeki atamalar, `x` ve `y` içeriğini birbiriyle değiştirir. Bu nedenle, hiçbir **`return`** ifade gerekli değildir.

Derleyici, `swap` prototipi her parametreye yönelik bağımsız değişken türleri içerdiğinden `swap` bağımsız değişkenleri için tür denetimi gerçekleştirir. Prototip ve tanımın parantez içindeki tanımlayıcıları, aynı veya farklı olabilir. Önemli olan, hem prototipte hem de tanımda bağımsız değişken türlerinin parametre listelerindeki türlerle eşleşmesidir.

## <a name="see-also"></a>Ayrıca bkz.

[İşlev çağrıları](../c-language/function-calls.md)
