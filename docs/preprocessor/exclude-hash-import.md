---
title: "(#import) hariç | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exclude
dev_langs: C++
helpviewer_keywords: exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f28a4ce5e06687c279d80bc482895c9394726841
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="exclude-import"></a>exclude (#import)
**C++ özel**  
  
 Öğeleri, oluşturulan tür kitaplığı üstbilgi dosyalarından çıkarır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
exclude("Name1"[, "Name2",...])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Name1`  
 Çıkarılacak ilk öğe.  
  
 `Name2`  
 Çıkarılacak ikinci öğe (gerekirse).  
  
## <a name="remarks"></a>Açıklamalar  
 Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. Bu öznitelik, her biri çıkarılacak üst düzey tür kitaplığı öğesi olan herhangi bir sayıda bağımsız değişken alabilir.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)