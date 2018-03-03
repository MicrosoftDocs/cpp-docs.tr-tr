---
title: "Derleyici Hatası C3888 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e6f0310324afcbde112623959c4dc3b11155fed1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3888"></a>Derleyici Hatası C3888
'name': Bu değişmez değer veri üye ile ilişkili const ifade C + tarafından desteklenmiyor +/ CLI  
  
 *Adı* ile bildirilen veri üyesi [değişmez değer](../../windows/literal-cpp-component-extensions.md) anahtar sözcüğü derleyici desteği olmayan bir değerle başlatılır. Derleyici yalnızca sabit Entegral, numaralandırma veya dize türlerini destekler. Olası nedeni **C3888** hata: veri üyesi bir bayt dizisi başlatılır.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Bildirilen değişmez değer veri üyesi desteklenen bir tür olup olmadığını denetleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [değişmez değer](../../windows/literal-cpp-component-extensions.md)