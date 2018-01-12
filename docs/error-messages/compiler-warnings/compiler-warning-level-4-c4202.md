---
title: "Derleyici Uyarısı (düzey 4) C4202 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4202
dev_langs: C++
helpviewer_keywords: C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eee7919cd4b14eb8d307b5fbec986523db29dbf6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4202"></a>Derleyici Uyarısı (düzey 4) C4202
kullanılan standart olmayan uzantısı: '...': prototip parametre adı listesi geçersiz  
  
 Eski stil işlev tanımı değişken bağımsız değişken içeriyor. Bu tanımları ANSI Uyumluluğu altında bir hata oluştur ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>Örnek  
  
```  
// C4202.c  
// compile with: /W4  
void func( a, b, ...)   // C4202  
int a, b;  
{}  
  
int main()  
{  
}  
```