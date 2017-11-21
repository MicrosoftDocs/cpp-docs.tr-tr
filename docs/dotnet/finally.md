---
title: Son olarak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 55e2b77fbbcc607d802c4ea9e54d7ef56d473bd5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="finally"></a>finally
Ek olarak `try` ve `catch` yan tümceleri, CLR özel durum destekler işleme bir `finally` yan tümcesi. Semantiğini özdeş `__finally` (SEH) işleme yapılandırılmış özel durum engelleyin. A `__finally` blok izleyin bir `try` veya `catch` bloğu.  
  
## <a name="remarks"></a>Açıklamalar  
 Amacı `finally` bloğu özel durum oluştu sonra kalan tüm kaynakları temizlemek için. Unutmayın `finally` blok her zaman yürütüldüğünde, bile hiçbir özel durum oluştu. `catch` Blok yönetilen bir özel durum oluşursa yalnızca yürütülebilir ilişkili içinde `try` bloğu.  
  
 `finally`bağlama duyarlı bir anahtar sözcüktür; bkz: [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, basit bir gösterir `finally` engelle:  
  
```  
// keyword__finally.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyException: public System::Exception{};  
  
void ThrowMyException() {  
   throw gcnew MyException;  
}  
  
int main() {  
   try {  
      ThrowMyException();  
   }  
   catch ( MyException^ e ) {  
      Console::WriteLine(  "in catch" );  
      Console::WriteLine( e->GetType() );  
   }  
   finally {  
      Console::WriteLine(  "in finally" );  
   }  
}  
```  
  
```Output  
in catch  
MyException  
in finally  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme](../windows/exception-handling-cpp-component-extensions.md)