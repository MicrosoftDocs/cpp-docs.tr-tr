---
title: Derleyici Hatası C2897 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2897
dev_langs:
- C++
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c3de4c0d3e6a93a783dfb660bc26f07be6fcacf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245890"
---
# <a name="compiler-error-c2897"></a>Derleyici Hatası C2897
yok Edicisi/Sonlandırıcı işlevi şablonu olamaz  
  
 Bir yıkıcı (yıkıcı bir dizi tanımlarsınız) bir şablon bildirme izin için Yıkıcılar veya sonlandırıcılar, aşırı yüklenemez.  
  
 Aşağıdaki örnek C2897 oluşturur:  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2897 oluşturur.  
  
```  
// C2897.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> ~X() {}   // C2897  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2897 oluşturur.  
  
```  
// C2897_b.cpp  
// compile with: /c /clr  
ref struct R2 {  
protected:  
   template<typename T> !R2(){}   // C2897 error  
};  
```