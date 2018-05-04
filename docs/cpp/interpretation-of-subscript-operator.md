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
ms.openlocfilehash: 9bba312c6969acf95be8899f58f65e31c75386c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="interpretation-of-subscript-operator"></a>Alt Simge İşleci Yorumu
Gibi diğer işleçler alt simge işleci (**[]**) kullanıcı tarafından yeniden tanımlanabilir. Alt simge işlecinin varsayılan davranışı, aşırı yüklenmemişse, aşağıdaki yöntemi kullanarak dizi adını ve alt simgeyi birleştirmektir:  
  
 \*((*dizi adı*) + (*alt simge*))  
  
 İşaretçi türleri içeren tüm toplama işlemlerinde olduğu gibi; ölçeklendirme, tür boyutunu ayarlamak için otomatik olarak gerçekleştirilir. Bu nedenle, sonuç değeri değil *alt simge* kökeni baytlar *dizi adı*; bunun yerine, bu *alt simge*dizisinin th öğesi. (Bu dönüştürme hakkında daha fazla bilgi için bkz: [ADDITIVE işleçleri](../cpp/additive-operators-plus-and.md).)  
  
 Benzer şekilde, çok boyutlu diziler için aşağıdaki yöntem kullanılarak adres türetilir:  
  
 **((**   
 ***dizi adı* ) + ()**   
 ***alt simge* 1***max*2  *\* max*3 *.. .max*n) **+** *alt simge*2  *\* max*3 *.. .max*n).   biçimindeki telefon numarasıdır. biçimindeki telefon numarasıdır. *+* *alt simge*n))  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Diziler](../cpp/arrays-cpp.md)