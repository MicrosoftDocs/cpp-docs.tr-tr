---
description: 'Daha fazla bilgi edinin: C Multipereptive Işleçleri'
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
ms.openlocfilehash: 61689435c5e76238feba26d5a49ffe3530798f88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300274"
---
# <a name="c-multiplicative-operators"></a>C Çarpma İşleçleri

Çarpma işleçleri çarpma ( <strong>\*</strong> ), Bölüm ( **/** ) ve kalan ( **%** ) işlemleri gerçekleştirir.

## <a name="syntax"></a>Syntax

*çoğulereptive-ifade*: &nbsp; &nbsp; &nbsp; &nbsp; *cast-* ifade &nbsp; &nbsp; &nbsp; &nbsp; *çoğulereptive-Expression* <strong>\*</strong> *cast-ifade* &nbsp; &nbsp; &nbsp; &nbsp; *çoğulereptive-Expression* **/** *cast-* Expression &nbsp; &nbsp; &nbsp; &nbsp; *çoğulereptive-Expression* **%** *cast-ifade*

Geri kalan işlecin işlenenleri ( **%** ) tamsayı olmalıdır. Çarpma ( <strong>\*</strong> ) ve bölüm ( **/** ) işleçleri tamsayı veya kayan tür işlenenleri alabilir; işlenen türleri farklı olabilir.

Çarpma işleçleri, işlenenler üzerinde Olağan aritmetik dönüştürmeleri gerçekleştirir. Sonucun türü, dönüştürmeden sonra işlenen türüdür.

> [!NOTE]
> Çarpma işleçleri tarafından gerçekleştirilen dönüştürmeler taşma veya yetersiz kalma koşulları sağlamadığından, çarpma işleminin sonucu dönüştürme sonrası işlenenlerin türünde gösterilmezse bilgiler kaybolabilir.

C çarpma işleçleri aşağıda açıklanmıştır:

|İşleç|Açıklama|
|--------------|-----------------|
|<strong>\*</strong>|Çarpma işleci, iki işleneninin çarpılmasına neden olur.|
|**/**|Bölme işleci, İlk işlenenin ikinciden bölünmesine neden olur. İki tamsayı işleneni ayrılmışsa ve sonuç bir tamsayı değilse, aşağıdaki kurallara göre kesilir:<br/><br/>-0 ile bölme sonucu, ANSI C standardına göre tanımlanmamıştır. Microsoft C derleyicisi, derleme zamanında veya çalışma zamanında bir hata oluşturur.<br/><br/>-Her iki işlenen de pozitif veya işaretsiz ise, sonuç 0 ' a doğru atılır.<br/><br/>-Her iki işlenen de negatif ise, işlemin sonucunun cebirsel bölümünün en büyük veya eşit olduğu en büyük tamsayıdır veya Cebirsel bölümünün büyük veya eşit olduğu en küçük tamsayının uygulama tanımlı olduğunu belirtir. (Aşağıdaki Microsoft 'a özgü bölümüne bakın.)|
|**%**|Geri kalan işlecin sonucu, ilk işlenen ikinciden bölündüğünde geri kalan işleçtir. Bölme geçersiz olduğunda, sonuç aşağıdaki kurallara göre belirlenir:<br/><br/>-Sağ işlenen sıfırsa, sonuç tanımsızdır.<br/><br/>-Her iki işlenen de pozitif veya işaretsiz ise, sonuç pozitif olur.<br/><br/>-Herhangi bir işlenen negatifse ve sonuç tam değilse, sonuç uygulama tanımlı olur. (Aşağıdaki Microsoft 'a özgü bölümüne bakın.)|

### <a name="microsoft-specific"></a>Microsoft'a özgü

Her iki işlenenin de negatif olduğu bölümde, kesilmenin yönü 0 ' a düşer.

Her iki işlem de kalan işleçle birlikte bırakılırsa, sonuç bölünmeyle aynı işarete sahiptir (ifadedeki ilk işlenen).

## <a name="examples"></a>Örnekler

Aşağıda gösterilen bildirimler aşağıdaki örnekler için kullanılır:

```
int i = 10, j = 3, n;
double x = 2.0, y;
```

Bu ifade çarpma işlecini kullanır:

```
y = x * i;
```

Bu durumda, `x` `i` 20,0 değerini vermek için ile çarpılır. Sonucun türü vardır **`double`** .

```
n = i / j;
```

Bu örnekte, 10 3 ' ü bölünmüştür. Sonuç 0 ' a doğru kesilir ve 3. tamsayı değeri atılır.

```
n = i % j;
```

Bu ifade, `n` 10 ' un 3 ' i bölündüğünde, 1 tamsayı kalanı atar.

**Microsoft'a Özgü**

Kalanın işareti, bölünme işaretiyle aynıdır. Örneğin:

```
50 % -6 = 2
-50 % 6 = -2
```

Her durumda `50` ve `2` aynı işarete sahip olmalıdır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çarpma Işleçleri ve mod Işleci](../cpp/multiplicative-operators-and-the-modulus-operator.md)
