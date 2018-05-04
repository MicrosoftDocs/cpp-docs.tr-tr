---
title: C çarpma işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1810cc9dd7a991e302e0e9e2db69f65aebebc613
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-multiplicative-operators"></a>C Çarpma İşleçleri
Çarpma işleçleri çarpma gerçekleştirin (**\***), bölme (**/**) ve geri kalan (`%`) işlemleri.  
  
 **Sözdizimi**  
  
 *ifade çarpma*:  
 *Cast ifadesi*  
  
 *ifade çarpma***\****cast ifadesi*   
  
 *ifade çarpma***/***cast ifadesi*   
  
 *ifade çarpma***%***cast ifadesi*   
  
 Kalan işlecinin işlenenleri (`%`) tam sayı olması gerekir. Çarpma (**\***) ve bölme (**/**) işleçleri integral veya kayan türü işlenenler alabilir; işlenen türleri farklı olabilir.  
  
 Çarpma işleçleri olağan aritmetik dönüştürmeler işlenen üzerinde gerçekleştirin. Sonuç türü dönüştürmeden sonra işlenen türüdür.  
  
> [!NOTE]
>  Çarpma işleçleri tarafından gerçekleştirilen dönüştürmeler taşma veya yetersiz kalma koşulları sağlamadığından, çarpma işleminin sonucu dönüştürme sonrası işlenenlerin türünde gösterilmezse bilgiler kaybolabilir.  
  
 C çarpma işleçleri aşağıda açıklanmıştır:  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|**\***|Çarpma işleci çarpılacağı iki işlenenleri neden olur.|  
|**/**|Bölme işleci ilk işleneni ikinciye ayrılmasına neden olur. Aşağıdaki kurallara göre iki tamsayı işlenen ayrılır ve sonucu bir tamsayı değilse kesilir:|  
||-0 bölme sonucu göre ANSI C standardı tanımlanmamıştır. Microsoft C Derleyici derleme zamanında ya da çalışma zamanı sırasında bir hata oluşturur.|  
||-Her iki işlenen pozitif veya imzasız olursa, sonuç 0 doğru kesilir.|  
||-Her iki işlenen negatifse olup işlemin sonucunu en büyük tamsayı cebirsel sayının küçük veya buna eşit veya sıfırdan büyük veya eşit cebirsel sayının en küçük tamsayı tanımlanan uygulamasıdır. (Aşağıdaki Microsoft Specific bölümüne bakın.)|  
|`%`|İlk işlenen saniye ayrıldığında kalan işleci kalan sonucudur. Bölme filtresinin olduğunda sonuç aşağıdaki kurallara göre belirlenir:|  
||-Sağ işleneni sıfır ise, sonuç tanımlanmamıştır.|  
||-Her iki işlenen pozitif veya imzasız olursa, pozitif bir sonucudur.|  
||-Her iki işlenen negatif ve sonucu filtresinin ise, sonuç tanımlanan uygulamasıdır. (Aşağıdaki Microsoft Specific bölümüne bakın.)|  
  
 **Microsoft özel**  
  
 Her iki işlenen negatif olduğu bölme ile kesme yönünü doğru 0'dır.  
  
 Her iki işlem kalan işleci bölme negatif ise sonucu (ifadesindeki ilk işlenen) bölünen aynı işarete sahiptir.  
  
 **SON Microsoft özel**  
  
## <a name="examples"></a>Örnekler  
 Aşağıda gösterilen bildirimleri ilişkin aşağıdaki örneklerde kullanılır:  
  
```  
int i = 10, j = 3, n;  
double x = 2.0, y;  
```  
  
 Bu bildirimi çarpma işleci kullanır:  
  
```  
y = x * i;  
```  
  
 Bu durumda, `x` çarpılır `i` 20.0 değeri vermek için. Sonuçta **çift** türü.  
  
```  
n = i / j;  
```  
  
 Bu örnekte, 10 3 ile ayrılmıştır. Sonucun tamsayı değeri 3 sağlayan 0 doğru kesilir.  
  
```  
n = i % j;  
```  
  
 Bu ifade atar `n` tamsayı geri kalanı, 1, 3 ile 10 ayrıldığında.  
  
 **Microsoft özel**  
  
 Kalan oturum bölünen oturum ile aynıdır. Örneğin:  
  
```  
50 % -6 = 2  
-50 % 6 = -2  
```  
  
 Her durumda `50` ve `2` aynı işarete sahip.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çarpan İşleçleri ve Modulus İşleci](../cpp/multiplicative-operators-and-the-modulus-operator.md)