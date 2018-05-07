---
title: Derleyici Hatası C3850 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: bb2068a283fc54a86b09f2af05b177f2151e940b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3850"></a>Derleyici Hatası C3850
'char': geçersiz bir karakter evrensel-karakter-name belirtir  
  
 Evrensel karakter adları aralık 0-10FFFF geçerli Unicode kod noktası temsil etmelidir olarak temsil karakter. Evrensel karakter adları Unicode yedek aralık, D800 DFFF veya kodlanmış yedek çifti değer içeremez. Derleyici, geçerli kodundan çifti otomatik noktası yedek oluşturur.  
  
 C derlenmiş kodda, evrensel karakter adları 0000-009F aralığında bir karakter olarak temsil edilmeyebilir dahil 0024 ('$'), özel durumları ile 0040 (' @') ve 0060 ('' ').  
  
 C++ derlenmiş kod içinde bir evrensel karakter adı bir dize veya karakter değişmez değer geçerli bir Unicode kod noktası kullanabilir. Bir hazır değer dışında evrensel karakter adları aralık 0000 001F ya da 007F-009F, her ikisi de dahil, bir denetim karakteri temsil etmiyor veya temel kaynak karakteri üyesi ayarlayın.  Daha fazla bilgi için bkz: [karakter kümesi](../../cpp/character-sets.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3850 oluşturur ve düzeltmek gösterilmektedir:  
  
```cpp  
// C3850.cpp  
int main() {  
   int \u0019 = 0;   // C3850, not in allowed range for an identifier  
   const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair  
   const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point  
}  
```