---
title: Derleyici Uyarısı (düzey 1) C4747 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4747
dev_langs:
- C++
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 203943f3741d07e278652a7032a6dcdcb305a384
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285830"
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