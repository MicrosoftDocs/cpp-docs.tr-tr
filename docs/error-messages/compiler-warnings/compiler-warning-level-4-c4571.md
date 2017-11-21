---
title: "Derleyici Uyarısı (düzey 4) C4571 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4571
dev_langs: C++
helpviewer_keywords: C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 293a3ffa2ddb14292b33ed222f18ca6f8dc6faec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4571"></a>Derleyici Uyarısı (düzey 4) C4571
Bilgi amaçlı: Visual C++ 7.1 beri değiştirilen catch(...) semantiği; yapılandırılmış özel durum (SEH) artık yakalandı  
  
 C4571 ile derleme yapılırken her catch(...) bloğu için oluşturulan **/EHs**.  
  
 İle derleme yapılırken **/EHs**, catch(...) blok yakalamaz yapılandırılmış özel durum (sıfıra, örneğin null işaretçinin); açıkça oluşturulan bir catch(...) blok yalnızca catch, C++ özel durum.  Daha fazla bilgi için bkz: [özel durum işleme](../../cpp/exception-handling-in-visual-cpp.md).  
  
 Varsayılan olarak bu uyarı kapalıdır.  Bu üzerinde ile derlerken emin olmak için uyarıyı Kapat **/EHs** (...) catch blokları yapılandırılmış özel durumları yakalamak düşünmüyorsunuz.  Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 C4571 aşağıdaki yollardan biriyle çözümleyebilirsiniz,  
  
-   İle derleme **/EHa** yapılandırılmış özel durumları yakalamak için catch(...) blokları yine de istiyorsanız.  
  
-   Yapılandırılmış özel durumları yakalamak için catch(...) blokları istemiyorsanız, ancak hala catch(...) blokları kullanmak istediğiniz C4571 etkinleştirmeyin.  Yapılandırılmış özel durum işleme anahtar sözcükleri kullanarak yapılandırılmış özel durum hala yakalayabilir (**__try**, **__except**, ve **__finally**).  Ancak, derlendiğinde unutmayın **/EHs** Yıkıcılar, yalnızca değil SEH özel durum oluştuğunda C++ özel durum olduğunda çağrılır.  
  
-   Catch blokları belirli C++ özel durumlar için catch(...) blok yerine ve isteğe bağlı olarak yapılandırılmış özel durum işlemeyi C++ özel durum işleme geçici ekleyin (**__try**, **__except**, ve **_ _finally**).  Bkz: [yapılandırılmış özel durum işleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md) daha fazla bilgi için.  
  
 Bkz: [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4571 oluşturur.  
  
```  
// C4571.cpp  
// compile with: /EHs /W4 /c  
#pragma warning(default : 4571)  
int main() {  
   try {  
      int i = 0, j = 1;  
      j /= i;   // this will throw a SE (divide by zero)  
   }  
   catch(...) {}   // C4571 warning  
}  
```