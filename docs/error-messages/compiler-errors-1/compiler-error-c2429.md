---
title: "Derleyici Hatası C2429 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2429
dev_langs: C++
helpviewer_keywords: C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f263673e6b325557694b26b1fd71e86c22029d05
ms.sourcegitcommit: 78f3f8208d49b7c1d87f4240f4a1496b7c29333e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/17/2017
---
# <a name="compiler-error-c2429"></a>Derleyici Hatası C2429

> '*dil özelliği*'derleyici bayrağı gerektirir'*derleyici seçeneği*'

Dil özelliği belirli derleyici seçeneği desteği gerektirir.

Hata **C2429: dil özelliği 'iç içe-ad-tanımı' gerektirir derleyici bayrağı ' / std:c ++ 17'** tanımlamak çalışırsanız oluşturulan bir *bileşik ad alanı*, bir veya daha fazla bilgi içeren bir ad alanı Visual Studio 2015 güncelleştirme 5'te başlayan kapsam iç içe geçmiş ad alanı adları. (Visual Studio 2017 sürüm 15.3, içinde **/Std: c ++ Son** anahtarı gereklidir.) Bileşik ad alanı tanımları C++ C ++ 17 önce izin verilmez. Bileşik ad alanı tanımları derleyici destekleyen zaman [/Std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) derleyici seçeneği belirtildi:

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
