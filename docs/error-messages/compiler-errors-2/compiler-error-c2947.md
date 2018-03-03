---
title: "Derleyici Hatası C2947 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2947
dev_langs:
- C++
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79083bc2713a21de24008a58ebb02ef15265cf39
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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