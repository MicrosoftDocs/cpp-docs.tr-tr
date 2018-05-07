---
title: Derleyici Uyarısı (düzey 4) C4256 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4256
dev_langs:
- C++
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed1a40f0da75460c4306f69da0f26eb0888bef66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4256"></a>Derleyici Uyarısı (düzey 4) C4256
'function': sanal tabanları ile sınıf için bir oluşturucuya sahip '...'; çağrıları Visual C++ eski sürümleriyle uyumlu olmayabilir  
  
 Olası uyumsuzluk.  
  
 Aşağıdaki kod örneği göz önünde bulundurun. Varsa S2::S2 Oluşturucusu tanımını (int i,...) sürüm 7, önce Visual C++ Derleyici sürümünü kullanarak derlenen ancak aşağıdaki örnekte geçerli sürümü tarafından derlenip, oluşturucuya çağrısı S3 için doğru nedeniyle çalışmayan bir özel durum çağırma kuralı değiştirin. Her ikisi de Visual C++ 6.0 kullanılarak derlendi, hiçbir parametreler için üç nokta geçirilmiş sürece çağrının oldukça sağ ya da, çalışır değil.  
  
 Bu uyarıyı çözmek için  
  
1.  Oluşturucu içinde üç nokta kullanmayın.  
  
2.  Kendi projedeki tüm bileşenleri (tanımlayın veya bu sınıfa referans kitaplıkları dahil) geçerli sürümüyle oluşturulmuş ve ardından uyarı kullanarak devre dışı olduğundan emin olun [uyarı](../../preprocessor/warning.md) pragması.  
  
 Aşağıdaki örnek C4256 oluşturur:  
  
```  
// C4256.cpp  
// compile with: /W4  
// #pragma warning(disable : 4256)  
struct S1  
{  
};  
  
struct S2: virtual public S1  
{  
   S2( int i, ... )    // C4256  
   {  
      i = 0;  
   }  
   /*  
   // try the following line instead  
   S2( int i)  
   {  
      i = 0;  
   }  
   */  
};  
  
void func1()  
{  
   S2 S3( 2, 1, 2 );   // C4256  
   // try the following line instead  
   // S2 S3( 2 );  
}  
  
int main()  
{  
}  
```