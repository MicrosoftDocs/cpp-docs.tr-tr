---
title: "Komut satırı uyarısı D9041 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9041
dev_langs: C++
helpviewer_keywords: D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9f80de8e9bbbf7c754ac8e13061ef3ae50c4715a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="command-line-warning-d9041"></a>Komut Satırı Uyarısı D9041
Geçersiz bir değer 'value' için '/ seçeneği'; ' değeri '; Ekle ' / analyze' Bu uyarı belirtirken komut satırı seçenekleri  
  
 Kod çözümleme uyarı numarası eklendi **/wd**, **/we**, **/wo**, veya **/wl** debelirtmedenkomutsatırıseçeneği**/ analyze** komut satırı seçeneği. Bu hatayı düzeltmek için ekleyip ya da **/ analyze** komut satırı seçeneği ya da geçersiz uyarı numarasını uygun Kaldır **/w** komut satırı seçeneği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek komut satırı uyarısı D9041 oluşturur:  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 Uyarı düzeltmek için add **/ analyze** komut satırı seçeneği. Varsa **/ analyze** olan geçersiz uyarı numarasından kaldırma derleyici sürümünüz desteklenmiyor, **/wd** seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut satırı hataları D8000-D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)