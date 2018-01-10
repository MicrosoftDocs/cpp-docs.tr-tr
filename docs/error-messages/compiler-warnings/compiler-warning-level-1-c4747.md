---
title: "Derleyici Uyarısı (düzey 1) C4747 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4747
dev_langs: C++
helpviewer_keywords: C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 094576ec19582b640ba0d4c57dfa34593177a267
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4747"></a>Derleyici Uyarısı (düzey 1) C4747
Yönetilen 'entrypoint' çağrılırken: yönetilen kod çalıştıramıyor DLL entrypoint ve DLL entrypoint ulaşıldı çağrıları dahil olmak üzere, yükleyici kilidi altında  
  
 Derleyici MSIL için derlenmiş (olası) bir DLL giriş noktası bulunamadı.  Giriş noktası için MSIL derlenmiş DLL yüklenirken ile olası sorunları nedeniyle, MSIL DLL giriş noktası işlevine derleme kesinlikle önerilmez.  
  
 Daha fazla bilgi için bkz: [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md) ve [Bağlayıcı araçları hatası LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Modülüyle derleme değil **/CLR**.  
  
2.  Giriş noktası işlevi ile işaretle `#pragma unmanaged`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4747 oluşturur.  
  
```  
// C4747.cpp  
// compile with: /clr /c /W1  
// C4747 expected  
#include <windows.h>  
  
// Uncomment the following line to resolve.  
// #pragma unmanaged  
  
BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {  
   return TRUE;  
};  
```