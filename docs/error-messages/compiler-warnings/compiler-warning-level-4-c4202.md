---
title: Derleyici Uyarısı (düzey 4) C4202
ms.date: 11/04/2016
f1_keywords:
- C4202
helpviewer_keywords:
- C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
ms.openlocfilehash: 0d5e7dd45b58f1231c39565bfd74c5895096a8b7
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541639"
---
# <a name="compiler-warning-level-4-c4202"></a>Derleyici Uyarısı (düzey 4) C4202

Standart olmayan uzantı kullanıldı: '... ': ad listesindeki prototip parametresi geçersiz

Eski stil işlev tanımı değişken bağımsız değişkenleri içerir. Bu tanımlar ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında bir hata oluşturur.

## <a name="example"></a>Örnek

```c
// C4202.c
// compile with: /W4
void func( a, b, ...)   // C4202
int a, b;
{}

int main()
{
}
```