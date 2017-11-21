---
title: "Bağlayıcı araçları hatası LNK2033 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2033
dev_langs: C++
helpviewer_keywords: LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 41bba79acaca7a83e4103d7d146831dc60c2c2ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2033"></a>Bağlayıcı Araçları Hatası LNK2033
'type' için çözümlenmemiş typeref belirteci (belirteç)  
  
 Bir tür tanımı MSIL meta verilerde yok.  
  
 LNK2033 ile derleme yapılırken oluşabilir **/CLR: safe** ve burada türü başvurulmaktadır MSIL modülünde bir MSIL modülü türü için yalnızca ileriye dönük bildirimi olduğu.  
  
 Tür altında tanımlanması gerekiyor **/CLR: safe**.  
  
 Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek LNK2033 oluşturur.  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```