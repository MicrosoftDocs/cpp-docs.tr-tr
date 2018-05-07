---
title: Arabirim üyesini açık geçersiz kılma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, explicit overrides
- overriding functions
- interface members, explicit overrides
- functions [C++], overriding
- explicit override of virtual function
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 811112d2721edccede6c7b4a278189fdec874523
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="explicit-override-of-an-interface-member"></a>Arabirim Üyesini Açık Geçersiz Kılma
Bir sınıftaki arabirim üyesini açık geçersiz kılma bildirme sözdizimi için Visual C++ C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Genellikle, bir arabirim üyesini - bir sınıf nesneleri bir arabirim tanıtıcısı üzerinden yönlendirildiği zaman kullanılır ve sınıf nesnelerine kullanıldığında, sınıf arabirimi üzerinden kullanılan bir arabirimi uygulayan bir sınıf içinde iki örneğini sağlamak istediğinizde. Örneğin:  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 Yönetilen Uzantılar'biz bunu arabirimi adı ile tam yöntemin adının arabirim yönteminin açık bir bildirimini sağlayarak yapın. Nitelenmemiş sınıfı özgü örneğidir. Bu durum dönüş değerini gereksinimini ihtiyacını ortadan kaldırır `Clone`, bu örnekte, açık bir örneği üzerinden çağrıldığında `R`.  
  
 Yeni sözdiziminde Yönetilen Uzantılar sözdizimi değiştirir genel bir geçersiz kılma mekanizması sunulmuştur. Bizim örneğimizde gibi yazılması:  
  
```  
public ref class R : public ICloneable {  
public:  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R  
   virtual R^ Clone();  
};  
```  
  
 Bu düzeltme açıkça kılınmasını arabirim üyesi olmasını gerektirir sınıfı içinde benzersiz bir ad verilir. Burada, garip adını sağladığınız `InterfaceClone`. Hala aynı - aracılığıyla yapılan bir çağrı davranıştır `ICloneable` arabirimi çağırır yeniden adlandırılmış `InterfaceClone`, while türünde bir nesne çağrısıyla `R` ikinci çağırır `Clone` örneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfta veya arabirimde üye bildirimleri (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Açık Geçersiz Kılmalar](../windows/explicit-overrides-cpp-component-extensions.md)