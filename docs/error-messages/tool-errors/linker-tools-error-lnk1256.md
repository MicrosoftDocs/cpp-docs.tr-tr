---
title: "Bağlayıcı araçları hatası LNK1256 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- xml
- LNK1256
dev_langs: C++
helpviewer_keywords: LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5a7b024971c1e2e9c938ee6519772f59f333fb28
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1256"></a>Bağlayıcı Araçları Hatası LNK1256
ALINK işlemi başarısız oldu: nedeni  
  
 LNK1256 ortak bir nedeni, bir derleme için yanlış sürüm numarasıdır. Derleme sürüm numarası, herhangi bir bölümünü değeri 65535 izin verilmiyor. Derleme sürümleri için geçerli aralık 0 - olduğu 65534.  
  
 ALINK adlandırılmış anahtar kapsayıcısını bulamadı, LNK1256 da neden olabilir. Anahtar kapsayıcısını silmek ve kullanarak yeniden tanımlayıcı ad CSP eklemek [Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool).  
  
 LNK1256 başka bir nedeni bağlayıcı ve Alink.dll arasında sürüm uyuşmazlığı olmasıdır. Bu, bozuk bir Visual Studio yüklemesi tarafından neden olabilir. Kullanım **programlar ve Özellikler** onarmak veya Visual Studio yeniden yüklemek için Windows Denetim Masası'nda.  
  
 Aşağıdaki örnek LNK1256 oluşturur:  
  
```  
// LNK1256.cpp  
// compile with: /clr /LD  
// LNK1256 expected  
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];  
public class CMyClass {  
public:  
   int value;  
};  
```