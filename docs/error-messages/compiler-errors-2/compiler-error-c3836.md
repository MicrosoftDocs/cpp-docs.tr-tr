---
title: "Derleyici Hatası C3836 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3836
dev_langs: C++
helpviewer_keywords: C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed48f6fd044ccc17dacd79d774f8db2c6888a0cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3836"></a>Derleyici Hatası C3836
statik Oluşturucusu bir üye Başlatıcı listeniz izin verilmiyor  
  
 Yönetilen sınıf üye başlatma listesi olan bir statik Oluşturucu sahip olamaz. Statik sınıf oluşturucular statik veri üyeleri başlatma başlatma, sınıf için ortak dil çalışma zamanı tarafından çağrılır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3836 oluşturur:  
  
```  
// C3836a.cpp  
// compile with: /clr  
ref class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```  
