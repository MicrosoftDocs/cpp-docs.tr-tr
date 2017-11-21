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
ms.openlocfilehash: a6499e3720cf6d61fa124c2fc5a43ce2ff30f249
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Yol adını belirtme](../../build/reference/specifying-the-pathname.md)