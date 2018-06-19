---
title: Bağlayıcı araçları hatası LNK1256 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- xml
- LNK1256
dev_langs:
- C++
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e4039dccb4dc8abd421b4622bbe928931f7f396
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300650"
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