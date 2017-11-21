---
title: "Derleyici Hatası C2728 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2728
dev_langs: C++
helpviewer_keywords: C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f83665f1f2b388ac751dd4fd4aec2f75e8651a3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2728"></a>Derleyici Hatası C2728
'type': yerel bir dizi bu tür içeremez  
  
 Dizi oluşturma sözdizimi, bir dizi oluşturmak için kullanılmış yönetilen veya WinRT nesneleri. Bir dizi oluşturulamıyor yönetilen veya yerel array sözdizimini kullanarak WinRT nesneleri.  
  
 Daha fazla bilgi için bkz: [dizi](../../windows/arrays-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C2728 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2728.cpp  
// compile with: /clr  
  
int main() {  
   int^ arr[5];   // C2728  
  
   // try the following line instead  
   array<int>^arr2;  
}  
```  
