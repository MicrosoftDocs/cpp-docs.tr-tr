---
title: Derleyici Hatası C2947 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2947
dev_langs:
- C++
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1af4e6a5a27c13d69351eaf0cddfafe11ba5f22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2947"></a>Derleyici Hatası C2947
bekleniyor ' >' yapı sonlandırmak için 'sözdizimi' bulundu  
  
 Genel veya şablon bağımsız değişken listesi doğru bir şekilde sona erdirildi değil.  
  
 C2947 da sözdizimi hataları tarafından oluşturulabilir.  
  
 Aşağıdaki örnek C2947 oluşturur:  
  
```  
// C2947.cpp  
// compile with: /c  
template <typename T>=   // C2947  
// try the following line instead  
// template <typename T>  
struct A {};  
```