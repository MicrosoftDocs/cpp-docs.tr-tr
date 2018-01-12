---
title: "Derleyici Uyarısı (düzey 4) C4001 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4001
dev_langs: C++
helpviewer_keywords: C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3b5c3d82bef81ee84514b39a0ce8ab07ad6e6c36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4001"></a>Derleyici Uyarısı (düzey 4) C4001
Standart olmayan uzantı 'tek satır yorum' kullanıldı  

> [!NOTE] 
> Tek satırlı yorumlar C99 içinde standart olduğundan bu uyarı Visual Studio 2017 sürüm 15,5 kaldırılır.
  
 Tek satırlı yorumlar c++ standart ve standart C ile C99 başlatırken. Katı ANSI Uyumluluğu altında ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), tek satırlı yorumlar içeren C dosyaları standart olmayan bir uzantı kullanım nedeniyle C4001 oluşturur. Tek satırlı yorumlar C++'da standart olduğundan, tek satırlı yorumlar içeren C dosyaları C4001 Microsoft Uzantıları (/Ze) ile derleme yapılırken üretmez.  
  
## <a name="example"></a>Örnek  
 Uyarı devre dışı bırakmak için açıklamadan çıkarın [#pragma warning(disable:4001)](../../preprocessor/warning.md).  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```