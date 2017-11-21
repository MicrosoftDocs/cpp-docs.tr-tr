---
title: "Derleyici Uyarısı (düzey 1) C4377 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4377
dev_langs: C++
helpviewer_keywords: C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e52479aac07cdb31f62b20cb6c865b48b270c2bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4377"></a>Derleyici Uyarısı (düzey 1) C4377
Yerel türler varsayılan olarak özel; -d1PrivateNativeTypes kullanım dışı bırakıldı  
  
 Önceki sürümlerde, derlemeler içindeki yerel türler varsayılan ve belgelenmemiş, iç derleyici seçeneği ortak (**/d1PrivateNativeTypes**) özel hale getirmek için kullanıldı.  
  
 Tüm türleri, yerel ve CLR, artık özel bir bütünleştirilmiş varsayılan olan şekilde **/d1PrivateNativeTypes** artık gerekli değildir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4377 oluşturur.  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```