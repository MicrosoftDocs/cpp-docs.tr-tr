---
title: "Derleyici Hatası C3850 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3850
dev_langs: C++
helpviewer_keywords: C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe77bb54a72c340a2fbf2a986a4346397cff11fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3850"></a>Derleyici Hatası C3850
'char': geçersiz bir karakter evrensel-karakter-name belirtir  
  
 Evrensel karakter adları aralık 0-10FFFF geçerli Unicode kod noktası temsil etmelidir olarak temsil karakter. Evrensel karakter adları Unicode yedek aralık, D800 DFFF veya kodlanmış yedek çifti değer içeremez. Derleyici, geçerli kodundan çifti otomatik noktası yedek oluşturur.  
  
 C derlenmiş kodda, evrensel karakter adları 0000-009F aralığında bir karakter olarak temsil edilmeyebilir dahil 0024 ('$'), özel durumları ile 0040 (' @') ve 0060 ('' ').  
  
 C++ derlenmiş kod içinde bir evrensel karakter adı bir dize veya karakter değişmez değer geçerli bir Unicode kod noktası kullanabilir. Bir hazır değer dışında evrensel karakter adları aralık 0000 001F ya da 007F-009F, her ikisi de dahil, bir denetim karakteri temsil etmiyor veya temel kaynak karakteri üyesi ayarlayın.  Daha fazla bilgi için bkz: [karakter kümesi](../../cpp/character-sets2.md).  
  
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