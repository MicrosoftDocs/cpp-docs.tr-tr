---
title: "Statement (C) geçiş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: switch
dev_langs: C++
helpviewer_keywords: switch keyword [C]
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b66e9f40e3fb7f4c9a6c9f6fcb9bcd9c2a45fdd3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="switch-statement-c"></a>switch Deyimi (C)
`switch` Ve **durumda** deyimleri Yardım denetim karmaşık koşullu ve dallanma işlemler. `switch` Deyimi deyimi kendi gövdesi içinde denetim aktarır.  
  
## <a name="syntax"></a>Sözdizimi  
 *Seçim deyimi*:  
 **geçiş (** *ifade* **)** *deyimi*  
  
 *Etiketli deyim*:  
 **Servis talebi***sabit ifadesi***:***deyimi*   
  
 **Varsayılan:***deyimi*   
  
 Denetim geçirir ifadesine özelliği **durum** *sabit ifadesi* değeri ile eşleşen **geçiş (** *ifade* **)**. `switch` Deyimi herhangi bir sayıda içerebilir **durum** örnekleri, ancak aynı içinde iki bir servis talebi sabit yok `switch` deyimi aynı değere sahip olabilir. Yürütme deyimi gövdesinin seçili ifadesine başlar ve gövde veya kadar sonuna kadar devam eder bir **sonu** deyimi denetimi gövdesi dışında aktarır.  
  
 Kullanımı `switch` deyimi genellikle arar aşağıdakine benzer:  
  
 `switch`( *ifade* )  
  
 **{**  
  
 *bildirimleri*  
  
 biçimindeki telefon numarasıdır.  
  
 biçimindeki telefon numarasıdır.  
  
 biçimindeki telefon numarasıdır.  
  
 **Servis talebi** *sabit ifadesi* **:**  
  
 *ifade eşitse yürütülen deyimleri*  
  
 *Bu sabit ifadesi değeri*  
  
 biçimindeki telefon numarasıdır.  
  
 biçimindeki telefon numarasıdır.  
  
 biçimindeki telefon numarasıdır.  
  
 **BREAK;**  
  
 **Varsayılan:**  
  
 *ifade eşit olmadığı durumlarda yürütülen deyimleri*  
  
 *herhangi büyük bir sabit ifade*  
  
 **}**  
  
 Kullanabileceğiniz **sonu** deyimi içinde belirli bir durumu işlenmesi sona erdirmek için `switch` deyimi ve sonuna dala `switch` deyimi. Olmadan **sonu**, sonraki durumuna kadar ifadeler çalıştırmasını program devam bir **sonu** veya deyim sonuna ulaşıldı. Bazı durumlarda, bu devamlılık istenebilir.  
  
 **Varsayılan** deyimi yoksa yürütüldüğünde **durum** *sabit ifadesi* değerine eşit olan **geçiş (**  *ifade* **)**. Varsa **varsayılan** deyimi atlanırsa ve hiçbir **durum** eşleşme bulunduğunda, ifadeler hiçbiri `switch` gövde çalıştırılır. En çok bir olabilir **varsayılan** deyimi. **Varsayılan** deyimi sonunda değil gelen; gövdesinde herhangi bir yerde görünebilir `switch` deyimi. A **durum** veya **varsayılan** etiketi içinde yalnızca görünebilir bir `switch` deyimi.  
  
 Türü `switch` *ifade* ve **durum** *sabit ifadesi* tam sayı olması gerekir. Her değeri **durum** *sabit ifadesi* deyimi gövdesi içinde benzersiz olmalıdır.  
  
 **Durum** ve **varsayılan** etiketleri `switch` deyimi gövde yürütme deyiminin gövdesinde başladığı belirleyen ilk test önemli. Switch ifadeleri iç içe. Tüm statik değişkenler hiçbir yürütmeden önce başlatılır `switch` deyimleri.  
  
> [!NOTE]
>  Bildirimleri bileşik deyim oluşturan başı görünür `switch` gövde ancak bildirimlerinde dahil başlatmaları yapılmaz. `switch` Deyimi doğrudan başlatmaları içeren satırları atlayarak gövdesi içinde yürütülebilir bir ifade için Denetim aktarır.  
  
 Aşağıdaki örnekler göstermektedir `switch` deyimleri:  
  
```  
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
  
 Tüm üç bilgilerinin `switch` Bu örnek gövdesinde çalışıp çalışmadığını `c` eşittir `'A'` bu yana bir **sonu** deyimi önce şu durumda görünmez. Yürütme denetimi ilk ifadesine transfer (`capa++;`) ve gövde kalanında sırayla devam eder. Varsa `c` eşittir `'a'`, `lettera` ve `total` artırılır. Yalnızca `total` olmazsa artırılır `c` eşit değil `'A'` veya `'a'`.  
  
```  
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
  
 Bu örnekte, bir **sonu** deyimi izleyen her deyiminin `switch` gövdesi. **Sonu** deyimi bir deyim yürütüldükten sonra bir çıkış deyimi gövdesinden zorlar. Varsa `i` -1 olarak, yalnızca eşittir `n` artırılır. **Sonu** deyiminden `n++;` yürütme denetimi kalan ifadeler atlayarak deyimi gövde dışında geçmesine neden olur. Benzer şekilde, varsa `i` 0 olarak yalnızca eşittir `z` ; olmazsa artırılır `i` 1'e, yalnızca eşittir `p` artırılır. En son **sonu** deyimi kesinlikle gerekli değildir, dışı denetim geçirir beri bileşik deyim, ancak sonunda gövde tutarlılık için eklenmiştir.  
  
 Tek bir deyimde birden çok taşıyabilir **durumda** etiketleri, aşağıdaki örnekte gösterildiği gibi:  
  
```  
case 'a' :  
case 'b' :  
case 'c' :  
case 'd' :  
case 'e' :  
case 'f' :  hexcvt(c);  
```  
  
 Bu örnekte, *sabit ifadesi* arasında herhangi bir harf eşittir `'a'` ve `'f'`, `hexcvt` işlevi çağrılır.  
  
 **Microsoft özel**  
  
 Microsoft C case değerlerini sayısını sınırlamaz bir `switch` deyimi. Yalnızca kullanılabilir bellek ile sınırlıdır. ANSI C gerektiren en az 257 durum etiketi içinde izin verilmeyecek bir `switch` deyimi.  
  
 Microsoft C için Microsoft uzantıları etkinleştirildiğini varsayılandır. Bu uzantıları devre dışı bırakmak için /Za derleyici seçeneği kullanın.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [switch deyimi (C++)](../cpp/switch-statement-cpp.md)