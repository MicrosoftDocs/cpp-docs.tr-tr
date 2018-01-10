---
title: "Olağan aritmetik dönüştürmeler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- arithmetic conversions [C++]
- type conversion [C++], arithmetic
- operators [C], arithmetic conversions
- data type conversion [C++], arithmetic
- conversions [C++], arithmetic
- arithmetic operators [C++], type conversions
ms.assetid: bfa49803-0efd-45d0-b987-111412a140d7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a73da6d96b0dc03fa3f4c4807d6a2dff4fef2879
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="usual-arithmetic-conversions"></a>Olağan Aritmetik Dönüştürmeler
Çoğu C işleçleri tür dönüştürmeleri için ortak bir türü bir ifadenin işlenenleri getirmek veya makine işlemlerinde kullanılan tamsayı boyutuna kısa değerler genişletmek için gerçekleştirin. C işleçleri tarafından gerçekleştirilen dönüşümleri belirli işleci ve işlenen veya işlenen türü bağlıdır. Ancak, birçok işleçleri kayan ve tam sayı türleri işlenen üzerinde benzer dönüşümleri gerçekleştirir. Bu dönüştürme "aritmetik dönüşümler." bilinen Uyumlu bir türde bir işlenen değer dönüştürülmesi değerine değişikliğe neden olmaz.  
  
 Aşağıda özetlenen aritmetik dönüşümler "olağan aritmetik dönüştürmeler." olarak adlandırılır Bu adımları aritmetik türü beklediğiniz ikili işleçler için uygulanır. Amacı, aynı zamanda sonuç türü olan bir ortak türü sonucu veren sağlamaktır. Hangi dönüşümleri gerçekte gerçekleşmesi belirlemek için aşağıdaki algoritması derleyici ikili işlemlerin ifadesinde uygulanır. Aşağıdaki adımlar bir öncelik sırası değildir.  
  
1.  Her iki işlenen türü ise `long double`, diğer işlenenin türü dönüştürülüp `long double`.  
  
2.  Yukarıdaki koşulu karşılanmadı ve her iki işlenen türü olup olmadığını **çift**, diğer işlenenin türü dönüştürülüp **çift**.  
  
3.  Yukarıdaki iki koşulları karşılanmadı ve her iki işlenen türü olup olmadığını **float**, diğer işlenenin türü dönüştürülüp **float**.  
  
4.  Yukarıdaki üç koşul karşılanmazsa (işlenenler yok türleri kayan biri), tam sayı dönüşümleri işlenen üzerinde şu şekilde gerçekleştirilir:  
  
    -   Her iki işlenen türü ise `unsigned long`, diğer işlenenin türü dönüştürülüp `unsigned long`.  
  
    -   Yukarıdaki koşulu karşılanmadı ve her iki işlenen türü olup olmadığını **uzun** ve diğer tür `unsigned int`, her iki işlenen türü için dönüştürülür `unsigned long`.  
  
    -   Yukarıdaki iki koşulları karşılanmadı ve her iki işlenen türü ise **uzun**, diğer işlenenin türü dönüştürülüp **uzun**.  
  
    -   Yukarıdaki üç koşulları karşılanmadı ve her iki işlenen türü ise `unsigned int`, diğer işlenenin türü dönüştürülüp `unsigned int`.  
  
    -   Yukarıdaki koşulların hiçbiri karşılanıyorsa, her iki işlenen türü için dönüştürülür `int`.  
  
 Aşağıdaki kod bu dönüştürme kurallarını gösterir:  
  
```  
float   fVal;  
double  dVal;  
int   iVal;  
unsigned long ulVal;  
  
dVal = iVal * ulVal; /* iVal converted to unsigned long  
                      * Uses step 4.  
                      * Result of multiplication converted to double   
                      */  
dVal = ulVal + fVal; /* ulVal converted to float  
                      * Uses step 3.  
                      * Result of addition converted to double   
                      */   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C İşleçleri](../c-language/c-operators.md)