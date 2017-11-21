---
title: "Derleyici Uyarısı (düzey 1) C4742 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4742
dev_langs: C++
helpviewer_keywords: C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 934c7d14d95d0b90cfdcdb694f743e6b13abd0e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4742"></a>Derleyici Uyarısı (düzey 1) C4742
'var' olan 'dosya1' ve 'dosya2' farklı hizalama: ve numarası  
  
 Başvurulan veya iki dosyasında tanımlanan bir dış değişken bu dosyaları farklı hizalama yok. Derleyici bulduğunda, bu uyarıyı yayılan `__alignof` bir değişken için *dosya1* farklıdır `__alignof` bir değişken için *dosya2*. Bu değişken farklı dosyalarında bildirirken uyumsuz türlerin kullanarak veya eşleşmeyen kullanarak kaynaklanabilir `#pragma pack` farklı dosyalarında.  
  
 Bu uyarıyı çözmek için aynı tür tanımı kullanın veya değişkenleri için farklı adlar kullanabilirsiniz.  
  
 Daha fazla bilgi için bkz: [paketi](../../preprocessor/pack.md) ve [__alignof işleci](../../cpp/alignof-operator.md).  
  
## <a name="example"></a>Örnek  
 Bu türü tanımlayan ilk dosyasıdır.  
  
```  
// C4742a.c  
// compile with: /c  
struct X {  
   char x, y, z, w;  
} global;  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4742 oluşturur.  
  
```  
// C4742b.c  
// compile with: C4742a.c /W1 /GL  
// C4742 expected  
extern struct X {  
   int a;  
} global;  
  
int main() {  
   global.a = 0;  
}  
```