---
title: "Derleyici Hatası C3808 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3808
dev_langs: C++
helpviewer_keywords: C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4d6a255bebeccc0c63ba621a7c5886fd318ffd5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3808"></a>Derleyici Hatası C3808
'type': ComImport özniteliğine sahip bir sınıf üyesi 'member', yalnızca soyut tanımlanamıyor veya dllimport işlevleri izin verilir  
  
 Türetilen bir tür <xref:System.Runtime.InteropServices.ComImportAttribute> tanımlayamazsınız `member`.  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3808 oluşturur.  
  
```  
// C3808.cpp  
// compile with: /c /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 {  
   int f() {}   // C3808  
   virtual int g() abstract;   // OK  
  
   [DllImport("msvcrt.dll")]  
   int printf(System::String ^, int i);   // OK  
};  
```