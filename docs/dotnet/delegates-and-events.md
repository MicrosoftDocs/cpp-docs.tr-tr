---
title: Temsilciler ve olaylar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __event keyword [C++]
- delegate keyword [C++]
- delegates [C++], upgrading from Managed Extensions for C++
- __delegate keyword
- events [C++], upgrading from Managed Extensions for C++
- event keyword [C++]
ms.assetid: 3505c626-7e5f-4492-a947-0e2248f7b84a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e332c24d30d0439705b6be5e0748518f6537478d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="delegates-and-events"></a>Temsilciler ve Olaylar
Temsilciler ve olaylar bildirme yolu C++ için Visual C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Aşağıdaki örnekte gösterildiği gibi çift alt çizgi artık gereklidir. Yönetilen Uzantılar örnek bir kod şöyledir:  
  
```  
__delegate void ClickEventHandler(int, double);  
__delegate void DblClickEventHandler(String*);  
  
__gc class EventSource {  
   __event ClickEventHandler* OnClick;    
   __event DblClickEventHandler* OnDblClick;    
};  
```  
  
 Yeni sözdiziminde aynı kod şu şekilde görünür:  
  
```  
delegate void ClickEventHandler( int, double );  
delegate void DblClickEventHandler( String^ );  
  
ref class EventSource {  
   event ClickEventHandler^ OnClick;   
   event DblClickEventHandler^ OnDblClick;   
};  
```  
  
 Olaylar (ve temsilciler) başvuru türleridir hat kullanımı nedeniyle temizleyin yeni sözdiziminde olduğu (`^`).  Olaylar, açık bildirim sözdizimi ve önceki kodda gösterildiği Önemsiz form destekler. Açık formda, kullanıcının belirttiği `add`, `raise`, ve `remove` olayla ilişkili yöntemler. (Yalnızca `add` ve `remove` yöntemleri gereklidir; `raise` yöntemdir isteğe bağlı.)  
  
 Yönetilen Uzantılar altında bu yöntemleri sağlarsanız, ayrıca açık olay bildiriminde sağlamaz, ancak mevcut değil olayı için bir ad üzerinde karar vermeniz gerekir. Her yöntem biçiminde belirtilir `add_EventName`, `raise_EventName`, ve `remove_EventName`, Yönetilen Uzantılar belirtiminden alınan aşağıdaki örnekteki gibi:  
  
```  
// explicit implementations of add, remove, raise  
public __delegate void f(int);  
public __gc struct E {  
   f* _E;  
public:  
   E() { _E = 0; }  
  
   __event void add_E1(f* d) { _E += d; }  
  
   static void Go() {  
      E* pE = new E;  
      pE->E1 += new f(pE, &E::handler);  
      pE->E1(17);   
      pE->E1 -= new f(pE, &E::handler);  
      pE->E1(17);   
   }  
  
private:  
   __event void raise_E1(int i) {  
      if (_E)  
         _E(i);  
   }  
  
protected:  
   __event void remove_E1(f* d) {  
      _E -= d;  
   }  
};  
```  
  
 Aşağıdaki çeviri gösterdiği gibi yeni sözdizimi bildirimi basitleştirir. Bir olay iki belirtir veya üç yöntem bir çift köşeli parantez içinde içine ve aşağıda gösterildiği gibi hemen olayının ve onun ilişkili temsilci türü bildirimi sonra yerleştirilir:  
  
```  
public delegate void f( int );  
public ref struct E {  
private:  
   f^ _E; // delegates are also reference types  
  
public:  
   E() {  // note the replacement of 0 with nullptr!  
      _E = nullptr;   
   }  
  
   // the new aggregate syntax of an explicit event declaration  
   event f^ E1 {  
   public:  
      void add( f^ d ) {  
         _E += d;  
      }  
  
   protected:  
      void remove( f^ d ) {  
         _E -= d;  
      }  
  
   private:  
      void raise( int i ) {  
         if ( _E )  
            _E( i );  
      }  
   }  
  
   static void Go() {  
      E^ pE = gcnew E;  
      pE->E1 += gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
      pE->E1 -= gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfta veya arabirimde üye bildirimleri (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Temsilci (C++ bileşen uzantıları)](../windows/delegate-cpp-component-extensions.md)   
 [event](../windows/event-cpp-component-extensions.md)