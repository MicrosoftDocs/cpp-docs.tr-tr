---
title: "Sekizlik ve onaltılık karakter belirtimleri | Microsoft Docs"
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
- octal characters
- hexadecimal characters
ms.assetid: 9264f3ec-46b8-41a5-b21a-8f7ed0a11871
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf3a27dc61543482d1d6484d0edd4b5e1bb04373
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="octal-and-hexadecimal-character-specifications"></a>Sekizlik ve Onaltılık Karakter Belirtimleri
Sıra  **\\**  *ooo* ASCII herhangi bir karakter belirtebilirsiniz anlamına gelir karakter kümesi olarak üç basamaklı sekizli karakter kodu. Sekizli tamsayının sayısal değeri, istediğiniz karakter veya geniş karakter değerini belirtir.  
  
 Benzer şekilde, dizisi **\x***SSS* herhangi bir ASCII karakter bir onaltılı karakter kodu belirtmenize olanak tanır. Örneğin, ASCII geri karakteri normal C kaçış sırası olarak verebilirsiniz (**\b**), veya olarak kod **\010** (sekizlik) veya **\x008** (onaltılı).  
  
 Sekizli bir çıkış dizisinde yalnızca 0 ile 7 arasındaki sayıları kullanabilirsiniz. Sekizli çıkış dizileri, asla üç basamaktan uzun olamaz ve sekizlik bir rakam olmayan ilk karakterle sonlandırılır. Üç sayının tümünü kullanmanız gerekmese de, en az birini kullanmanız gerekir. Örneğin, sekizli gösterimidir **\10** ASCII geri karakter ve **\101** bir ASCII haliyle A harfi için grafik.  
  
 Benzer şekilde, onaltılı çıkış dizisi için en az bir sayı kullanmanız gerekir, ancak ikinci ve üçüncü sayıyı atlayabilirsiniz. Bu nedenle, onaltılık çıkış dizisi geri karakter ya da belirtebilirsiniz **\x8**, **\x08**, veya **\x008**.  
  
 Sekizlik ya da onaltılık çıkış dizisi değerinin türü için gösterilebilir değerler aralığında olmalıdır **imzasız char** karakter sabiti ve türü için `wchar_t` için joker karakter sabiti. Bkz: [çok baytlı ve geniş karakterler](../c-language/multibyte-and-wide-characters.md) joker karakter sabitleri hakkında bilgi için.  
  
 Sekizli çıkış sabitlerinden farklı olarak, bir çıkış dizisinde bulunabilecek onaltılı basamaklar sınırsızdır. Onaltılı bir çıkış dizisi, onaltılı olmayan ilk karakterde sonlandırılır. Onaltılık basamak harfleri içerdiğinden **bir** aracılığıyla **f**, bakım kullandı, kaçış sırası sonlandırır hedeflenen basamaklı emin olmak için. Karışıklığı önlemek için, bir makro tanımına sekizli veya onaltılı karakter tanımları koyabilirsiniz:  
  
```  
#define Bell '\x07'  
```  
  
 Onaltılı değerler için, doğru değeri net şekilde göstermek üzere dize bölünebilir:  
  
```  
"\xabc"    /* one character  */  
"\xab" "c" /* two characters */  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Karakter Sabitleri](../c-language/c-character-constants.md)