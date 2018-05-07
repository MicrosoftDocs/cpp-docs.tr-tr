---
title: Derleyici Uyarısı (Düzey 3 ve 4) C4244 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4244
dev_langs:
- C++
helpviewer_keywords:
- C4244
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36908fa5f46cee0b86941ec630c3716c918e556f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-levels-3-and-4-c4244"></a>Derleyici Uyarısı (Düzey 3 ve 4) C4244
'type1' öğesinden 'type2', olası veri kaybını 'dönüştürme' dönüştürme  
  
 Bir tamsayı türü daha küçük bir tamsayı türü dönüştürülür. Bu düzey 4 uyarı ise *type1* olan `int` ve *type2* değerinden küçük `int`. Aksi takdirde, Düzey 3 olur (türünde bir değer atanan [__int64](../../cpp/int8-int16-int32-int64.md) türünde bir değişken için `unsigned int`). Olası veri kaybını oluşmuş olabilir.  
  
 C4244 alırsanız, uyumlu türleri kullanılacak programınızı değiştirmek veya olası değerleri aralığı her zaman, kullanmakta olduğunuz türleri ile uyumlu olmasını sağlamak için kodunuzun bazı mantığı ekleyin.  
  
 C4244 ayrıca 2 düzeyinde tetikleyebilir; bkz: [Derleyici Uyarısı (Düzey 2) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md) daha fazla bilgi için.  
  
 Dönüştürme örtük dönüşümler nedeniyle bir sorun olabilir.  
  
 Aşağıdaki örnek C4244 oluşturur:  
  
```  
// C4244_level4.cpp  
// compile with: /W4  
int aa;  
unsigned short bb;  
int main() {  
   int b = 0, c = 0;  
   short a = b + c;   // C4244  
  
   bb += c;   // C4244  
   bb = bb + c;   // C4244  
   bb += (unsigned short)aa;   // C4244  
   bb = bb + (unsigned short)aa;   // OK  
}  
```  
  
 Daha fazla bilgi için bkz: [olağan aritmetik dönüştürmeler](../../c-language/usual-arithmetic-conversions.md).  
  
```  
// C4244_level3.cpp  
// compile with: /W3  
int main() {  
   __int64 i = 8;  
   unsigned int ii = i;   // C4244  
}  
```  
  
 64-bit hedefleri için kod oluşturma uyarı için 32-bit hedefleri oluşturulurken oluşturmaz C4244 uyarı ortaya çıkabilir. Örneğin, bir arasındaki işaretçileri 32-bit platformlarda 32-bitlik bir miktar ancak 64 bit platformlarda 64-bitlik bir miktar farktır.  
  
 Aşağıdaki örnek, 64-bit hedefler için derlendiğinde C4244 oluşturur:  
  
```  
// C4244_level3_b.cpp  
// compile with: /W3   
int main() {  
   char* p1 = 0;  
   char* p2 = 0;  
   int x = p2 - p1;   // C4244  
}  
```