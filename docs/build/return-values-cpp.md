---
title: "Dönüş değerleri (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 53583524-b337-4228-a9c6-c9bf516babe8
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8f8ac22790fa6b94dd19ba7d46cf737824e898f1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="return-values-c"></a>Dönüş Değerleri (C++)
64 bit sığması skaler bir dönüş değeri RAX üzerinden döndürülür — bu __m64 türleri içerir. Float, double ve vektör türleri gibi dahil olmayan skaler türleri [__m128](../cpp/m128.md), [__m128i](../cpp/m128i.md), [__m128d](../cpp/m128d.md) XMM0'döndürdü. Kullanılmayan BITS RAX veya XMM0 döndürülen değeri durumunu tanımlanmamıştır.  
  
 Kullanıcı tanımlı türler, genel işlevler ve statik üye işlevleri değeri tarafından döndürülebilir. RAX değerinde tarafından döndürülen için kullanıcı tanımlı türler 1, 2, 4, 8, 16, 32 veya 64 bit uzunluğu olmalıdır; hiçbir kullanıcı tanımlı oluşturucusu, yıkıcı veya kopya atama işleci; hiçbir özel veya korumalı olmayan statik veri üyeleri; Başvuru türü statik olmayan veri üye yok; taban sınıf yok; sanal işlevler yok; ve ayrıca bu gereksinimleri karşılamayan veri üye yok. (Bu temelde C ++ 03 tanımıdır POD türü. C ++ 11'de standart tanımı değiştiğinden kullanmanız önerilmez `std::is_pod` bu test için.) Aksi durumda, çağıranın bellek ayırma ve dönüş değeri için bir işaretçi ilk bağımsız değişken geçirme sorumluluğu üstlenir. Sonraki bağımsız değişkenler sonra sağ tarafta bir bağımsız değişken gölgeye. Aynı işaretçi RAX'daki Aranan tarafından döndürülen gerekir.  
  
 Bu örnekler, parametreler ve dönüş değerleri belirtilen bildirimleri işlevleriyle için nasıl geçirilir gösterir:  
  
## <a name="example-of-return-value-1---64-bit-result"></a>Dönüş değeri 1-64 bit sonuç örneği  
  
```Output  
__int64 func1(int a, float b, int c, int d, int e);  
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,  
// callee returns __int64 result in RAX.  
```  
  
## <a name="example-of-return-value-2---128-bit-result"></a>Dönüş değeri 2-128 bit sonuç örneği  
  
```Output  
__m128 func2(float a, double b, int c, __m64 d);   
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,   
// callee returns __m128 result in XMM0.  
```  
  
## <a name="example-of-return-value-3---user-type-result-by-pointer"></a>Dönüş değeri 3 - kullanıcı türü sonucu işaretçisi örneği  
  
```Output  
struct Struct1 {  
   int j, k, l;    // Struct1 exceeds 64 bits.   
};  
Struct1 func3(int a, double b, int c, float d);   
// Caller allocates memory for Struct1 returned and passes pointer in RCX,   
// a in RDX, b in XMM2, c in R9, d pushed on the stack;   
// callee returns pointer to Struct1 result in RAX.  
```  
  
## <a name="example-of-return-value-4---user-type-result-by-value"></a>Dönüş değeri 4 - kullanıcı türü sonucu değeriyle örneği  
  
```Output  
struct Struct2 {  
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.  
};  
Struct2 func4(int a, double b, int c, float d);   
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;   
// callee returns Struct2 result by value in RAX.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma kuralı](../build/calling-convention.md)