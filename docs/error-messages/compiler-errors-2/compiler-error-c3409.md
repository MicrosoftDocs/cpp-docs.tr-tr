---
title: "Derleyici Hatası C3409 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3409
dev_langs: C++
helpviewer_keywords: C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 083c71cdaa1cb3fe1959ce59e16e3d1e6949159d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3409"></a>Derleyici Hatası C3409
boş öznitelik blok izin verilmiyor  
  
 Köşeli ayraçlar derleyici tarafından yorumlanan bir [özniteliği](../../windows/cpp-attributes-reference.md) bloğu, ancak hiçbir öznitelik bulunamadı.  
  
 Lambda ifadesi tanımının bir parçası olarak köşeli kullandığınızda derleyici bu hata oluşmasına neden olabilir. Bu hata, derleyici köşeli ayraç lambda ifadesi veya bir öznitelik blok tanımının bir parçası olup olmadığını belirleyemez oluşur. Lambda ifadeleri hakkında daha fazla bilgi için bkz: [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Köşeli ayraçlar bir öznitelik blok parçası ise:  
  
    1.  Bir veya daha fazla öznitelikler özniteliği bloğundaki sağlar.  
  
    2.  Öznitelik blok kaldırın.  
  
2.  Köşeli ayraçlar lambda ifadesi parçası ise:  
  
    1.  Lambda ifadesi geçerli sözdizimi kurallarına uyduğundan emin olun.  
  
         Lambda ifadesi sözdizimi hakkında daha fazla bilgi için bkz: [Lambda ifadesi sözdizimi](../../cpp/lambda-expression-syntax.md).  
  
    2.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3409 oluşturur.  
  
```  
// C3409.cpp  
// compile with: /c  
#include <windows.h>  
[]   // C3409  
class a {};  
  
// OK  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface x {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class b : public x {};  
```  
  
## <a name="example"></a>Örnek  
 Lambda ifadesi kullandığından, aşağıdaki örnek C3409 oluşturur `mutable` belirtimi, ancak parametre listesi sağlamaz. Derleyici köşeli ayraç lambda ifadesi veya bir öznitelik blok tanımının bir parçası olup olmadığını belirleyemez.  
  
```  
// C3409b.cpp  
  
int main()  
{  
   [] mutable {}();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [özniteliği](../../windows/cpp-attributes-reference.md)   
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)   
 [Lambda ifadesi sözdizimi](../../cpp/lambda-expression-syntax.md)