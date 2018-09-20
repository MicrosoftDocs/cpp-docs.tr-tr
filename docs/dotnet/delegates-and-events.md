---
title: Temsilciler ve olaylar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 26b67cdce8d52cba7d02f182f0582e20d0303c33
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373314"
---
# <a name="delegates-and-events"></a>Temsilciler ve Olaylar

Temsilciler ve olaylar bildirme yolu, Visual C++ için C++ için Yönetilen Uzantılar'dan değişti.

Aşağıdaki örnekte gösterildiği gibi çift alt çizgi artık gereklidir. Aşağıda bir örnek kod Yönetilen Uzantılar:

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

Olaylar (ve temsilciler) başvuru türleridir hat kullanımı nedeniyle Temizle yeni sözdiziminde olduğu (`^`).  Olaylar, hem bir açık bildiriminin sözdizimi hem de önceki kodda gösterilen Önemsiz form destekler. Açık formda kullanıcının belirttiği `add`, `raise`, ve `remove` olayla ilişkili yöntemler. (Yalnızca `add` ve `remove` yöntemleri gereklidir; `raise` yöntemi, isteğe bağlıdır.)

Yönetilen Uzantılar altında bu yöntemleri sağlarsanız, açık olay bildiriminde de sağlamaz, ancak mevcut değil olay adına karar vermeniz gerekir. Her yöntem formunda belirtilen `add_EventName`, `raise_EventName`, ve `remove_EventName`Yönetilen Uzantılar'belirtiminden alınan aşağıdaki örnekte gibi:

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

Aşağıdaki çevirinin gösterdiği gibi bildirimi yeni sözdizimini basitleştirir. Bir olayı iki belirtir veya üç yöntem içindeki bir çifti küme ayraçlarının içine ve hemen olay ve ilişkili temsilci türünü bildiriminden sonra aşağıda gösterildiği gibi yerleştirilir:

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

[Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[temsilci (C++ Bileşen Uzantıları)](../windows/delegate-cpp-component-extensions.md)<br/>
[event](../windows/event-cpp-component-extensions.md)