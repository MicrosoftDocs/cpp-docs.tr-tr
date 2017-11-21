---
title: "__uuidof işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
dev_langs: C++
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 54a21ead5f47bd931bae912cb4ca28a8d900a75b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="uuidof-operator"></a>__uuidof İşleci
**Microsoft özel**  
  
 İfadeye bağlı GUID alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      __uuidof (  
   expression   
)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *İfade* , bu tür veya bir değişkeni bu tür bir şablonu özelleştirilmiş tür adı, işaretçi, başvuru veya dizi türünde olabilir. Derleyici ekli GUID bulmak için kullanabileceğiniz sürece bağımsız değişkeni geçerli değil.  
  
 Bu iç, özel bir durum olduğunda ya da **0** veya **NULL** bağımsız değişken olarak sağlanır. Bu durumda, `__uuidof` sıfırları oluşan bir GUID döndürür.  
  
 İlişkili GUID ayıklamak için bu anahtar sözcük kullanın:  
  
-   Nesne tarafından [UUID](../cpp/uuid-cpp.md) genişletilmiş öznitelik.  
  
-   Bir kitaplık bloğu ile oluşturulan [Modülü](../windows/module-cpp.md) özniteliği.  
  
> [!NOTE]
>  Hata ayıklama derlemesi içinde `__uuidof` her zaman bir nesnede dinamik olarak (çalışma zamanı) başlatır. Bir sürümde yapıdaki `__uuidof` statik olarak (derleme zamanında) bir nesne başlatabilirsiniz.  
  
## <a name="example"></a>Örnek  
 (Ole32.lib ile derlenen) aşağıdaki kod modülü özniteliği ile oluşturulan bir kitaplık blok UUID'si görüntülenir:  
  
```  
// expre_uuidof.cpp  
// compile with: ole32.lib  
#include "stdio.h"  
#include "windows.h"  
  
[emitidl];  
[module(name="MyLib")];  
[export]  
struct stuff {  
   int i;  
};  
  
int main() {  
   LPOLESTR lpolestr;  
   StringFromCLSID(__uuidof(MyLib), &lpolestr);  
   wprintf_s(L"%s", lpolestr);  
   CoTaskMemFree(lpolestr);  
}  
```  
  
## <a name="comments"></a>Açıklamalar  
 Kitaplık adı olduğu artık kapsamda durumlarda __LIBID kullanabilirsiniz\_ yerine `__uuidof`. Örneğin:  
  
```  
StringFromCLSID(__LIBID_, &lpolestr);  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)