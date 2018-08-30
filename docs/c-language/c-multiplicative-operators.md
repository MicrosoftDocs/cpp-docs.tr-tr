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
ms.openlocfilehash: 0be97e271ce8b500274d0e2ab1f271183ef7c238
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200000"
---
# <a name="c-multiplicative-operators"></a>C Çarpma İşleçleri
Çarpma işleçleri çarpma gerçekleştirin (<strong>\*</strong>), bölme (**/**) ve kalanı (**%**) işlemleri.  
  
## <a name="syntax"></a>Sözdizimi

*ifade çarpma*:  
&nbsp;&nbsp;&nbsp;&nbsp;*Cast ifadesi*  
&nbsp;&nbsp;&nbsp;&nbsp;*ifade çarpma* <strong>\*</strong> *atama ifadesi*  
&nbsp;&nbsp;&nbsp;&nbsp;*ifade çarpma* **/** *atama ifadesi*  
&nbsp;&nbsp;&nbsp;&nbsp;*ifade çarpma* **%** *atama ifadesi*

Kalan işlecinin işlenenleri (**%**) tam sayı olmalıdır. Çarpma (<strong>\*</strong>) ve bölme (**/**) işleçleri, tamsayı veya kayan-türü işlenen alabilir; işlenen türleri farklı olabilir.  
  
Çarpma işleçleri olağan aritmetik dönüştürmeler işlenenler üzerinde gerçekleştirin. Sonuç türü dönüştürme işleminden sonra işlenenler türüdür.  
  
> [!NOTE]
>  Çarpma işleçleri tarafından gerçekleştirilen dönüştürmeler taşma veya yetersiz kalma koşulları sağlamadığından, çarpma işleminin sonucu dönüştürme sonrası işlenenlerin türünde gösterilmezse bilgiler kaybolabilir.  
  
 C çarpma işleçleri aşağıda açıklanmıştır:  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|<strong>\*</strong>|Çarpma işleci iki işlenenleri çarpılmasına neden olur.|  
|**/**|Bölme işleci, birinci işlenenin ikinci tarafından Bölünecek neden olur. Aşağıdaki kurallara göre iki tamsayı işlenen ayrılır ve sonucu bir tamsayı değilse kesilir:<br/><br/>-ANSI C standardına göre 0 ile bölme sonucu tanımsızdır. Microsoft C derleyicisi, derleme zamanı veya çalışma zamanı sırasında bir hata oluşturur.<br/><br/>-Her iki işlenen de pozitif veya işaretsiz ise, sonuç 0 doğru kesilir.<br/><br/>-Her iki işlenen negatif ise, işlemin sonucunu en büyük tamsayı cebirsel sayının küçük veya ona eşit olduğundan veya en küçük tamsayı değerinden büyük veya eşittir cebirsel sayının tanımlanan uygulamasıdır. (Microsoft Specific bölümüne bakın.)|  
|**%**|Birinci işlenenin ikinci bölündüğünde kalan işleci kalan sonucudur. Bölme işlemi filtresinin olduğunda sonuç aşağıdaki kurallara göre belirlenir:<br/><br/>-Sağ işlenen sıfır ise, sonuç tanımsızdır.<br/><br/>-Her iki işlenen de pozitif veya işaretsiz ise sonuç pozitif olur.<br/><br/>-Ya da bir işlenen negatif ise ve sonuç bölümünü kesin değilse, uygulama tanımlı sonucudur. (Microsoft Specific bölümüne bakın.)|  
  
 **Microsoft'a özgü**  
  
 İki işlenenden negatif olduğu sıfıra bölme, kesilme yönü doğru 0 ' dir.  
  
 Her iki işlem kalan işleci bölme negatif ise, sonuç bölünen (ifadesindeki ilk işlenen) aynı işarete sahiptir.  
  
 **END Microsoft özgü**  
  
## <a name="examples"></a>Örnekler  
 Aşağıda gösterilen bildirimler için aşağıdaki örneklere kullanılır:  
  
```  
int i = 10, j = 3, n;  
double x = 2.0, y;  
```  
  
 Bu deyim, çarpma işleci kullanır:  
  
```  
y = x * i;  
```  
  
 Bu durumda, `x` çarpılır `i` 20.0 değeri vermek için. Sonuç **çift** türü.  
  
```  
n = i / j;  
```  
  
 Bu örnekte, 10 3 ile ayrılır. Sonuç, tamsayı değeri 3 sonuçlanmıyor 0 doğru kesilir.  
  
```  
n = i % j;  
```  
  
 Bu bildirimi atar `n` tamsayı geri kalanı, 3 ile 10 bölündüğünde 1.  
  
 **Microsoft'a özgü**  
  
 Kalan oturum bölünen işareti ile aynıdır. Örneğin:  
  
```  
50 % -6 = 2  
-50 % 6 = -2  
```  
  
 Her durumda `50` ve `2` aynı işarete sahip.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çarpan İşleçleri ve Modulus İşleci](../cpp/multiplicative-operators-and-the-modulus-operator.md)