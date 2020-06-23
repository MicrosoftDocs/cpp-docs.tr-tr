---
title: return Deyimi (C)
description: C dili return ifadesinin işlevi yürütmeyi sonlandırır ve isteğe bağlı olarak çağırana bir değer döndürür.
ms.date: 06/10/2020
helpviewer_keywords:
- ( ) parentheses in return statements
ms.assetid: 18cd82cf-f899-4b28-83ad-4eff353ddcb4
ms.openlocfilehash: 7d518aa17185c96de15c8f9aa9b65ae5c72bd014
ms.sourcegitcommit: 01b911613606c3fc92cbd9ca48cca6046a7e8258
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2020
ms.locfileid: "84716300"
---
# <a name="return-statement-c"></a>return Deyimi (C)

Bir **`return`** ifade bir işlevin yürütülmesini sonlandırır ve çağırma işlevine denetim döndürür. Yürütme, çağrının hemen ardından gelen noktada çağırma işlevinde sürdürülür. Bir **`return`** ifade, çağırma işlevine bir değer döndürebilir. Daha fazla bilgi için bkz. [dönüş türü](../c-language/return-type.md).

## <a name="syntax"></a>Syntax

> *sıçrama-deyim*: \
> &nbsp;&nbsp;&nbsp;&nbsp;**`return`***ifade*&#8203;<sub>opt</sub>**`;`**

Varsa *ifadesinin*değeri çağırma işlevine döndürülür. *İfade* atlanırsa, işlevin dönüş değeri tanımsızdır. Varsa ifadesi değerlendirilir ve ardından işlev tarafından döndürülen türe dönüştürülür. Bir **`return`** deyim dönüş türüne sahip işlevlerde bir ifade içerdiğinde **`void`** , derleyici bir uyarı oluşturur ve ifade değerlendirilmez.

**`return`** Bir işlev tanımında hiçbir ifade görünürse, çağrılan işlevin son ifadesi yürütüldükten sonra Denetim otomatik olarak çağırma işlevine döner. Bu durumda, çağrılan işlevin dönüş değeri tanımsızdır. İşlevin dışında bir dönüş türü varsa **`void`** , bu ciddi bir hatadır ve derleyici bir uyarı tanılama iletisi yazdırır. İşlevin **`void`** dönüş türü varsa, bu davranış normaldir, ancak kötü stil olarak kabul edilebilir. **`return`** Amacınızı açık hale getirmek için düz bir ifade kullanın.

İyi bir mühendislik uygulaması olarak, işlevleriniz için her zaman bir dönüş türü belirleyin. Dönüş değeri gerekmiyorsa, işlevi dönüş türüne sahip olacak şekilde bildirin **`void`** . Bir dönüş türü belirtilmemişse, C derleyicisi varsayılan dönüş türünü varsayar **`int`** .

Birçok programcı, deyiminin *ifade* bağımsız değişkenini içine almak için ayraçları kullanır **`return`** . Ancak, C parantezleri gerektirmez.

Derleyici, deyimden sonra yerleştirilmiş herhangi bir deyim bulursa ulaşılamaz kod hakkında bir uyarı tanılama iletisi verebilir **`return`** .

Bir **`main`** işlevde **`return`** deyim ve ifade isteğe bağlıdır. Döndürülen değere ne olur, belirtilmişse, uygulamaya bağlıdır. **Microsoft 'a özgü**: Microsoft C uygulama, ifade değerini programı çağıran işleme döndürür, örneğin *`cmd.exe`* . Hiçbir **`return`** ifade sağlanmazsa, Microsoft C çalışma zamanı başarı (0) veya hata (sıfır olmayan bir değer) gösteren bir değer döndürür.

## <a name="example"></a>Örnek

Bu örnek, birkaç bölümde yer aldığı bir programdır. Bu, **`return`** ifadesini ve bir değer döndürmek için ve isteğe bağlı olarak işlev yürütme ve isteğe bağlı olarak nasıl kullanıldığını gösterir.

```C
// C_return_statement.c
// Compile using: cl /W4 C_return_statement.c
#include <limits.h>      // for INT_MAX
#include <stdio.h>       // for printf

long long square( int value )
{
    // Cast one operand to long long to force the
    // expression to be evaluated as type long long.
    // Note that parentheses around the return expression
    // are allowed, but not required here.
    return ( value * (long long) value );
}
```

`square`İşlevi, aritmetik bir hata oluşmasını engellemek için bağımsız değişkeninin karekökünü döndürür daha geniş bir tür. **Microsoft 'a özgü**: Microsoft C uygulamasında, **`long long`** türü taşma olmadan iki değerin çarpımını alacak kadar büyük olur **`int`** .

İçindeki ifadesinin etrafındaki parantezler, **`return`** `square` ifadenin bir parçası olarak değerlendirilir ve deyimi için gerekli değildir **`return`** .

```C
double ratio( int numerator, int denominator )
{
    // Cast one operand to double to force floating-point
    // division. Otherwise, integer division is used,
    // then the result is converted to the return type.
    return numerator / (double) denominator;
}
```

`ratio`İşlevi, iki **`int`** bağımsız değişkenin oranını kayan nokta değeri olarak döndürür **`double`** . **`return`** İfade, işlenenlerinin birini öğesine kaldırarak kayan nokta işlemini kullanmaya zorlanır **`double`** . Aksi takdirde, tamsayı bölme işleci kullanılır ve kesirli bölüm kaybolacaktır.

```C
void report_square( void )
{
    int value = INT_MAX;
    long long squared = 0LL;
    squared = square( value );
    printf( "value = %d, squared = %lld\n", value, squared );
    return; // Use an empty expression to return void.
}
```

`report_square`İşlevi `square` , bir parametre değeri ile `INT_MAX` , ' a sığan en büyük işaretli tamsayı değeri ile çağırır **`int`** . **`long long`** Sonuç içinde depolanır `squared` ve sonra yazdırılır. `report_square`İşlevin **`void`** dönüş türü var, bu nedenle deyiminde bir ifadesi yok **`return`** .

```C
void report_ratio( int top, int bottom )
{
    double fraction = ratio( top, bottom );
    printf( "%d / %d = %.16f\n", top, bottom, fraction );
    // It's okay to have no return statement for functions
    // that have void return types.
}
```

`report_ratio`İşlevi `ratio` ve parametre değerleriyle çağırır `1` `INT_MAX` . **`double`** Sonuç içinde depolanır `fraction` ve sonra yazdırılır. `report_ratio`İşlevin **`void`** dönüş türü vardır, bu nedenle açıkça bir değer döndürmesi gerekmez. `report_ratio`"Alt sınırın dışında" yürütülmesi ve çağırana değer döndürmez.

```C
int main()
{
    int n = 1;
    int x = INT_MAX;

    report_square();
    report_ratio( n, x );

    return 0;
}
```

**`main`** İşlevi iki işlevi çağırır: `report_square` ve `report_ratio` . `report_square`Parametre alıp döndürmez **`void`** , sonucunu bir değişkene atamayız. Benzer şekilde, öğesini döndürür, bu `report_ratio` **`void`** nedenle dönüş değerini kaydetmemiz gerekir. Bu işlev çağrılarının her biri gerçekleştirildikten sonra, bir sonraki ifadede yürütme devam eder. Ardından **`main`** `0` , programın sona erdirmek için bir değer (genellikle başarıyı raporlamak için kullanılır) döndürür.

Örneği derlemek için adlı bir kaynak kodu dosyası oluşturun *`C_return_statement.c`* . Ardından, örnek kodu gösterilen sırayla kopyalayın. Dosyayı kaydedin ve komutunu kullanarak bir geliştirici komut istemi penceresinde derleyin:

**`cl /W4 C_return_statement.c`**

Ardından, örnek kodu çalıştırmak için **`C_return_statement.exe`** komut istemine yazın. Örneğin çıktısı şuna benzer:

```Output
value = 2147483647, squared = 4611686014132420609
1 / 2147483647 = 0.0000000004656613
```

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
