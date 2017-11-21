---
title: "Derleyici Uyarısı (düzey 1) C4743 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4743
dev_langs: C++
helpviewer_keywords: C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 28ab5a9535184ea06ab9dd8f6e6203b98992e975
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4743"></a>Derleyici Uyarısı (düzey 1) C4743
'*türü*'farklı boyutuna sahip '*dosya1*'ve'*dosya2*': *numarası* ve *numarası* bayt  
  
 Başvurulan veya iki dosyasında tanımlanan bir dış değişken farklı türleri bu dosyaları sahiptir ve derleyici belirlenen değişkende boyutunu *dosya1* değişkende boyutunu farklıdır *dosya2*.  
  
 Bu uyarı için C++ yayınlaması gerektiğini zaman önemli söz konusu değildir. Bu bildirimler sanal işlevler içeriyorsa ve bildirimler aynı değilse iki farklı dosyaları aynı adla aynı türlerini bildirirseniz derleyici uyarı C4744 sanal işlev tablolar için yayma. Uyarı aynı tür için iki farklı boyutlu sanal işlev tabloları yoktur ve bağlayıcı yürütülebilir birleştirmek için bunlardan birini seçmeniz gerekir çünkü oluşur.  Bu yanlış sanal işlev çağırma programınıza sonuçlanabilir mümkündür.  
  
 Bu uyarıyı çözmek için aynı tür tanımı kullanın veya türleri veya değişkenleri için farklı adlar kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Bu örnek türünün bir tanımını içerir.  
  
```  
// C4743a.cpp  
// compile with: /c  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
};  
  
void C::f1(void) {}  
void C::f2(void) {}  
void C::f3(void) {}  
C q;  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4743 oluşturur.  
  
```  
// C4743b.cpp  
// compile with: C4743a.cpp /W1 /GL /O2  
// C4743 expected  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
    virtual void f4(void);  
    virtual void f5(void);  
};  
  
void C::f4(void) {}  
void C::f5(void) {}  
C x;  
  
int main() {}   
```