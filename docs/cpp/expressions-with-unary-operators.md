---
title: "Birli işleçli ifadeler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44485f0c5749db36ececd2061955f9956cb49ece
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="expressions-with-unary-operators"></a>Birli İşleçli İfadeler
Birli işleçleri deyimde yalnızca bir işlenen hareket. Birli işleçleri aşağıdaki gibidir:  
  
-   [İndirection işleci (*)](../cpp/indirection-operator-star.md)  
  
-   [Address-of işleci (&)](../cpp/address-of-operator-amp.md)  
  
-   [Birli artı işleci (+)](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [Tekli değilleme işleci (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [Mantıksal değilleme işleci (!)](../cpp/logical-negation-operator-exclpt.md)  
  
-   [Birinin tamamlama işleci (~)](../cpp/one-s-complement-operator-tilde.md)  
  
-   [Önek arttırma işleci (++)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [Önek azaltma işleci (-)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [Atama işleci (.)](../cpp/cast-operator-parens.md)  
  
-   [sizeof işleci](../cpp/sizeof-operator.md)  
  
-   [__uuidof işleci](../cpp/uuidof-operator.md)  
  
-   [__alignof işleci](../cpp/alignof-operator.md)  
  
-   [New işleci](../cpp/new-operator-cpp.md)  
  
-   [delete işleci](../cpp/delete-operator-cpp.md)  
  
 Bu işleçlere sağdan sola birleşim vardır. Birli ifadeler genellikle bir sonek veya birincil ifade önündeki sözdizimi içerir.  
  
 Olası form birli ifadelerin verilmiştir.  
  
-   *sonek ifade*  
  
-   `++`*Tek terimli ifadesi*  
  
-   `--`*Tek terimli ifadesi*  
  
-   *birli işleç* *cast ifadesi*  
  
-   `sizeof`*Tek terimli ifadesi*  
  
-   `sizeof(`*türü adı*`)`  
  
-   `decltype(`*ifade*`)`  
  
-   *ayırma ifade*  
  
-   *ayırmayı kaldırma ifade*  
  
 Tüm *sonek ifade* olarak kabul edilir bir *Tek terimli ifadesi*, ve herhangi bir birincil ifade olduğu kabul edildiği için bir *sonek ifade*, tüm birincil ifadeler olduğu kabul bir *Tek terimli ifadesi* de. Daha fazla bilgi için bkz: [sonek ifadeleri](../cpp/postfix-expressions.md) ve [birincil ifadeler](../cpp/primary-expressions.md).  
  
 A *birli işleç* bir veya daha fazla aşağıdaki simgelerden oluşur:`* & + - ! ~`  
  
 *Cast ifadesi* türünü değiştirmek için isteğe bağlı bir cast ile birli ifadesidir. Daha fazla bilgi için bkz: [atama işleci: ()](../cpp/cast-operator-parens.md).  
  
 Bir *ifade* herhangi bir ifade olabilir. Daha fazla bilgi için bkz: [ifadeleri](../cpp/expressions-cpp.md).  
  
 *Ayırma ifade* başvurduğu `new` işleci. *Ayırmayı kaldırma ifade* başvurduğu `delete` işleci. Daha fazla bilgi için bu konunun önceki kısımlarında bağlantılara bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade Türleri](../cpp/types-of-expressions.md)