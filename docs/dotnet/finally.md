---
title: Son olarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd357c8eeed9eddc6940ce02de6e5d2b4f8c68d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Özel Durum İşleme](../windows/exception-handling-cpp-component-extensions.md)