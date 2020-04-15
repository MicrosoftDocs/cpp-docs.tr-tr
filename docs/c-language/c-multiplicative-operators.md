---
title: C Çarpma İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- arithmetic operators [C++], multiplicative operators
- / operator
- / operator, multiplicative operators
- remainder operator (%)
- operators [C], multiplication
- '% operator'
- slash (/) operator
- multiplication operator [C++], multiplicative operators
ms.assetid: 495471c9-319b-4eb4-bd97-039a025fd3a9
ms.openlocfilehash: f9f5f62e2326826e3087a8668cd9107da4b85388
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335004"
---
# <a name="c-multiplicative-operators"></a>C Çarpma İşleçleri

Çarpan işleçleri çarpma (<strong>\*</strong>),**/** bölme (**%**), ve kalan ( ) işlemleri gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

*çarpan-ifade*: &nbsp; &nbsp; &nbsp; &nbsp; *dökme* &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **%** **/** *multiplicative-expression* <strong>\*</strong> &nbsp; &nbsp; &nbsp; &nbsp; *multiplicative-expression* *cast-expression* *cast-expression* *cast-expression* *multiplicative-expression* ifade çarpan-ifade döküm-ifade çarpan-ifade cast-expression çarpan-ifade çarpan-ifade döküm-ifade çarpan-ifade dökme-ifade &nbsp; &nbsp;

Geri kalan işleç**%**() operands integral olmalıdır. Çarpma (<strong>\*</strong>) ve**/** bölme ( ) işleçleri integral veya kayan tip operands alabilir; operands türleri farklı olabilir.

Çarpan işleçleri operands üzerinde olağan aritmetik dönüşümleri gerçekleştirmek. Sonucun türü, dönüşümden sonraki operandların türüdür.

> [!NOTE]
> Çarpma işleçleri tarafından gerçekleştirilen dönüştürmeler taşma veya yetersiz kalma koşulları sağlamadığından, çarpma işleminin sonucu dönüştürme sonrası işlenenlerin türünde gösterilmezse bilgiler kaybolabilir.

C çarpan işleçleri aşağıda açıklanmıştır:

|İşleç|Açıklama|
|--------------|-----------------|
|<strong>\*</strong>|Çarpma işleci iki operand'ın çarpılmasına neden olur.|
|**/**|Bölme işleci, ilk operand'ın ikinci operanda bölünmesine neden olur. İki tümsek operands bölünür ve sonuç bir karşıcı değilse, aşağıdaki kurallara göre kesilir:<br/><br/>- 0 ile bölünme sonucu ANSI C standardına göre tanımsızdır. Microsoft C derleyicisi derleme zamanında veya çalışma zamanında bir hata oluşturur.<br/><br/>- Her iki operands pozitif veya imzasız ise, sonuç 0 doğru kesilir.<br/><br/>- Eğer operand negatif ise, işlemin sonucu en büyük tamsayı daha az veya cebirsel bölüm eşit olup olmadığını ya da en küçük tamsayı büyük veya cebirsel bölüm e eşit uygulama tanımlanır. (Aşağıdaki Microsoft'a özel bölüme bakın.)|
|**%**|Geri kalan işleç sonucu, ilk operand ikinciye bölündüğünde kalan dır. Bölünme kesin olmadığında, sonuç aşağıdaki kurallarla belirlenir:<br/><br/>- Sağ operand sıfır ise, sonuç tanımsız.<br/><br/>- Her iki operands pozitif veya imzasız ise, sonuç olumludur.<br/><br/>- Eğer operand negatif ve sonuç kesin değilse, sonuç tanımlanır. (Aşağıdaki Microsoft'a özel bölüme bakın.)|

### <a name="microsoft-specific"></a>Microsoft'a özgü

Her iki operandın negatif olduğu bölmede, kesilme yönü 0'a doğrudur.

Her iki işlem de kalan işleçle bölünme halinde negatifse, sonuç temettü (ifadedeki ilk operand) ile aynı işarete sahiptir.

## <a name="examples"></a>Örnekler

Aşağıda gösterilen bildirimler aşağıdaki örnekler için kullanılır:

```
int i = 10, j = 3, n;
double x = 2.0, y;
```

Bu ifadede çarpma işleci kullanır:

```
y = x * i;
```

Bu durumda, `x` değeri 20.0 vermek `i` için çarpılır. Sonuç **çift** türü vardır.

```
n = i / j;
```

Bu örnekte, 10 3'e bölünür. Sonuç 0'a doğru kesilir ve yineci değeri 3'ü verir.

```
n = i % j;
```

Bu ifade, `n` 10'un 3'e bölündüğü tamsayı geri kalanını 1 atar.

**Microsoft'a Özgü**

Geri kalan ın işareti temettü işareti ile aynıdır. Örneğin:

```
50 % -6 = 2
-50 % 6 = -2
```

Her durumda, `50` `2` ve aynı işareti var.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[Çarpan İşleçleri ve Modulus İşleci](../cpp/multiplicative-operators-and-the-modulus-operator.md)
