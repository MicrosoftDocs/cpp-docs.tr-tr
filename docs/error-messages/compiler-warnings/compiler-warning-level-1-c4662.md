---
title: Derleyici Uyarısı (düzey 1) C4662
ms.date: 11/04/2016
f1_keywords:
- C4662
helpviewer_keywords:
- C4662
ms.assetid: 7efda273-d04a-47b7-ad65-ff1ff94b5ffc
ms.openlocfilehash: ff8a2f73523802a7c62e999be00c77400fbc0f23
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051422"
---
# <a name="compiler-warning-level-1-c4662"></a>Derleyici Uyarısı (düzey 1) C4662

açık örnek oluşturma; Şablon-sınıf ' Identifier1 ', ' identifier2 ' öğesinin özelleştiritireceği bir tanıma sahip değil

Belirtilen şablon sınıfı bildirildi, ancak tanımlanmadı.

## <a name="example"></a>Örnek

```cpp
// C4662.cpp
// compile with: /W1 /LD
template<class T, int i> class MyClass; // no definition
template MyClass< int, 1>;              // C4662
```