---
title: "Derleyici Hatası C2768 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2768
dev_langs: C++
helpviewer_keywords: C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42f4c23f36669ae2dd3284d8902f6ba017617201
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2768"></a>Derleyici Hatası C2768
'function': Geçersiz bağımsız açık şablon kullanımı  
  
 Derleyici işlev tanımı bir işlev şablonunun açık alt uzmanlaşması olması gerekiyordu veya işlev tanımı için yeni bir işlev olması gerekiyordu belirleyemedi.  
  
 Bu hata, Visual Studio .NET 2003'te derleyici uyumluluğu geliştirmeleri bir parçası olarak sunulmuştur.  
  
 Aşağıdaki örnek C2768 oluşturur:  
  
```  
// C2768.cpp  
template<typename T>  
void f(T) {}  
  
void f<int>(int) {}   // C2768  
  
// an explicit specialization  
template<>  
void f<int>(int) {}   
  
// global nontemplate function overload  
void f(int) {}  
```