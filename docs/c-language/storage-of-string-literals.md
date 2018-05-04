---
title: Dize değişmez değerlerini depolama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d87998f7e9d579c012f5db2f38f20886c1e74c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="storage-of-string-literals"></a>Dize Değişmez Değerlerini Depolama
Sabit değerli bir dize karakterlerini sırada bitişik bellek konumlara depolanır. Kaçış dizisi (gibi **\\ \\** veya  **\\"**) dize sabit değeri içinde tek bir karakter olarak sayılır. Bir null karakter (tarafından temsil edilen **\0** kaçış dizisi) otomatik olarak eklenir ve sonuna her dize değişmez değer işaretler. (Bu sistemdeki [çeviri aşaması](../preprocessor/phases-of-translation.md) 7.) Derleyici iki farklı adreslerde iki özdeş dizeleri depolayabilir değil olduğunu unutmayın. [/GF](../build/reference/gf-eliminate-duplicate-strings.md) aynı dize tek bir kopyasını yürütülebilir dosyaya yerleştirmek için derleyici zorlar.  
  
## <a name="remarks"></a>Açıklamalar  
 **Microsoft özel**  
  
 Statik depolama süresi dizelerine sahipsiniz. Bkz: [depolama sınıfları](../c-language/c-storage-classes.md) depolama süresi hakkında bilgi için.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Dize Değişmez Değerleri](../c-language/c-string-literals.md)