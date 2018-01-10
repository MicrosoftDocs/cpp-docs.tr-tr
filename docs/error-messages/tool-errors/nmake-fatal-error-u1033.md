---
title: "NMAKE önemli hatası U1033 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1033
dev_langs: C++
helpviewer_keywords: U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 94f2626e1ce318d83d306595e386f880c62dec3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE Önemli Hatası U1033
sözdizimi hatası: 'string' beklenmeyen  
  
 Dize derleme görevleri dosyası söz diziminin geçerli bir parçası değil.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Kapanış köşeli ayarlarsanız (**<<**) satır içi dosya olmayan için bir satır başında, aşağıdaki hata oluşur:  
  
    ```  
    syntax error : 'EOF' unexpected  
    ```  
  
2.  Derleme görevleri dosyası makrosu tanımında eşittir işareti bulunan varsa (**=**) bir önceki adı veya bir şey genişletir makrosu adı tanımlanmakta ise olmadan aşağıdaki hata oluşur:  
  
    ```  
    syntax error : '=' unexpected  
    ```  
  
3.  Noktalı virgül (**;**) bir açıklama satırı araçlarında. INI satır başında aşağıdaki hata oluşuyor değil:  
  
    ```  
    syntax error : ';' unexpected  
    ```  
  
4.  Derleme görevleri dosyası bir sözcük işlemci tarafından biçimlendirilmiş, aşağıdaki hata oluşabilir:  
  
    ```  
    syntax error : ':' unexpected  
    ```