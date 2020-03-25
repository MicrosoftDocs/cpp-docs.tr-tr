---
title: Derleyici hatası C3850
ms.date: 09/05/2018
f1_keywords:
- C3850
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
ms.openlocfilehash: 5de7994e8bf46105e94271ab29bf9e27f1da3e76
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165578"
---
# <a name="compiler-error-c3850"></a>Derleyici hatası C3850

> '*char*': bir evrensel karakter adı geçersiz bir karakter belirtiyor

## <a name="remarks"></a>Açıklamalar

Evrensel karakter adları olarak temsil edilen karakterler, 0-10FFFF aralığındaki geçerli Unicode kod noktalarını temsil etmelidir. Evrensel karakter adı, Unicode vekil aralığında, D800-DFFF veya kodlanmış bir vekil çiftinde bir değer içeremez. Derleyici, geçerli bir kod noktasından otomatik olarak yedek çift oluşturur.

C olarak derlenen kodda, evrensel bir karakter adı, 0024 (' $ '), 0040 ('\@') ve 0060 (' ' ') özel durumları ile 0000-009F (dahil) aralığında bir karakteri temsil edebilir.

Olarak C++derlenen kodda, bir evrensel karakter adı bir dize veya karakter sabit değerinde herhangi bir geçerli Unicode kod noktasını kullanabilir. Bir sabit değer dışında, bir evrensel karakter adı 0000-001F veya 007F-009F aralıklarında bir denetim karakteri veya temel kaynak karakter kümesinin bir üyesini temsil edebilir.  Daha fazla bilgi için bkz. [karakter kümeleri](../../cpp/character-sets.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3850 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3850.cpp
int main() {
   int \u0019 = 0;   // C3850, not in allowed range for an identifier
   const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair
   const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point
}
```
