---
title: Derleyici Uyarısı (düzey 1) C4010 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06ab6307a34887fe2d8a8719e20c31da9728664b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4010"></a>Derleyici Uyarısı (düzey 1) C4010
Satır devamlılığı karakteri tek satırlı yorum içerir  
  
 Tarafından sunulan tek satırlı bir yorum, / / ters eğik çizgi içerir (\\) satır devamlılığı karakteri olarak görev yapar. Derleyici bir devamlılık olması için sonraki satıra göz önünde bulundurur ve yorum olarak değerlendirir.  
  
 Bazı sözdizimi düzenleyicileri devamlılığı karakteri bir açıklama olarak aşağıdaki satırı göstermiyor yönelik. Bu uyarı neden tüm satırlarda renklendirme sözdizimi yoksay.  
  
 Aşağıdaki örnek C4010 oluşturur:  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```