---
title: "Statement (C) için | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- for keyword [C]
ms.assetid: 560a8de4-19db-4868-9f18-dbe51b17900d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18c2b89e8c09ca7ddb6ba7f2cc02c9b400265a35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="for-statement-c"></a>for Deyimi (C)
**İçin** deyimi bir deyim yineleyin veya belirtilen sayıda bileşik deyim olanak sağlar. Gövdesi bir **için** deyimi, isteğe bağlı bir koşul yanlış olana kadar sıfır veya daha fazla kez yürütüldüğünde. İsteğe bağlı ifade içinde kullanabilir **için** başlatmak ve sırasında değerlerini değiştirmek için deyimi **için** deyiminin yürütme.  
  
## <a name="syntax"></a>Sözdizimi  
 *Yineleme deyimi*:  
 &nbsp;&nbsp;**için** **(** *init ifade*<sub>kabul</sub> **;** *koşullu ifade*<sub>kabul</sub> **;** *döngü ifade*<sub>kabul</sub> **)** *deyimi*  
  
 Yürütme işlemi bir **için** deyimi aşağıdaki gibi devam eder:  
  
1.  *İnit ifade*herhangi biri, değerlendirileceği durumunda. Bu döngünün başlatma belirtir. Tür sınırlaması yoktur *init ifade*.  
  
2.  *Koşullu ifade*herhangi biri, değerlendirileceği durumunda. Bu ifade aritmetik veya işaretçi türü olmalıdır. Her yinelemeden önce değerlendirilir. Üç sonuçları desteklenir:  
  
    -   Varsa *koşullu ifade* olan **true** (sıfır), *deyimi* yürütülür; ardından *döngü ifade*herhangi biri, değerlendirileceği,. *Döngü ifade* her yinelemeden sonra değerlendirilir. Tür sınırlaması yoktur. Yan etkiler düzende yürütülür. İşlem daha sonra yeniden değerlendirmesi ile başlar *koşullu ifade*.  
  
    -   Varsa *koşullu ifade* atlanırsa, *koşullu ifade* true ve tam olarak önceki paragrafta açıklanan yürütme devam eder olarak kabul edilir. A **için** deyimi olmadan bir *koşullu ifade* bağımsız değişkeni sonlandırır yalnızca bir **sonu** veya **dönmek** deyimi deyimi içinde Gövde yürütüldüğünde, veya bir **goto** (etiketli deyimi dışında **için** deyimi gövde) yürütülür.  
  
    -   Varsa *koşullu ifade* olan **false** (0) yürütülmesi **için** açıklamayı sonlandıran ve denetim geçirir program sonraki ifadesine.  
  
 A **için** deyimi de sonlandırır ne zaman bir **sonu**, **goto**, veya **dönmek** deyimi deyimi gövdesi içinde gerçekleştirilir. A **devam** deyiminde bir **için** döngüye neden *döngü ifade* değerlendirilecek. Zaman bir **sonu** deyimi içinde yürütüldüğünde bir **için** döngü, *döngü ifade* hesaplanan yürütülen ya da. Bu bildirimi  
  
```  
for( ;; )  
```  
  
 yalnızca ile çıkılması, sonsuz bir döngüde üretmek için her zamanki yolu bir **sonu**, **goto**, veya **dönmek** deyimi.  
  
## <a name="code"></a>Kod  
 Bu örnekte gösterilmiştir **için** deyimi:  
  
```  
// c_for.c  
int main()  
{  
   char* line = "H e  \tl\tlo World\0";  
   int space = 0;  
   int tab = 0;  
   int i;  
   int max = strlen(line);  
   for (i = 0; i < max; i++ )   
   {  
      if ( line[i] == ' ' )  
      {  
          space++;  
      }  
      if ( line[i] == '\t' )  
      {  
          tab++;  
      }  
   }  
  
   printf("Number of spaces: %i\n", space);  
   printf("Number of tabs: %i\n", tab);  
   return 0;  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
Number of spaces: 4  
Number of tabs: 2  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Deyimler](../c-language/statements-c.md)