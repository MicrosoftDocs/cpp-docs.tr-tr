---
title: Derleyici Uyarısı (düzey 1) C4377 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4377
dev_langs:
- C++
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef049f85cd17bfeaba243b84da9fca93ae4036b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274787"
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