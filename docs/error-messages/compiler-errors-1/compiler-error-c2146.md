---
title: "Derleyici Hatası C2146 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2146
dev_langs: C++
helpviewer_keywords: C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a7da8021cabb5eab31ae12912374268ee4d7d24b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2146"></a>Derleyici Hatası C2146
sözdizimi hatası: 'tanımlayıcısı 'tanımlayıcısı' önce belirteci' eksik  
  
 Beklenen derleyici `token` ve bulunan `identifier` yerine.  Olası nedenler:  
  
1.  Yazım veya büyük/küçük harf hata oluştu.  
  
2.  Tanımlayıcının bildiriminde eksik tür belirteci.  
  
 Bu hata, bir yazım hatası nedeni olabilir. Hata [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) genellikle bu hata önce gelir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2146 oluşturur.  
  
```  
// C2146.cpp  
class CDeclaredClass {};  
  
class CMyClass {  
   CUndeclared m_myClass;   // C2146  
   CDeclaredClass m_myClass2;   // OK  
};  
  
int main() {  
   int x;  
   int t x;   // C2146 : missing semicolon before 'x'  
}  
```  
  
## <a name="example"></a>Örnek  
 Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucunda da oluşturulabilir: eksik `typename` anahtar sözcüğü.  
  
 Aşağıdaki örnek Visual Studio .NET 2002'de derler ancak Visual Studio .NET 2003'te başarısız olur:  
  
```  
// C2146b.cpp  
// compile with: /c  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
  
template <typename T>  
X<T>::Y func() { }   // C2146  
  
// OK  
template <typename T>  
typename X<T>::Y func() { }  
```  
  
## <a name="example"></a>Örnek  
 Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucunda ayrıca görürsünüz: açık özelleştirmeleri birincil şablondan şablon parametreleri artık bulunamıyor.  
  
 Kullanımını `T` birincil şablondan açık uzmanlık içinde izin verilmiyor. Kodun Visual C++, Visual Studio .NET 2003 ve Visual Studio .NET sürümlerinde geçerli olması için tüm örneklerini uzmanlık şablon parametresinde açıkça özel türüyle değiştirin.  
  
 Aşağıdaki örnek Visual Studio .NET ile derlenen ancak Visual Studio .NET 2003'te başarısız olur:  
  
```  
// C2146_c.cpp  
// compile with: /c  
template <class T>   
struct S;  
  
template <>   
struct S<int> {  
   T m_t;   // C2146  
   int m_t2;   // OK  
};  
```