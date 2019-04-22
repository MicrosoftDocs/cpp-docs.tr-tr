---
title: Derleyici Hatası C3397
ms.date: 11/04/2016
f1_keywords:
- C3397
helpviewer_keywords:
- C3397
ms.assetid: a8536e87-79c4-4ed7-bd96-42704d06391f
ms.openlocfilehash: c6ca48eb53cf1c6d661a201fa8c4d2539669b9bf
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777425"
---
# <a name="compiler-error-c3397"></a>Derleyici Hatası C3397

Toplama başlatma varsayılan bağımsız değişkenler izin verilmiyor

Bir dizi yanlış bildirildi.  Bkz: [diziler](../../extensions/arrays-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3397 oluşturur.

```
// C3397.cpp
// compile with: /clr
// /clr /c
void Func(array<int> ^p = gcnew array<int> { 1, 2, 3 });   // C3397
void Func2(array<int> ^p = gcnew array<int> (3));   // OK

int main() {
   array<int> ^p = gcnew array<int> { 1, 2, 3};   // OK
}
```