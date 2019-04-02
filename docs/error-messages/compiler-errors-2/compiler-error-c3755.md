---
title: Derleyici Hatası C3755
ms.date: 11/04/2016
f1_keywords:
- C3755
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
ms.openlocfilehash: 5d1260138bfdbc318817c336077eef326b62f8b8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767437"
---
# <a name="compiler-error-c3755"></a>Derleyici Hatası C3755

'temsilci': bir temsilci tanımlanamıyor

A [temsilci (C++ bileşen uzantıları)](../../extensions/delegate-cpp-component-extensions.md) bildirimi yapıldı ancak tanımlanmadı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3755 oluşturur.

```
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

## <a name="example"></a>Örnek

Bir temsilci şablonu oluşturmaya çalışırsanız C3755 da meydana gelebilir. Aşağıdaki örnek, C3755 oluşturur.

```
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```