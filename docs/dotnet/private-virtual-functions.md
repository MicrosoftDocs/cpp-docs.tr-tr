---
title: "Özel sanal işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- virtual functions, private
- derived classes, virtual functions
- access modifiers [C++], for class members
- member access [C++], virtual members
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b407bc469a345706f99cf5bad578f678e652a4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="private-virtual-functions"></a>Özel Sanal İşlevler
Türetilmiş sınıflarda özel sanal işlevler işlenme Visual C++ için C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Yönetilen Uzantılar'türetilmiş bir sınıf içinde geçersiz kılınması yeteneğini sanal işlev erişim düzeyini kısıtlamaz. Yeni sözdiziminde sanal işlev erişemezler bir temel sınıf sanal işlevi geçersiz kılınamaz. Örneğin:  
  
```  
__gc class MyBaseClass {  
   // inaccessible to a derived class   
   virtual void g();  
};  
  
__gc class MyDerivedClass : public MyBaseClass {  
public:  
   // okay in Managed Extensions; g() overrides MyBaseClass::g()  
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible  
   void g();  
};  
```  
  
 Bu tür bir tasarım yeni sözdizimi üzerine gerçek eşlemesi yok. Biri sadece temel sınıf üyelerinin - diğer bir deyişle, özel olmayan erişilebilir sahiptir. Devralınan yöntemlerin aynı erişimi taşımaları gerekmez. Bu örnekte, az bozucu değişiklik MyBaseClass üyesi olmaktır `protected`. Bu şekilde genel programın erişim yöntemine MyBaseClass ile hala yasaktır.  
  
```  
ref class MyBaseClass {  
protected:  
   virtual void g();  
};  
  
ref class MyDerivedClass : MyBaseClass {  
public:  
   virtual void g() override;  
};  
```  
  
 Unutmayın açık olmaması `virtual` yeni sözdizimi altında temel sınıf anahtar sözcüğü bir uyarı iletisi oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 