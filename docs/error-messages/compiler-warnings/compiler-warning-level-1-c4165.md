---
title: "Derleyici Uyarısı (düzey 1) C4165 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4165
dev_langs: C++
helpviewer_keywords: C4165
ms.assetid: f5bed515-2290-4f88-8dab-b45d95fe26ef
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b0764442e4a9b920cf120c82715368bcba5c8099
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4165"></a>Derleyici Uyarısı (düzey 1) C4165
'Bool'; 'HRESULT' dönüştürülüyor Bu istediğinize emin misiniz?  
  
Bir HRESULT kullanırken bir [varsa](../../cpp/if-else-statement-cpp.md) deyimi, HRESULT dönüştürülür bir [bool](../../cpp/bool-cpp.md) açıkça değişkeni olarak bir HRESULT için test sürece. Varsayılan olarak bu uyarı kapalıdır.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C4165 oluşturur  
  
```cpp  
// C4165.cpp  
// compile with: /W1  
#include <windows.h>  
#pragma warning(1:4165)  
  
extern HRESULT hr;  
int main() {  
   if (hr) {  
   // try either of the following ...  
   // if (FAILED(hr)) { // C4165 expected  
   // if (hr != S_OK) {  
   }  
}  
```