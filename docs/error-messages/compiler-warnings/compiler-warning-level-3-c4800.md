---
title: "Derleyici Uyarısı (Düzey 3) C4800 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4800
dev_langs: C++
helpviewer_keywords: C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 464550a8d56e6b3407fa41b811a7214b4aee529c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4800"></a>Derleyici Uyarısı (Düzey 3) C4800  
  
> '*türü*': değer bool 'true' veya 'false' (Performans Uyarısı) zorlama  
  
Bir değeri olmayan bu uyarı oluşturulur `bool` atanmış veya türüne yüklenen `bool`. Atayarak bu ileti genellikle, kaynaklanır `int` değişkenleri `bool` değişkenleri nerede `int` değişken yalnızca değerler içerdiğinden **true** ve **yanlış**ve olabilir tür olarak yeniden bildirilen `bool`. İfade türü kullanacak şekilde yeniden yazma, `bool`, sonra da ekleyebilirsiniz "`!=0`" ifadesine sağlayan ifade türü `bool`. İfade türü atama `bool` tasarım gereğidir uyarıyı devre dışı bırakılmaz.  
  
Bu uyarı artık Visual Studio 2017 içinde oluşturulur.  
  
## <a name="example"></a>Örnek
  
 Aşağıdaki örnek C4800 oluşturur ve düzeltmek gösterilmektedir:  
  
```cpp  
// C4800.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
  
   // To fix, instead try:  
   // bool i = 0;  
  
   bool j = i;   // C4800  
   j++;  
}  
```