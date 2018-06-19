---
title: Derleyici Uyarısı (Düzey 3) C4191 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4191
dev_langs:
- C++
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 892bf76a8480e573a71e768fbe24778e7e66f88b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291498"
---
# <a name="compiler-warning-level-3-c4191"></a>Derleyici Uyarısı (Düzey 3) C4191
'işlem başına işleci': 'gerekli türüne' 'türünden ifadesinin' güvensiz dönüştürme  
  
 İşlev işaretçileri ilgili çeşitli işlemler güvenli olmadığı kabul edilir:  
  
-   Farklı çağırma kurallarını türleriyle işlevi.  
  
-   Farklı işlev türleriyle kuralları döndür.  
  
-   Bağımsız değişken veya return türleriyle farklı boyutlarda, türü kategorilerini ve sınıflandırmalarını.  
  
-   Farklı bağımsız değişken listesi uzunlukları (üzerinde `__cdecl`, yalnızca daha kısa listesi, hatta daha uzun listeden dönüştürme daha kısa ise varargs).  
  
-   Veri işaretçisine (dışında **void\***) takma adlı bir işlev işaretçisi karşı.  
  
-   Üzerinde bir hata veya uyarı verecek herhangi bir tür fark bir `reinterpret_cast`.  
  
 Sonuç işaretçi aracılığıyla bu işlev çağırma programınızı çökmesine neden olabilir.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4191 oluşturur:  
  
```  
// C4191.cpp  
// compile with: /W3 /clr  
#pragma warning(default: 4191)  
  
void __clrcall f1() { }  
void __cdecl   f2() { }  
  
typedef void (__clrcall * fnptr1)();  
typedef void (__cdecl   * fnptr2)();  
  
int main() {  
   fnptr1 fp1 = static_cast<fnptr1>(&f1);  
   fnptr2 fp2 = (fnptr2) &f2;  
  
   fnptr1 fp3 = (fnptr1) &f2;   // C4191  
   fnptr2 fp4 = (fnptr2) &f1;   // C4191  
};  
```