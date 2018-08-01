---
title: Alt simge işleci yorumu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- subscript operator [C++], interpretation of
- arrays [C++], subscripting
- interpreting subscript operators [C++]
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75659730198e09a172625c54bfcbdd54b7a9f857
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404794"
---
# <a name="interpretation-of-subscript-operator"></a>Alt Simge İşleci Yorumu
Alt simge işleci diğer işleçler gibi (**[]**) kullanıcı tarafından tekrar tanımlanabilir. Alt simge işlecinin varsayılan davranışı, aşırı yüklenmemişse, aşağıdaki yöntemi kullanarak dizi adını ve alt simgeyi birleştirmektir:  
  
 \*((*dizi adı*) + (*alt simge*))  
  
 İşaretçi türleri içeren tüm toplama işlemlerinde olduğu gibi; ölçeklendirme, tür boyutunu ayarlamak için otomatik olarak gerçekleştirilir. Bu nedenle, sonuç değeri değil *alt simge* kaynağı bayt *dizi adı*; bunun yerine, bu *alt simge*dizinin th öğesi. (Bu dönüştürme hakkında daha fazla bilgi için bkz. [toplama işleçleri](../cpp/additive-operators-plus-and.md).)  
  
 Benzer şekilde, çok boyutlu diziler için aşağıdaki yöntem kullanılarak adres türetilir:  
  
 **((**   
 ***dizi adı* ) + ()**   
 ***alt simge* 1***max*2  *\* max*3 *.. .max*n) **+** *alt simge*2  *\* max*3 *.. .max*n).   biçimindeki telefon numarasıdır. biçimindeki telefon numarasıdır. *+* *alt simge*n))  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Diziler](../cpp/arrays-cpp.md)