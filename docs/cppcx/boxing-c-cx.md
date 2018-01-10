---
title: Kutulama (C + +/ CX) | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d953e35c0fe238dc8dee76ad6c2d5aab7a0ab1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="boxing-ccx"></a>Kutulama (C + +/ CX)
*Kutulama* bir değer türü değişkeni gibi kaydırma [Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)— veya gibi temel skaler bir tür `int`— değişkeni götürenbiryöntemegeçirildiğinderefsınıfında[Platform::Object ^](../cppcx/platform-object-class.md) girdi türü olarak.  
  
## <a name="passing-a-value-type-to-an-object-parameter"></a>Bir nesne için bir değer türü geçirme ^ parametresi  
 Açıkça türü için bir yöntem parametresi geçirmek için bir değişken kutusuna gerekmese [Platform::Object ^](../cppcx/platform-object-class.md), daha önce Kutulu değerleri aldığınızda açıkça geri özgün türe sahip.  
  
 [!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]  
  
### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Platform::IBox kullanarak\<T > boş değer atanabilen değer türlerini desteklemek için  
 C# ve Visual Basic boş değer atanabilen değer türleri kavramını destekler. C + +/ CX, kullanabileceğiniz `Platform::IBox<T>` boş değer atanabilen değer türü parametrelerini desteklemek genel yöntemler kullanıma sunmak için türü. Aşağıdaki örnek C + gösterir +/ C# çağıran bağımsız değişkenlerden biri null başarılı olduğunda null döndüren CX genel yöntem.  
  
 [!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]  
  
 Bir C# XAML istemci, onu şöyle kullanmasını sağlayabilirsiniz:  
  
```  
  
// C# client code  
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();  
    int? a = null;  
    int? b = 5;  
    var result = obj.Multiply(a,b); //result = null  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sistem türü (C + +/ CX)](../cppcx/type-system-c-cx.md)   
 [Atama (C + +/ CX)](../cppcx/casting-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)