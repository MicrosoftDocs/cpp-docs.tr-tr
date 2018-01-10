---
title: "Derleyici Hatası C2993 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2993
dev_langs: C++
helpviewer_keywords: C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3715e2183c8194fe7bcf2613cbee3a0052588385
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2993"></a>Derleyici Hatası C2993
'tanımlayıcısı': 'parametresi' tür olmayan şablon parametresi için geçersiz tür  
  
 Bir şablonu yapısı veya birleşim bağımsız değişkeni ile bildiremezsiniz. İşaretçileri yapılar ve birleşimleri şablon parametreleri olarak geçirmek için kullanın.  
  
 Aşağıdaki örnek C2993 oluşturur:  
  
```  
// C2993.cpp  
// compile with: /c  
// C2993 expected  
struct MyStruct {  
   int a;char b;  
};  
  
template <class T, struct MyStruct S>   // C2993  
  
// try the following line instead  
// template <class T, struct MyStruct * S>  
class CMyClass {};  
```  
  
 Bu hata ayrıca Visual Studio .NET 2003'te yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulacak: kayan nokta artık izin tür olmayan şablon parametreleri. C++ Standart kayan nokta tür olmayan şablon parametreleri izin vermiyor.  
  
 İşlev şablonunun ise, kullanım kayan geçirmek için bir işlev bağımsız değişkeni tür olmayan şablon parametresi (Bu kodu Visual C++, Visual Studio .NET 2003 ve Visual Studio .NET sürümlerinde geçerli olur) üzerine gelin. Sınıf şablonu ise, kolay geçici çözüm yoktur.  
  
```  
// C2993b.cpp  
// compile with: /c  
template<class T, float f> void func(T) {}   // C2993  
  
// OK  
template<class T>   void func2(T, float) {}  
```