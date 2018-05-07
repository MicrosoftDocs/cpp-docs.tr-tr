---
title: NMAKE önemli hatası U1033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1d39d4c35ec66d405d51d601b7c5d2b2ab37b02
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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