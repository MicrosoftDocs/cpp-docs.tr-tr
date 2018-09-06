---
title: Derleyici Hatası C3850 | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3850
dev_langs:
- C++
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: daa4b6128672b47891c563acfd4399952a17e7e6
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894544"
---
# <a name="compiler-error-c3850"></a>Derleyici Hatası C3850

> '*char*': bir evrensel karakter adı geçersiz bir karakter belirtiyor

## <a name="remarks"></a>Açıklamalar

Evrensel karakter adları geçerli aralık 0-10FFFF Unicode kod noktaları temsil etmelidir olarak temsil edilen karakter. Evrensel karakter adı Unicode vekil aralığı, D800 DFFF ya da bir kodlanmış vekil çifti bir değer içeremez. Derleyici vekil çifti geçerli bir kod noktası otomatik olarak oluşturur.

C derlenmiş kod içinde bir evrensel karakter adı 0000-009f arasındaki aralıktaki bir karakter olarak temsil edilmeyebilir 0024 ('$'), özel durumları ile kapsamlı 0040 ('\@') ve 0060 ('' ').

C++ derlenmiş kod içinde bir evrensel karakter adı geçerli bir Unicode kod noktasını bir dize veya karakter sabiti kullanabilir. Bir sabit değer dışında bir evrensel karakter adı aralık 0000 001F ya da 007F-009f arasındaki, her ikisi de dahil, bir denetim karakteri temsil etmeyebilir veya temel kaynak karakter kümesi.  Daha fazla bilgi için [karakter kümesi](../../cpp/character-sets.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3850 oluşturur ve bu sorunun nasıl gösterir:

```cpp
// C3850.cpp
int main() {
   int \u0019 = 0;   // C3850, not in allowed range for an identifier
   const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair
   const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point
}
```