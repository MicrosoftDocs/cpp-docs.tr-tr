---
title: "Dize değişmez değerlerini depolama | Microsoft Docs"
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
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bc3314e569a7229e3cf316b46e1a8df4c9bb722e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="storage-of-string-literals"></a>Dize Değişmez Değerlerini Depolama
Sabit değerli bir dize karakterlerini sırada bitişik bellek konumlara depolanır. Kaçış dizisi (gibi  **\\ \\**  veya  **\\"**) dize sabit değeri içinde tek bir karakter olarak sayılır. Bir null karakter (tarafından temsil edilen **\0** kaçış dizisi) otomatik olarak eklenir ve sonuna her dize değişmez değer işaretler. (Bu sistemdeki [çeviri aşaması](../preprocessor/phases-of-translation.md) 7.) Derleyici iki farklı adreslerde iki özdeş dizeleri depolayabilir değil olduğunu unutmayın. [/GF](../build/reference/gf-eliminate-duplicate-strings.md) aynı dize tek bir kopyasını yürütülebilir dosyaya yerleştirmek için derleyici zorlar.  
  
## <a name="remarks"></a>Açıklamalar  
 **Microsoft özel**  
  
 Statik depolama süresi dizelerine sahipsiniz. Bkz: [depolama sınıfları](../c-language/c-storage-classes.md) depolama süresi hakkında bilgi için.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Dize Değişmez Değerleri](../c-language/c-string-literals.md)