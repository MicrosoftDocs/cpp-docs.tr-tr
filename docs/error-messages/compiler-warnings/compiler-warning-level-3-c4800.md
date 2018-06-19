---
title: Derleyici Uyarısı (Düzey 3) C4800 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4800
dev_langs:
- C++
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed4b14ae2f3af3218909d6cd4609f1f45d3d7cc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293640"
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