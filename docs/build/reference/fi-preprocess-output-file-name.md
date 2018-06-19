---
title: -Fi (çıktı dosyası adını Önişle) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fi
dev_langs:
- C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e7fe5ffbb8a6ccdd5ef02d2cf3feb6b94d48233
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371518"
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