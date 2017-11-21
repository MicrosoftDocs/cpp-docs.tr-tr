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
ms.openlocfilehash: d23d417b89f2b810fcf78c141bd51eb7ef4b311d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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