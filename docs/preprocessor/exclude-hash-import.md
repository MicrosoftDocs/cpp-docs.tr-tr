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
ms.workload: cplusplus
ms.openlocfilehash: bd63eed4eea9404fd0a542c0be20f1770e461508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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