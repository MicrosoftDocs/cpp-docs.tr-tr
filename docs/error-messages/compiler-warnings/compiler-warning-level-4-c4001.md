---
title: Derleyici Uyarısı (düzey 4) C4001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc728fa5c66fb4b42c8fe4a785f36048ffbaed4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292665"
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