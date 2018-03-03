---
title: C sabit ifadeleri | Microsoft Docs
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
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 596f558ea5c22f1850800d95b0d4ad0b5edd6a8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-constant-expressions"></a>C Sabit İfadeleri
Bir sabit ifadesine derleme zamanında zaman çalıştırmamanız değerlendirilir ve bir sabit kullanılabilir herhangi bir yerde kullanılabilir. Sabit ifade türü için gösterilebilir değerleri aralığı içinde bir sabit değerlendirilmelidir. Bir sabit ifadesine can işlenenleri tamsayı sabitleri, karakter sabitleri, kayan nokta sabitleri, numaralandırma sabitleri olabilir atamaları, yazın `sizeof` ifadeleri ve diğer sabit ifadeler.  
  
## <a name="syntax"></a>Sözdizimi  
 *Sabit ifadesi*:  
 *Koşullu ifade*  
  
 *Koşullu ifade*:  
 *OR ifadesi mantıksal*  
  
 *OR ifadesi mantıksal* **?**  *ifade* **:***koşullu ifade*   
  
 *ifade*:  
 *atama ifadesi*  
  
 *ifade* **,***atama ifadesi*   
  
 *atama ifadesi*:  
 *Koşullu ifade*  
  
 *Tek terimli ifadesi atama işleci atama ifadesi*  
  
 *atama işleci*: biri  
 **= \*= /= %= += -= <\<= >>= &= ^= &#124;=**  
  
 Terminal dışı yapısı bildirimcisi, numaralandırıcı, doğrudan bildirimcisi, doğrudan Özet bildirimcisi ve etiketli deyim içeren *sabit ifadesi* nonterminal.  
  
 Tam sayı sabit bir ifade bit alanı üyesi bir yapısı, bir numaralandırma sabit değeri, bir dizi boyutu veya değerini boyutunu belirtmek için kullanılması gereken bir **durumda** sabit.  
  
 Önişlemci yönergeleri kullanılan sabit ifadeler ek kısıtlamalar geçerlidir. "Kısıtlı sabit ifadeler." sonuç olarak, bilinen Kısıtlı bir sabit ifadesine içeremez `sizeof` ifadeleri, numaralandırma sabitleri herhangi türü veya kayan türü sabitleri atamaları yazın. Ancak, özel sabit ifade içeriyor `defined (` *tanımlayıcısı*`)`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlenenler ve İfadeler](../c-language/operands-and-expressions.md)