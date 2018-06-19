---
title: Komut satırı uyarısı D9041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9041
dev_langs:
- C++
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c22573d26e09e14789f4cbd64d68f4082125c2b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298645"
---
# <a name="command-line-warning-d9041"></a>Komut Satırı Uyarısı D9041
Geçersiz bir değer 'value' için '/ seçeneği'; ' değeri '; Ekle ' / analyze' Bu uyarı belirtirken komut satırı seçenekleri  
  
 Kod çözümleme uyarı numarası eklendi **/wd**, **/we**, **/wo**, veya **/wl** debelirtmedenkomutsatırıseçeneği **/ analyze** komut satırı seçeneği. Bu hatayı düzeltmek için ekleyip ya da **/ analyze** komut satırı seçeneği ya da geçersiz uyarı numarasını uygun Kaldır **/w** komut satırı seçeneği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek komut satırı uyarısı D9041 oluşturur:  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 Uyarı düzeltmek için add **/ analyze** komut satırı seçeneği. Varsa **/ analyze** olan geçersiz uyarı numarasından kaldırma derleyici sürümünüz desteklenmiyor, **/wd** seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut satırı hataları D8000-D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)