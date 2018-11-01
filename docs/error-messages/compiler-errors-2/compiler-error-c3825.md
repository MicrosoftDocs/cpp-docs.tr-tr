---
title: Derleyici Hatası C3825
ms.date: 11/04/2016
f1_keywords:
- C3825
helpviewer_keywords:
- C3825
ms.assetid: 18e204a1-f26e-42c6-8d74-2b49cc95f940
ms.openlocfilehash: ddb665dab303b3133d4018910c2142a20a889bb0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528641"
---
# <a name="compiler-error-c3825"></a>Derleyici Hatası C3825

'class': yönetilen bir ya da WinRTclass yalnızca yönetilen destek veya WinRTevents gerçekleştirebilirsiniz.

Yalnızca .NET olayları yönetilen sınıflar desteklenir. Yalnızca Windows çalışma zamanı olayları, Windows çalışma zamanı sınıflar desteklenir. Yönetilen kodda bu hatayı düzeltmek için tür parametresi değiştirme `event_source` ve `event_receiver` gelen `native` için `managed`. Alternatif olarak, özniteliğini kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3825 oluşturur ve bu sorunun nasıl gösterir:

```
// C3825a.cpp
// compile with: /clr
public delegate void del1();

[event_source(native)]           // To fix, change 'native' to 'managed' or delete this line
ref class CEventSrc
{
public:
   event del1^ event1;       // C3825

   void FireEvents() {
      event1();
   }
};

[event_receiver(native)]         // To fix, change 'native' to 'managed' or delete this line
ref class CEventRec
{
public:
   void handler1()
   {
      System::Console::WriteLine("Executing handler1().\n");
   }
   void HookEvents(CEventSrc^ pSrc)
   {
      pSrc->event1 += gcnew del1(this, &CEventRec::handler1);
   }
   void UnhookEvents(CEventSrc^ pSrc)
   {
      pSrc->event1 -= gcnew del1(this, &CEventRec::handler1);
   }
};

int main()
{
   CEventSrc^ pEventSrc = gcnew CEventSrc;
   CEventRec^ pEventRec = gcnew CEventRec;
   pEventRec->HookEvents(pEventSrc);
   pEventSrc->FireEvents();
   pEventRec->UnhookEvents(pEventSrc);
}
```