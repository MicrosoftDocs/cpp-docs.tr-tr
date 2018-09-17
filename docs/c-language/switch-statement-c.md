---
title: Statement (C) geçiş | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- switch
dev_langs:
- C++
helpviewer_keywords:
- switch keyword [C]
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d5a4598a83c448a36750dc1aac6b4a22ef3513f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704359"
---
# <a name="switch-statement-c"></a>switch Deyimi (C)
`switch` Ve **çalışması** deyimleri Yardım denetimi karmaşık koşullu ya da dal oluşturma işlemleri. `switch` Deyimi denetimi kendi gövdesi içindeki bir ifade aktarır.  
  
## <a name="syntax"></a>Sözdizimi

*Seçimi deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**geçiş (** *ifade* **)** *deyimi*  
  
*Etiketli deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Servis talebi***sabit-ifade***:***deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Varsayılan:***deyimi*  
  
Denetim özelliği deyime geçer **çalışması** *sabit-ifade* değeriyle eşleşen **geçiş (** *ifade* **)**. `switch` Deyimi herhangi bir sayıda içerebilir **çalışması** örnekleri, ancak hiçbir iki büyük/küçük harf sabitleri aynı `switch` deyimi aynı değere sahip olabilir. Deyim gövdesinin yürütülmesini seçili ifadede başlar ve gövde veya kadar sonuna kadar devam eder. bir **sonu** denetimi gövdenin dışında deyime aktarır.  
  
Kullanım `switch` deyimi genellikle görünür aşağıdakine benzer:  

```C
switch ( expression )
{
    // declarations
    // . . .
    case constant_expression:
        // statements executed if the expression equals the
        // value of this constant_expression
        break;
    default:
        // statements executed if expression does not equal
        // any case constant_expression
}
```

Kullanabileceğiniz **sonu** deyimi içinde belirli bir durumun işlenmesini sonlandırmak için `switch` deyimi ve dal sonuna `switch` deyimi. Olmadan **sonu**, program sonraki durumuna kadar deyim yürütmeye devam eder bir **sonu** veya deyimin sonuna ulaşıldı. Bazı durumlarda, bu devamlılık istenebilir.

**Varsayılan** hiçbir deyimi yürütüldüğünde **çalışması** *sabit-ifade* değerine eşittir **geçiş (**  *ifade* **)**. Varsa **varsayılan** deyimi atlanırsa ve hiçbir **çalışması** eşleşme bulunduğunda deyimlerinde hiçbiri `switch` gövdesi yürütülür. En fazla bir olabilir **varsayılan** deyimi. **Varsayılan** deyimi sonunda değil gelmesi; gövdesinde her yerde görünebilir `switch` deyimi. A **çalışması** veya **varsayılan** etiketi içinde yalnızca görüntülenebilir bir `switch` deyimi.

Türünü `switch` *ifade* ve **çalışması** *sabit-ifade* tam sayı olmalıdır. Her değer **çalışması** *sabit-ifade* deyim gövdesi içinde benzersiz olmalıdır.

**Çalışması** ve **varsayılan** etiketlerini `switch` deyim gövdesi yürütme deyiminin gövdesinde başladığı belirleyen ilk test önemlidir. Switch deyimleri iç içe olabilir. Statik değişkenlerin hiçbir yürütmeden önce başlatılır `switch` deyimleri.

> [!NOTE]
> Bildirimleri oluşturan bileşik deyim, kafası görünür `switch` gövdesi, ancak bildirimlerinde dahil başlatmalar yapılmaz. `switch` Deyime başlatmalar içeren satırları atlayarak gövdesi içindeki yürütülebilir bir deyimin için doğrudan denetim aktarır.

Aşağıdaki örnekler gösterir `switch` ifadeleri:

```C
switch( c )
{
    case 'A':
        capa++;
    case 'a':
        lettera++;
    default :
        total++;
}
```

Tüm üç deyimi `switch` , bu örnekte gövdesi yürütülür `c` eşittir `'A'` bu yana bir **sonu** deyimi, önce aşağıdaki durum görünmez. Yürütme denetimi, ilk deyime aktarılır (`capa++;`) ve gövde kalanında sırayla devam eder. Varsa `c` eşittir `'a'`, `lettera` ve `total` artırılır. Yalnızca `total` artırılır `c` eşit değildir `'A'` veya `'a'`.

```C
switch( i )
{
    case -1:
        n++;
        break;
    case 0 :
        z++;
        break;
    case 1 :
        p++;
        break;
}
```

Bu örnekte, bir **sonu** deyimi takip eden her deyiminin `switch` gövdesi. **Sonu** deyimi bir deyim yürütüldükten sonra gelen deyim gövdesi bir çıkış zorlar. Varsa `i` -1 olarak, yalnızca eşittir `n` artırılır. **Sonu** deyiminin sonrasındaki `n++;` yürütme denetimi, deyim gövdesi dışında kalan deyimleri atlayarak geçmesine neden olur. Benzer şekilde, varsa `i` 0 olarak, yalnızca eşittir `z` ; artırılır `i` 1, yalnızca eşittir `p` artırılır. En son **sonu** deyimi kesinlikle gerekli olmadığı, dışı denetim geçer beri bileşik deyim, ancak daha uçtaki gövdesi tutarlılık sağlamak için dahil edilmiştir.  
  
Tek bir deyimde birden çok gerçekleştirebilirsiniz **çalışması** etiketleri, aşağıdaki örnekte gösterildiği gibi:  
  
```C
case 'a' :  
case 'b' :  
case 'c' :  
case 'd' :  
case 'e' :  
case 'f' :  hexcvt(c);  
```  
  
Bu örnekte, *sabit-ifade* arasında herhangi bir harf eşittir `'a'` ve `'f'`, `hexcvt` işlevi çağrılır.  
  
**Microsoft'a özgü**  
  
Microsoft C, durum değeri sayısını sınırlamaz bir `switch` deyimi. Sayı yalnızca kullanılabilir bellekle sınırlıdır. ANSI C gerektiren en az 257 durum etiketi içinde izin bir `switch` deyimi.  
  
Microsoft C için varsayılan Microsoft genişletmelerinin etkinleştirilmiş olduğu. Bu uzantıları devre dışı bırakmak için /Za derleyici seçeneğini kullanın.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.

[switch Deyimi (C++)](../cpp/switch-statement-cpp.md)