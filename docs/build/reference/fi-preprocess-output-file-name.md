---
title: "-Fi (çıktı dosyası adını Önişle) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Fi
dev_langs: C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9bc3076a529984358aed16902f509ceb01423f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (Çıktı Dosyası Adını Önişle)
Çıktı dosyasına adını belirtir [/P (dosyaya Önişle)](../../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği önceden işlenmiş çıktısı yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Fipathname  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`pathname`|Çıktı dosyası yolu ve adı üretilen **/P** derleyici seçeneği.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım **/Fi** derleyici seçeneği ile birlikte **/P** derleyici seçeneği.  
  
 İçin bir yol belirtirseniz, `pathname` parametresi, kaynak dosyasının temel adı önceden işlenmiş çıkış dosyasının temel adı kullanılır. `pathname` Parametresi belirli dosya adı uzantısı gerektirmez. Ancak, bir dosya adı uzantısı belirtmezseniz, ".i" uzantısı kullanılır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını PROGRAM.cpp preprocesses, Yorumlar korur, ekler [#line](../../preprocessor/hash-line-directive-c-cpp.md) yönergeleri ve sonucu MYPROCESS.i dosyasına yazar.  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [/P (dosyaya önişle)](../../build/reference/p-preprocess-to-a-file.md)   
 [Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)