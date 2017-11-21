---
title: "Derleyici Hatası C2756 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2756
dev_langs: C++
helpviewer_keywords: C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4ca6e01d1c4b2f7dda2a941eeef4599d62241fe3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2756"></a>Derleyici Hatası C2756
'şablon türü': varsayılan şablon değişkenlerini kısmi uzmanlığı üzerinde izin verilmiyor  
  
 Şablon için bir kısmi uzmanlığı varsayılan bağımsız değişkeni içerebilir.  
  
 Aşağıdaki örnek C2756 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2756.cpp  
template <class T>  
struct S {};  
  
template <class T=int>  
// try the following line instead  
// template <class T>  
struct S<T*> {};   // C2756  
```