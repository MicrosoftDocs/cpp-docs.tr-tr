---
title: "Derleyici Hatası C3415 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3415
dev_langs: C++
helpviewer_keywords: C3415
ms.assetid: fa2db8ab-2820-4ec3-a740-fb5e2adcfb29
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1237db7e705d12115b4bb1ab18d23b516c40d6a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3415"></a>Derleyici Hatası C3415
birden çok 'section_name' bölümü farklı öznitelikleri ('değeri') bulunamadı  
  
 Çakışan değerler belirtildi [bölüm](../../preprocessor/section.md) pragmaları.  
  
 `value`Geçerli ntimage.h belirtildiği gibi bölüm için bir ayardır. Örneğin:  
  
```  
// Section contains extended relocations.  
#define IMAGE_SCN_LNK_NRELOC_OVFL            0x01000000    
// Section can be discarded.  
#define IMAGE_SCN_MEM_DISCARDABLE            0x02000000    
// Section is not cachable.  
#define IMAGE_SCN_MEM_NOT_CACHED             0x04000000    
// Section is not pageable.  
#define IMAGE_SCN_MEM_NOT_PAGED              0x08000000    
// Section is shareable.  
#define IMAGE_SCN_MEM_SHARED                 0x10000000    
// Section is executable.  
#define IMAGE_SCN_MEM_EXECUTE                0x20000000    
// Section is readable.  
#define IMAGE_SCN_MEM_READ                   0x40000000    
// Section is writeable.  
#define IMAGE_SCN_MEM_WRITE                  0x80000000    
```  
  
 Aşağıdaki örnek C3415 oluşturur:  
  
```  
// C3415.cpp  
#pragma section("mysec1",write)  
#pragma section("mysec1",read)   // C3415  
```