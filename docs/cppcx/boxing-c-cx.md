---
title: Kutulama (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ed67496189388b869d7d9491ac4baad3de810ca
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751984"
---
# <a name="boxing-ccx"></a>Kutulama (C + +/ CX)
*Kutulama* bir değer türü değişkeni gibi sarmalama [Windows::Foundation::DateTime](https://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)— ya da temel bir skalar türü gibi `int`— değişken alan bir yönteme geçildiğinde bir başvuru sınıfındaki [ Platform::Object ^](../cppcx/platform-object-class.md) giriş türü olarak.  
  
## <a name="passing-a-value-type-to-an-object-parameter"></a>Bir değer türü bir nesneye geçirme ^ parametre  
 Bir değişken türü için bir yöntem parametresi geçirmek için açıkça kutusunda zorunda değilsiniz [Platform::Object ^](../cppcx/platform-object-class.md), daha önce Kutulu değerleri aldığınızda açıkça yeniden orijinal türüne sahip.  
  
 [!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]  
  
### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Platform::ıbox kullanarak\<T > boş değer atanabilen değer türleri desteklemek için  
 C# ve Visual Basic'te boş değer atanabilen değer türleri kavramını destekler. C + +/ CX, kullanabileceğiniz `Platform::IBox<T>` null yapılabilir değer türü parametrelerini destekleyen genel yöntemleri açığa türü. Aşağıdaki örnekte gösterilmektedir C + +/ C# çağıran bağımsız değişkenlerden biri null başarılı olduğunda, null döndüren CX genel yöntem.  
  
 [!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]  
  
 C# XAML istemcisinde, onu şöyle raporlarını kullanabilirsiniz:  
  
```  
  
// C# client code  
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();  
    int? a = null;  
    int? b = 5;  
    var result = obj.Multiply(a,b); //result = null  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi (C + +/ CX)](../cppcx/type-system-c-cx.md)   
 [Atama (C + +/ CX)](../cppcx/casting-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)