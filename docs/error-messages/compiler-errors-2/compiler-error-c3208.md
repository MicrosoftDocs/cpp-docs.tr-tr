---
title: "Derleyici Hatası C3208 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3208
dev_langs: C++
helpviewer_keywords: C3208
ms.assetid: 6d060bfe-52cf-4599-8f70-bdeb5a670df3
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c5f9346ae786b967ccff4adfe2deddee839c361d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3208"></a>Derleyici Hatası C3208
'function': sınıf şablon 'sınıfı' şablon parametresi listesi şablonu şablon parametresi 'parametresi' şablon parametresi listesi eşleşmiyor  
  
 Şablon Şablon parametresi sağlanan sınıf şablonu aynı sayıda şablon parametreleri yok.  
  
 Aşağıdaki örnek C3208 oluşturur:  
  
```  
// C3208.cpp  
template <template <class T> class TT >  
int f();  
  
template <class T1, class T2>  
struct S;  
  
template <class T1>  
struct R;  
  
int i = f<S>();   // C3208  
// try the following line instead  
// int i = f<R>();  
```