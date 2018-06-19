---
title: Derleyici Uyarısı (düzey 1) C4742 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4742
dev_langs:
- C++
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9c5c891699e89b177f9a3c070a95f496e2c77ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282086"
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