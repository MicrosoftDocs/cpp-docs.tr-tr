---
title: Derleyici Hatası C3836 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3836
dev_langs:
- C++
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45a2eda2567e63771ed4c8919945e34ee41be1cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267400"
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
