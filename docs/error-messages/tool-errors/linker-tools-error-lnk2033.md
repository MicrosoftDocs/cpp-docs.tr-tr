---
title: Bağlayıcı araçları hatası LNK2033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2033
dev_langs:
- C++
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d03e8d2e0502d6e3664bff05c75fffb4f4ebd5da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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