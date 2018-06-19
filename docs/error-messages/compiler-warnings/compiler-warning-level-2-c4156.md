---
title: Derleyici Uyarısı (Düzey 2) C4156 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4156
dev_langs:
- C++
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 249d90712b4a8b02f10deaa4d87cdbb7a7c17ae3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296455"
---
# <a name="compiler-warning-level-2-c4156"></a>Derleyici Uyarısı (Düzey 2) C4156
dizi biçimi 'Delete'; kullanmadan bir dizi ifadesi silme Değiştirilen dizi biçimi  
  
 Dizi olmayan tür **silme** bir dizi silemezsiniz. Derleyici çevrilen **silmek** dizi form.  
  
 Bu uyarı, yalnızca Microsoft uzantıları altında (/Ze) oluşur.  
  
## <a name="example"></a>Örnek  
  
```  
// C4156.cpp  
// compile with: /W2  
int main()  
{  
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];  
   delete array; // C4156, changed by compiler to "delete [] array;"  
}  
```