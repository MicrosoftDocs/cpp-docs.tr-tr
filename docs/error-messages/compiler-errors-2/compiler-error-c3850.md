---
title: Derleyici Hatası C3850
ms.date: 09/05/2018
f1_keywords:
- C3850
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
ms.openlocfilehash: 9cd0428726f92c7347b162f74b46035f99cc2d3c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380961"
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