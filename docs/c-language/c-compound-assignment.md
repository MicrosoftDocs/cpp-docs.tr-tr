---
title: "C bileşik atama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operators [C], assignment
- compound assignment operators
- assignment operators, compound
ms.assetid: db7b5893-cd56-4f1c-9981-5a024200ab63
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b8b9166c1beae167f6d31913c3df10a8f57bbef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-compound-assignment"></a>C Bileşik Atama
Bileşik atama işleçleri basit atama işleci başka bir ikili işleç ile birleştirin. Bileşik atama işleçleri ek operatör tarafından belirtilen işlemi gerçekleştirmek, sonra sol işleneni sonucu atayın. Örneğin, bir bileşik atama ifadesi gibi  
  
```  
  
expression1  
+=  
expression2  
  
```  
  
 olarak anladım  
  
```  
  
expression1  
=  
expression1  
+  
expression2  
  
```  
  
 Bileşik atama ifadeyi hesaplar ancak bileşik atama ifadesi genişletilmiş sürüme eşdeğer olmadığından *İfade1* genişletilmiş sürüm değerlendirir sırasında yalnızca bir kez,  *İfade1* iki kez: Ek işlemi ve atama işlemi.  
  
 Bileşik atama işlecinin işlenenleri kayan veya tamsayı türünde olmalıdır. Her bileşik atama işleci karşılık gelen ikili işleç gerçekleştirir ve buna göre işlenenleri türlerini kısıtlar dönüşümleri gerçekleştirir. Toplama atama (`+=`) ve çıkarma Ataması (**-=**) işleçleri ayrıca sol işleneni durumda sağ işleneni Tamsayı türünde olmalıdır, işaretçi türü vardır. Bileşik atama işleminin sonucunu, sol işleneni türü ve değeri vardır.  
  
```  
#define MASK 0xff00  
  
n &= MASK;  
```  
  
 Bit düzeyinde kapsayıcı-ve işlem gerçekleştirilir Bu örnekte, `n` ve `MASK`, ve sonucu atandığı `n`. Bildirim sabiti `MASK` ile tanımlanmış bir [#define](../preprocessor/hash-define-directive-c-cpp.md) önişlemci yönergesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Atama İşleçleri](../c-language/c-assignment-operators.md)